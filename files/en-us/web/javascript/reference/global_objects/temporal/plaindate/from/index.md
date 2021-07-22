---
title: Temporal.PlainDate.from()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/from
tags:
  - Class
  - JavaScript
  - date
---
{{JSRef}}

The **`from()`** static method creates a new
{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}} object
from another value.

## Syntax

```js
from(date)
from(date, options)
```

### Parameters

- `date`

  - : A representation of the desired date, either as an object or a string in
    valid ISO 8601 format. If the value is another
    {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
    object, a new object representing the same date is returned.

    If the value is any other object, it must contain, at a minimum:

    - A `year` or `eraYear` property.

      - If `eraYear` is used, an `era` must also be supplied.

    - Either a `month` or a `monthCode` property.
    - A `day` property. The object may also contain a `calendar` property. If
      omitted, the ISO 8601 calendar is used.

    Any non-object, non-string value will be converted to a string, which is
    expected to be in ISO 8601 format. For other calendars, the calendar is also
    parsed in addition to year and month. Any other parts of the string, such as
    those relating to time or time zone, are optional and will be ignored. If
    the string is invalid according to ISO 8601, then a `RangeError` will be
    thrown regardless of the value of the `overflow` option (see next).

- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new `Temporal.PlainDate` object. These are:
    - `overflow`
      - : Determines how out-of-range values in _date_ are handled. There are
        two options:
        - `'constrain'` (default)
          - : Out-of-range values are clamped to the nearest in-range value.
        - `'reject'` \* : Out-of-range values will cause the function to throw a
          `RangeError`.
          > **Note:** If _date_ is a string, the `overflow` property's value is
          > ignored.

### Return value

A new {{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}
object. If the result is earlier or later than the range of dates
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} can
represent (approximately half a million years centered on the Unix epoch), this
function will throw a `RangeError` regardless of the value of `overflow`.

## Examples

```js
date = Temporal.PlainDate.from('2006-08-24'); // => 2006-08-24
date = Temporal.PlainDate.from('2006-08-24T15:43:27'); // => 2006-08-24
date = Temporal.PlainDate.from('2006-08-24T15:43:27Z'); // => 2006-08-24
date = Temporal.PlainDate.from('2006-08-24T15:43:27+01:00[Europe/Brussels]');
  // => 2006-08-24
date === Temporal.PlainDate.from(date); // => false

date = Temporal.PlainDate.from({year: 2006, month: 8, day: 24}); // => 2006-08-24
date = Temporal.PlainDate.from(Temporal.PlainDateTime.from('2006-08-24T15:43:27'));
  // => 2006-08-24
  // same as above; Temporal.PlainDateTime has year, month, and day properties

calendar = Temporal.Calendar.from('islamic');
date = Temporal.PlainDate.from({ year: 1427, month: 8, day: 1, calendar }); // => 2006-08-24[u-ca=islamic]
date = Temporal.PlainDate.from({ year: 1427, month: 8, day: 1, calendar: 'islamic' });
  // => 2006-08-24[u-ca=islamic]
  // same as above

// Different overflow modes
date = Temporal.PlainDate.from({ year: 2001, month: 13, day: 1 }, { overflow: 'constrain' });
  // => 2001-12-01
date = Temporal.PlainDate.from({ year: 2001, month: 1, day: 32 }, { overflow: 'constrain' });
  // => 2001-01-31
date = Temporal.PlainDate.from({ year: 2001, month: 13, day: 1 }, { overflow: 'reject' });
  // => throws
date = Temporal.PlainDate.from({ year: 2001, month: 1, day: 32 }, { overflow: 'reject' });
  // => throws
```
