---
title: Temporal.Instant.prototype.toString()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/toString
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toString()</code></strong> method returns a string representing the date and time in ISO 8601 format.</span> This method overrides the <code>{{jsxref('Object.toString','Object.prototype.toString()')}}</code> method and provides a convenient, unambiguous string representation of a date and time. The string can be passed to <code>{{jsxref('Temporal.Instant/from','Temporal.Instant.from()')}}</code> to create a new <code>{{jsxref('Temporal.Instant','Temporal.Instant')}}</code> object.</p>

## Syntax

```js
toString();
toString(options)
```

### Parameters

- `options` {{optional_inline}}

  - : An object with properties influencing the formatting. The following
    options are recognized:

    - `timeZone`
      - : The time zone in which to express the instant. This can be a
        \`Temporal.TimeZone\` object, an object implementing the Temporal time
        zone protocol, or a string. The default is to use UTC. If a time zone
        other than UTC is supplied, the string will be the date and time in the
        given time zone, and include the time zone's UTC offset.
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

A string expressing the instant as a date and time.

## Examples

```js
instant = Temporal.Instant.fromEpochMilliseconds(1574074321816);
instant.toString(); // => '2019-11-18T10:52:01.816Z'
instant.toString({ timeZone: Temporal.TimeZone.from('UTC') });
// => '2019-11-18T10:52:01.816+00:00'
instant.toString({ timeZone: 'Asia/Seoul' });
// => '2019-11-18T19:52:01.816+09:00'

instant.toString({ smallestUnit: 'minute' });
// => '2019-11-18T10:52Z'
instant.toString({ fractionalSecondDigits: 0 });
// => '2019-11-18T10:52:01Z'
instant.toString({ fractionalSecondDigits: 4 });
// => '2019-11-18T10:52:01.8160Z'
instant.toString({ smallestUnit: 'second', roundingMode: 'halfExpand' });
// => '2019-11-18T10:52:02Z'
```
