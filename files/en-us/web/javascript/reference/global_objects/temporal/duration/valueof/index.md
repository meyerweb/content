---
title: Temporal.Duration.prototype.valueOf()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/valueOf
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
{{jsxref('Temporal/Duration','Temporal.Duration')}} objects
with the relational operators `<`, `>=`, `>`, or `>=`.

## Syntax

```js
valueOf()
```

### Parameters

None.

### Return value

An exception.
