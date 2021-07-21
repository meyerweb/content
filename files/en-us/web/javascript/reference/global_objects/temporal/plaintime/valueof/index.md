---
title: Temporal.PlainTime.prototype.valueOf()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/valueOf
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
{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}} objects
with the relational operators `<`, `>=`, `>`, or `>=`. Use
{{jsxref('Temporal/PlainTime/compare','Temporal.PlainTime.compare()')}}
for this, or
{{jsxref('Temporal/PlainTime/equals','Temporal.PlainTime.equals()')}}
for equality.

## Syntax

```js
valueOf()
```

### Parameters

None.

### Return value

An exception.
