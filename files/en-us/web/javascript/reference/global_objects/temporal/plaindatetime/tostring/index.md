---
title: Temporal.PlainDateTime.prototype.toString()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/toString
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toString()</code></strong> method returns a string representing the date and time in ISO 8601 format.</span> This method overrides the <code>{{jsxref('Object.toString','Object.prototype.toString()')}}</code> method and provides a convenient, unambiguous string representation of a date and time. The string can be passed to <code>{{jsxref('Temporal.PlainDateTime/from','Temporal.PlainDateTime.from()')}}</code> to create a new <code>{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}</code> object.</p>

## Syntax

```js
toString()
toString(options)
```

### Parameters

- `options` {{optional_inline}}

  - : An object with properties influencing the formatting. The following
    options are recognized:

    - `calendarName`
      - : Whether to show the calendar annotation in the return value. Valid
        values are `"auto"`, `"always"`, and `"never"`. The default is `"auto"`.
        <div class="note"><p>Normally, a calendar annotation is shown when the <code>PlainDateTime</code>'s calendar is not the ISO 8601 calendar. By setting the <code>calendarName</code> option to <code>"always"</code> or <code>"never"</code>, this can be overridden to always or never show the annotation, respectively.</p></div>
    - `fractionalSecondDigits`
      - : An single-digit integer or the string `'auto'` defining how many
        digits to print after the decimal point in the output string. The
        default is `'auto'`, which omits any trailing zeroes after the decimal
        point.
    - `smallestUnit`
      - : A string defining the smallest unit of time to include in the output
        string. Valid values are:
        - `'minute'`
        - `'second'`
        - `'millisecond'`
        - `'microsecond'`
        - `'nanosecond'`
        <div class="note"><p>If <code>smallestUnit</code> is defined, it overrides the value of <code>fractionalSecondDigits</code>.</p></div>
    - `roundingMode`

      - : A string defining how to deal with any remainder. The valid values
        are:

        - `'ceil'`
          - : Always round up, toward 23:59:59.999999999.
        - `'floor'`

          `'trunc'`

          - : Always round down, toward 00:00. These two rounding modes behave
            identically, but are included for consistency with
            `{{jsxref('Temporal/Duration.round()','Temporal.Duration.round()')}}`,
            where they do **not** behave identically.

        - `'halfExpand'` (default)
          - : Round to the nearest of the values allowed by `roundingIncrement`
            and `smallestUnit`. If there is a tie, round up, toward
            23:59:59.999999999.

### Return value

A string representing the date and time in ISO 8601 format.

## Examples

```js
dt = Temporal.PlainDateTime.from({
  year: 1999,
  month: 12,
  day: 31,
  hour: 23,
  minute: 59,
  second: 59,
  millisecond: 999,
  microsecond: 999,
  nanosecond: 999
});
dt.toString(); // => '1999-12-31T23:59:59.999999999'

dt.toString({ smallestUnit: 'minute' });    // => '1999-12-31T23:59'
dt.toString({ fractionalSecondDigits: 0 }); // => '1999-12-31T23:59:59'
dt.toString({ fractionalSecondDigits: 4 }); // => '1999-12-31T23:59:59.9999'
dt.toString({ fractionalSecondDigits: 8, roundingMode: 'halfExpand' });
// => '2000-01-01T00:00:00.00000000'
```
