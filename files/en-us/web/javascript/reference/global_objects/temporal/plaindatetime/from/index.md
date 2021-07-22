---
title: Temporal.PlainDateTime.from()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/from
tags:
  - Class
  - JavaScript
  - date
---
{{JSRef}}

The **`from()`** static method creates a new
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object from another value.

## Syntax

```js
from(dateTime)
from(dateTime, options)
```

### Parameters

- `dateTime`

  - : A representation of the desired date and time, either as an object or as a
    string in valid ISO 8601 format. If the value is another
    {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
    object, a new object representing the same date is returned.

    If the value is any other object, it must contain, at a minimum:

    - A `year` or `eraYear` property.

      - If `eraYear` is used, an `era` must also be supplied.

    - Either a `month` or a `monthCode` property.
    - A `day` property. The object may also contain a `calendar` property; if
      omitted, the ISO 8601 calendar is used. The default value of any omitted
      date-related property (e.g.,
      {{jsxref('Temporal.PlainDateTime/era','era')}}) is
      determined by the calendar in use. The default value of any omitted
      time-related property (e.g.,
      {{jsxref('Temporal.PlainDateTime/minute','minute')}}) is
      zero.

    Any non-object, non-string value will be converted to a string, which is
    expected to be in ISO 8601 format. For other calendars, the calendar is also
    parsed in addition to date and time. Any other parts of the string, such as
    a time zone, are optional and will be ignored. If the string is invalid
    according to ISO 8601, then a `RangeError` will be thrown regardless of the
    value of the `overflow` option (see next).

- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new `Temporal.PlainDateTime` object. These are:
    - `overflow`
      - : Determines how out-of-range values in _dateTime_ are handled. There
        are two options:
        - `'constrain'` (default)
          - : Out-of-range values are clamped to the nearest in-range value.
        - `'reject'` \* : Out-of-range values will cause the function to throw a
          `RangeError`.
          > **Note:** If _dateTime_ is a string, the `overflow` property's value
          > is ignored. **Warning:** Although Temporal does not deal with leap
          > seconds, times coming from other software may have a `second` value
          > of `60`. In the default `constrain` mode, this will be converted to
          > `59`. In `reject` mode, the constructor will throw, so if you have
          > to interoperate with times that may contain leap seconds, don't use
          > `reject`. However, if parsing an ISO 8601 string with a seconds
          > component of `:60`, then it will always result in a `second` value
          > of `59`, in accordance with POSIX.

### Return value

A new
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object. If the result is earlier or later than the range of dates
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
can represent (approximately half a million years centered on the Unix epoch),
this function will throw a `RangeError` regardless of the value of `overflow`.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30');
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30Z'); // => 1995-12-07T03:24:30
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30+01:00[Europe/Brussels]');
  // => 1995-12-07T03:24:30
  // same as above; time zone is ignored
dt === Temporal.PlainDateTime.from(dt); // => false

dt = Temporal.PlainDateTime.from({
  year: 1995,
  month: 12,
  day: 7,
  hour: 3,
  minute: 24,
  second: 30,
  millisecond: 0,
  microsecond: 3,
  nanosecond: 500
}); // => 1995-12-07T03:24:30.0000035
dt = Temporal.PlainDateTime.from({ year: 1995, month: 12, day: 7 }); // => 1995-12-07T00:00:00
dt = Temporal.PlainDateTime.from(Temporal.PlainDate.from('1995-12-07T03:24:30'));
  // => 1995-12-07T00:00:00
  // same as above; Temporal.PlainDate has year, month, and day properties

calendar = Temporal.Calendar.from('hebrew');
dt = Temporal.PlainDateTime.from({ year: 5756, month: 3, day: 14, hour: 3, minute: 24, second: 30, calendar });
  // => 1995-12-07T03:24:30[u-ca=hebrew]
dt = Temporal.PlainDateTime.from({ year: 5756, month: 3, day: 14, hour: 3, minute: 24, second: 30, calendar: 'hebrew' });
  // => 1995-12-07T03:24:30[u-ca=hebrew]
  // same as above

// Different overflow modes
dt = Temporal.PlainDateTime.from({ year: 2001, month: 13, day: 1 }, { overflow: 'constrain' });
  // => 2001-12-01T00:00:00
dt = Temporal.PlainDateTime.from({ year: 2001, month: 1, day: 32 }, { overflow: 'constrain' });
  // => 2001-01-31T00:00:00
dt = Temporal.PlainDateTime.from({ year: 2001, month: 1, day: 1, hour: 25 }, { overflow: 'constrain' });
  // => 2001-01-01T23:00:00
dt = Temporal.PlainDateTime.from({ year: 2001, month: 1, day: 1, minute: 60 }, { overflow: 'constrain' });
  // => 2001-01-01T00:59:00

dt = Temporal.PlainDateTime.from({ year: 2001, month: 13, day: 1 }, { overflow: 'reject' });
  // => throws
dt = Temporal.PlainDateTime.from({ year: 2001, month: 1, day: 32 }, { overflow: 'reject' });
  // => throws
dt = Temporal.PlainDateTime.from({ year: 2001, month: 1, day: 1, hour: 25 }, { overflow: 'reject' });
  // => throws
dt = Temporal.PlainDateTime.from({ year: 2001, month: 1, day: 1, minute: 60 }, { overflow: 'reject' });
  // => throws
  
```
