---
title: Temporal.Calendar.prototype.yearMonthFromFields()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/yearMonthFromFields
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>yearMonthFromFields()</code></strong> method returns a new <code>{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}</code> object determined by the field values passed to it.</span> This method is called indirectly when using the
<code>{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth.from()')}}</code> method, and it is rare for developers to need to call <code>Temporal.Calendar.yearMonthFromFields()</code> directly.</p>

## Syntax

```js
yearMonthFromFields(fields)
yearMonthFromFields(fields, options)
```

### Parameters

- `fields`
  - : An object containing fields that help identify the date to be constructed.
    Some fields may be required, some optional, and others ignored.
- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new Temporal object. These are:
    - `overflow`
      - : Determines how out-of-range values in _fields_ are handled. There are
        two options:
        - `'constrain'` (default)
          - : Out-of-range values are clamped to the nearest in-range value.
        - `'reject'`
          - : Out-of-range values will cause the function to throw a
            `RangeError`.

### Return value

A new
`{{jsxref('Temporal/plainYearMonth','Temporal.plainYearMonth')}}`
object representing the new year and month.

## Examples

```js
date = Temporal.Calendar.from('iso8601').yearMonthFromFields(
  { year: 2021, month: 4, day: 20 }
);
date.year; // => 2021
date.month; // => 4
date.monthCode; // => 'M04'
date.day; // => undefined
date.dayOfWeek; // => undefined
```

```js
date = Temporal.Calendar.from('gregory').yearMonthFromFields(
  { year: 2021, month: 15 },
  { overflow: 'constrain' }
);
date.year; // => 2021
date.month; // => 12
date.monthCode; // => 'M12'
date.era; // => 'ce'
date.eraYear; // => 2021
```

```js
date = Temporal.Calendar.from('hebrew').yearMonthFromFields(
  { year: 5779, month: 6 }
);
date.year; // => 5779
date.month; // => 6
date.monthCode; // => 'M05L'
```
