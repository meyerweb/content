---
title: Temporal.PlainMonthDay.prototype.valueOf()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainMonthDay/valueOf
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
{{jsxref('Object/valueOf','Object.prototype.valueOf()')}} and
**always** throws an exception.This method exists because it's not possible to
compare
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}
objects with the relational operators `<`, `<=`, `>`, or `>=`. Instead, use
{{jsxref('Temporal/PlainMonthDay/equals','Temporal.PlainMonthDay.equals()')}}
to check for equality.

## Syntax

```js
valueOf()
```

### Parameters

None.

### Return value

An exception.
