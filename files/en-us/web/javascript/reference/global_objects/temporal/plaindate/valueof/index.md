---
title: Temporal.PlainDate.prototype.valueOf()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/valueOf
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
{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}} objects
with the relational operators `<`, `>=`, `>`, or `>=`. Use
{{jsxref('Temporal/PlainDate/compare','Temporal.PlainDate.compare()')}}
for this, or
{{jsxref('Temporal/PlainDate/equals','Temporal.PlainDate.equals()')}}
for equality.

## Syntax

```js
valueOf()
```

### Parameters

None.

### Return value

An exception.
