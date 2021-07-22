---
title: Temporal.Instant.prototype.valueOf()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/valueOf
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
{{jsxref('Temporal/Instant','Temporal.Instant')}} objects with
the relational operators `<`, `>=`, `>`, or `>=`. Use
{{jsxref('Temporal/Instant/compare','Temporal.Instant.compare()')}}
for this, or
{{jsxref('Temporal/instant/equals','Temporal.instant.equals()')}}
for equality.

## Syntax

```js
valueOf()
```

### Parameters

None.

### Return value

An exception.
