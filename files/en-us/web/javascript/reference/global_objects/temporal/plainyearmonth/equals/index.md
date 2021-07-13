---
title: Temporal.PlainYearMonth.prototype.equals()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/equals
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

<p class="summary"><span class="seoSummary">This method determines whether a <code>{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}</code> object is exactly the same as another year-month combination.</span></p>

This function exists because it's not possible to compare using
`yearMonth == other` or `yearMonth === other`, due to ambiguity in the primitive
representation and between Temporal types.

## Syntax

```js
equals(other)
```

### Parameters

- `other`
  - : Another month to compare. Either a
    `{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}`
    object, or a value that can be converted to one as if passed to
    `{{jsxref('Temporal/PlainYearMonth.from()','Temporal.PlainYearMonth.from()')}}`.

### Return value

A boolean `true` if `PlainYearMonth` and `other` are equal; otherwise, `false`.
If you also need to know the order in which the two months occur when they are
not equal, use
`{{jsxref('Temporal/PlainYearMonth/compare','Temporal.PlainYearMonth.compare()')}}`
instead.

<div class="note"><strong>Note:</strong> this function will always return <code>false</code> if the two <code>{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}</code> objects have different {{jsxref('Temporal.PlainYearMonth/calendar','calendar')}} properties, even if the actual years and months are equal.</div>

## Examples

```js
ym = Temporal.PlainYearMonth.from('2019-06');
other = Temporal.PlainYearMonth.from('2006-08');
ym.equals(other); // => false
ym.equals(ym); // => true
```
