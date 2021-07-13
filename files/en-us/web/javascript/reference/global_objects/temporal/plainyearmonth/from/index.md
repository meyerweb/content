---
title: Temporal.PlainYearMonth.from()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/from
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - Time Zone
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>from()</code></strong> static method creates a new <code>{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}</code> object from another value.</span></p>

## Syntax

```js
from(value)
from(value, options)
```

### Parameters

- `value`

  - : A representation of the desired year and month. This can be represented in
    a number of ways:

    - A
      `{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}`
      object.
    - A
      `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
      object.
    - A
      `{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`
      object.
    - A
      `{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
      object.
    - An object that contains, at a minimum:

      - A `year` or `eraYear` property.

        - If `eraYear` is used, an `era` must also be supplied.

      - Either a `month` or a `monthCode` property.

      The object may also contain a `calendar` property. If omitted, the ISO
      8601 calendar is used.

    - A string in valid ISO 8601 format. Any non-object, non-string value will
      be converted to a string, which is expected to be in ISO 8601 format. For
      the ISO 8601 calendar, only the year and month will be parsed from the
      string. For other calendars, the calendar is also parsed in addition to
      year and month. Any other parts of the string are optional and will be
      ignored. If the string is invalid according to ISO 8601, then a
      `RangeError` will be thrown regardless of the value of the `overflow`
      option (see next).

- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new `Temporal.PlainYearMonth` object. These are:
    - `overflow`
      - : Determines how out-of-range values in _value_ are handled. There are
        two options:
        - `'constrain'` (default)
          - : Out-of-range values are clamped to the nearest in-range value.
        - `'reject'`
          - : Out-of-range values will cause the function to throw a
            `RangeError`.

### Return value

A new
`{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}`
object.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2019-06'); // => 2019-06
ym = Temporal.PlainYearMonth.from('2019-06-24'); // => 2019-06
ym = Temporal.PlainYearMonth.from('2019-06-24T15:43:27'); // => 2019-06
ym = Temporal.PlainYearMonth.from('2019-06-24T15:43:27Z'); // => 2019-06
ym = Temporal.PlainYearMonth.from('2019-06-24T15:43:27+01:00[Europe/Brussels]'); // => 2019-06
ym === Temporal.PlainYearMonth.from(ym); // => false

ym = Temporal.PlainYearMonth.from({ year: 2019, month: 6 }); // => 2019-06
ym = Temporal.PlainYearMonth.from(Temporal.PlainDate.from('2019-06-24')); // => 2019-06
  // (same as above; Temporal.PlainDate has year and month properties)

// Different overflow modes
ym = Temporal.PlainYearMonth.from({ year: 2001, month: 13 }, { overflow: 'constrain' });
  // => 2001-12
ym = Temporal.PlainYearMonth.from({ year: 2001, month: 13 }, { overflow: 'reject' });
  // => throws
  
```
