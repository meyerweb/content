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

This method determines whether a
{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}
object is exactly the same as another year-month combination.

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
    {{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}
    object, or a value that can be converted to one as if passed to
    {{jsxref('Temporal/PlainYearMonth.from()','Temporal.PlainYearMonth.from()')}}.

### Return value

A boolean `true` if `PlainYearMonth` and `other` are equal; otherwise, `false`.
If you also need to know the order in which the two months occur when they are
not equal, use
{{jsxref('Temporal/PlainYearMonth/compare','Temporal.PlainYearMonth.compare()')}}
instead.

> **Note:** This function will always return `false` if the two
> {{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}
> objects have different
> {{jsxref('Temporal.PlainYearMonth/calendar','calendar','','nocode')}}
> properties, even if the actual years and months are equal.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2019-06');
other = Temporal.PlainYearMonth.from('2006-08');
ym.equals(other); // => false
ym.equals(ym); // => true
```
