---
title: Temporal.ZonedDateTime.prototype.toString()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/toString
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toString()</code></strong> method returns a string representing the date and time in ISO 8601 format.</span> This method overrides the <code>{{jsxref('Object.toString','Object.prototype.toString()')}}</code> method and provides a convenient, unambiguous string representation of a date and time. The string can be passed to <code>{{jsxref('Temporal.ZonedDateTime/from','Temporal.ZonedDateTime.from()')}}</code> to create a new <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> object.</p>

## Syntax

```js
toString()
toString(options)
```

### Parameters

- `options` {{optional_inline}}

  - : An object with properties influencing the formatting. The following
    options are recognized:

    - `offset`
      - : Whether to show the time zone offset in the return value. Valid values
        are `'auto'` and `'never'`. The default is `'auto'`.
    - `timeZoneName`
      - : Whether to show the time zone name annotation in the return value.
        Valid values are `'auto'` and `'never'`. The default is `'auto'`.
    - `calendarName`
      - : Whether to show the calendar annotation in the return value. Valid
        values are `'auto'`, `'always'`, and `'never'`. The default is `'auto'`.
        <div class="note"><p>Normally, a calendar annotation is shown when the <code>ZonedDateTime</code>'s calendar is not the ISO 8601 calendar. By setting the <code>calendarName</code> option to <code>'always'</code> or <code>'never'</code>, this can be overridden to always or never show the annotation, respectively.</p></div>
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

A string containing an ISO 8601 date+time+offset format, a bracketed time zone
suffix, and (if the calendar is not `iso8601`) a calendar suffix.

## Examples

```js
zdt = Temporal.ZonedDateTime.from({ year: 2019, month: 12, day: 1, hour: 12, timeZone: 'Africa/Lagos' });
zdt.toString(); // => '2019-12-01T12:00:00+01:00[Africa/Lagos]'
zdt = zdt.withCalendar('japanese');
zdt.toString(); // => '2019-12-01T12:00:00+01:00[Africa/Lagos][u-ca=japanese]'
```
