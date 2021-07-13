---
title: Temporal.PlainYearMonth.prototype.subtract()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/subtract
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

<p class="summary"><span class="seoSummary">The <strong><code>subtract()</code></strong> method creates a new <code>{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}</code> object by subtracting a duration from the <code>{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}</code>.</span> Subtracting a negative duration is equivalent to {{jsxref('Temporal.PlainYearMonth/add','adding')}} the absolute value of that duration.</p>

## Syntax

```js
subtract(duration)
subtract(duration, options)
```

### Parameters

- `duration`
  - : An object with properties denoting a duration, such as `{ months: 5 }`, or
    a string value such as `P5M`, or a
    `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object. If `duration` is not such a string nor a
    `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object, then it will be converted to one as if it were passed to
    `{{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}`.
- `options` {{optional_inline}}

  - : An object containing properties that represent options for constructing
    the new `Temporal.PlainYearMonth` object. These are:

    - `overflow`
      - : Determines how out-of-range values in _duration_ are handled. There
        are two options:
        - `'constrain'` (default)
          - : Out-of-range values are clamped to the nearest in-range value.
        - `'reject'` \* : Out-of-range values will cause the function to throw a
        `RangeError`.
        <div class="note"><strong>Note:</strong> The <code>overflow</code> option has no effect in the default ISO calendar, because a year is always 12 months and therefore not ambiguous. However, <code>overflow</code> may have an effect in calendars where years can be different numbers of months.<p></p></div>

    ### Return value

    A new
    `{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}`
    object representing the year and month indicated by the original `oldMonth`
    minus `duration`. If the result is earlier or later than the range that
    `{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}`
    can represent (just over half a million years centered on the Unix epoch), a
    `RangeError` will be thrown instead.

    ## Examples

    ```js
        ym = Temporal.PlainYearMonth.from('2019-06');
        ym.subtract({ years: 20, months: 4 }); // => 1999-02
        ```
