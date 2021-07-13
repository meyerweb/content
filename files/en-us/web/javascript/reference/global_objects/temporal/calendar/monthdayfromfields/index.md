---
title: Temporal.Calendar.prototype.monthDayFromFields()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/monthDayFromFields
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>monthDayFromFields()</code></strong> method returns a new <code>{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}</code> object determined by the field values passed to it.</span> This method is called indirectly when using the
<code>{{jsxref('Temporal.PlainYearMonth','Temporal.PlainMonthDay.from()')}}</code> method, and it is rare for developers to need to call <code>Temporal.Calendar.monthDayFromFields()</code> directly.</p>

## Syntax

```js
monthDayFromFields(fields);
monthDayFromFields(fields, options);
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
`{{jsxref('Temporal/PlainMonthDay','Temporal.PlainMonthDay')}}`
object representing the new year and month.

## Examples

```js
date = Temporal.Calendar.from('iso8601').monthDayFromFields(
  { year: 2021, month: 4, day: 20 }
);
date.year; // => undefined
date.month; // => undefined
date.monthCode; // => 'M04'
date.day; // => 20
date.dayOfWeek; // => undefined
```

```js
date = Temporal.Calendar.from('iso8601').monthDayFromFields(
  { monthCode: 'M04', day: 20 }
);
date.year; // => undefined
date.month; // => undefined
date.monthCode; // => 'M04'
date.day; // => 20
date.dayOfWeek; // => undefined
```

```js
date = Temporal.Calendar.from('hebrew').monthDayFromFields(
  { year: 5779, month: 6, day: 18 }
);
date.year; // => undefined
date.monthCode; // => 'M05L'
date.day; // => 18
```
