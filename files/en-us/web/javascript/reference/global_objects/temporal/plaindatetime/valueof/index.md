---
title: Temporal.PlainDateTime.prototype.valueOf()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/valueOf
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
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
objects with the relational operators `<`, `>=`, `>`, or `>=`. Use
{{jsxref('Temporal/PlainDateTime/compare','Temporal.PlainDateTime.compare()')}}
for this, or
{{jsxref('Temporal/PlainDateTime/equals','Temporal.PlainDateTime.equals()')}}
for equality.

## Syntax

```js
valueOf()
```

### Parameters

None.

### Return value

An exception.
