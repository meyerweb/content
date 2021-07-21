---
title: Temporal.PlainTime.from()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/from
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

The **`from()`** static method creates a new
{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}} object
from another value.

## Syntax

```js
from(time)
from(time, options)
```

### Parameters

- `time`

  - : A representation of the desired time. If the value is another
    {{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}
    object, a new object representing the same time is returned. If the value is
    any other object, a
    {{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}
    will be constructed from the values of any `hour`, `minute`, `second`,
    `millisecond`, `microsecond`, and `nanosecond` properties that are present.
    Any missing values are assumed to be `0`. If the `calendar` property is
    present, it must be the ISO 8601 calendar or the string `iso8601`.

    Any non-object value will be converted to a string, which is expected to be
    in ISO 8601 format. If the string designates a date or a time zone, they
    will be ignored.

- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new `Temporal.PlainTime` object. These are:
    - `overflow`
      - : Determines how out-of-range values in _time_ are handled. There are
        two options:
        - `'constrain'` (default)
          - : Out-of-range values are clamped to the nearest in-range value.
        - `'reject'` \* : Out-of-range values will cause the function to throw a
          `RangeError`.
          > **Note:** If the _time_ value is a string, `overflow` is ignored.

> **Warning:** Although Temporal does not deal with leap seconds, times coming
> from other software may have a `second` value of `60`. In the default
> `constrain` mode, this will be converted to `59`. In `reject` mode, the
> constructor will throw, so if you have to interoperate with times that may
> contain leap seconds, don't use `reject`. However, if parsing an ISO 8601
> string with a seconds component of `:60`, then it will always result in a
> `second` value of `59`, in accordance with POSIX.

### Return value

A new {{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}
object.

## Examples

```js
time = Temporal.PlainTime.from('03:24:30'); // => 03:24:30
time = Temporal.PlainTime.from('1995-12-07T03:24:30'); // => 03:24:30
time = Temporal.PlainTime.from('1995-12-07T03:24:30Z'); // => 03:24:30
time = Temporal.PlainTime.from('1995-12-07T03:24:30+01:00[Europe/Brussels]');
  // => 03:24:30
  // (same as above; time zone is ignored)
time === Temporal.PlainTime.from(time); // => false

time = Temporal.PlainTime.from({
  hour: 19,
  minute: 39,
  second: 9,
  millisecond: 68,
  microsecond: 346,
  nanosecond: 205
}); // => 19:39:09.068346205
time = Temporal.PlainTime.from({ hour: 19, minute: 39, second: 9 }); // => 19:39:09
time = Temporal.PlainTime.from(Temporal.PlainDateTime.from('2020-02-15T19:39:09'));
  // => 19:39:09
  // (same as above; Temporal.PlainDateTime has hour, minute, etc. properties)

// Different overflow modes
time = Temporal.PlainTime.from({ hour: 15, minute: 60 }, { overflow: 'constrain' });
  // => 15:59:00
time = Temporal.PlainTime.from({ hour: 15, minute: -1 }, { overflow: 'constrain' });
  // => 15:00:00
time = Temporal.PlainTime.from({ hour: 15, minute: 60 }, { overflow: 'reject' });
  // => throws
time = Temporal.PlainTime.from({ hour: 15, minute: -1 }, { overflow: 'reject' });
  // => throws
  
```
