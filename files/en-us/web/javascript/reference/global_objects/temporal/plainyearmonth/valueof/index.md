---
title: Temporal.PlainYearMonth.prototype.valueOf()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/valueOf
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

The **`valueOf()`** method overrides
{{jsxref('Object/valueOf','Object.prototype.valueOf')}} and
**always** throws an exception.This is because it's not possible to compare
{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}
objects with the relational operators `<`, `>=`, `>`, or `>=`. Use
{{jsxref('Temporal/PlainYearMonth/compare','Temporal.PlainYearMonth.compare()')}}
for this, or
{{jsxref('Temporal/PlainYearMonth/equals','Temporal.PlainYearMonth.equals()')}}
for equality.

## Syntax

```js
valueOf()
```

### Parameters

None.

### Return value

An exception.
