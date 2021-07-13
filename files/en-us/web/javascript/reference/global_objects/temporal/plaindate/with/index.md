---
title: Temporal.PlainDate.prototype.with()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/with
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>with()</code></strong> method returns a new <code>{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}</code> object which is a modification of the original object using new property values.</span></p>

## Syntax

```js
with(newValues)
with(newValues, options)
```

### Parameters

- `newValues`
  - : An object containing some or all of the properties accepted by
    `{{jsxref('Temporal/PlainDate/from','Temporal.PlainDate.from()')}}`.
    <div class="note"><strong>Note:</strong> <code>calendar</code> and <code>timeZone</code> properties are not allowed on <var>newValues</var>. See the methods <code>{{jsxref('Temporal/PlainDate/withCalendar','withCalendar()')}}</code> and <code>{{jsxref('Temporal/PlainDate/toZonedDateTime','toZonedDateTime()')}}</code>.<p></p></div>
- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new `Temporal.PlainDate` object. These are:
    - `overflow`
      - : Determines how out-of-range values in _newValues_ are handled. There
        are two options:
        - `'constrain'` (default)
          - : Out-of-range values are clamped to the nearest in-range value.
        - `'reject'`
          - : Out-of-range values will cause the function to throw a
            `RangeError`.

### Return value

A new `{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}`
object. If the result is earlier or later than the range of dates
`{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}` can
represent (approximately half a million years centered on the Unix epoch), this
method will throw a `RangeError` regardless of the value of `overflow`.

## Examples

```js
date = Temporal.PlainDate.from('2006-01-24');
// What's the first day of this month?
date.with({ day: 1 }); // => 2006-01-01
// What's the last day of the next month?
const nextMonthDate = date.add({ months: 1 });
nextMonthDate.with({ day: nextMonthDate.daysInMonth }); // => 2006-02-28
```
