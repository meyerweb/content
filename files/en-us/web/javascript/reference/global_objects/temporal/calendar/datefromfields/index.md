---
title: Temporal.Calendar.prototype.dateFromFields()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/dateFromFields
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>dateFromFields()</code></strong> method returns a new <code>{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}</code> object determined by the field values passed to it.</span> This method is called indirectly when using
<code>{{jsxref('Temporal/PlainDate/from','Temporal.PlainDate.from()')}}</code> method. It is rare for developers to need to call <code>Temporal.Calendar.dateFromFields()</code> directly.</p>

## Syntax

```js
dateFromFields(fields);
dateFromFields(fields, options);
```

### Parameters

- `fields`
  - : An object containing fields that help identify the date to be constructed.
    These vary by calendar system; for example, the ISO 8601 calendar accepts
    `year`, `month`, `monthCode`, and `day` fields. The Gregorian calendar
    accepts the same fields, and adds the `era` and `eraYear` fields. Other
    calendars may accept some, all, or none of those. Some fields may be
    required, and others optional. In general, see introductory note on how
    developers should rarely, if ever, call this method directly.
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

A new `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
object representing the new date.

## Examples

```js
date = Temporal.Calendar.from('iso8601').dateFromFields(
  { year: 2021, month: 4, day: 20 }
);
date.year; // => 2021
date.month; // => 4
date.monthCode; // => 'M04'
date.day; // => 20
date.dayOfWeek; // => 2
date.era; // => undefined
date.eraYear; // => undefined
```

```js
date = Temporal.Calendar.from('gregory').dateFromFields(
  { year: 2021, month: 4, day: 37 },
  { overflow: 'constrain' }
);
date.year; // => 2021
date.month; // => 4
date.monthCode; // => 'M04'
date.day; // => 30
date.dayOfWeek; // => 5
date.era; // => 'ce'
date.eraYear; // => 2021
```

```js
date = Temporal.Calendar.from('hebrew').dateFromFields(
  { year: 5779, month: 6, day: 18 }
);
date.year; // => 5779
date.month; // => 6
date.monthCode; // => 'M05L'
date.day; // => 18
```
