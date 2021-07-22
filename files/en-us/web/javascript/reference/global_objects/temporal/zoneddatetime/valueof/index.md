---
title: Temporal.ZonedDateTime.prototype.valueOf()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/valueOf
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
{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
objects with the relational operators `<`, `>=`, `>`, or `>=`. Use
{{jsxref('Temporal/ZonedDateTime/compare','Temporal.ZonedDateTime.compare()')}}
for this, or
{{jsxref('Temporal/ZonedDateTime/equals','Temporal.ZonedDateTime.equals()')}}
for equality.

## Syntax

```js
valueOf()
```

### Parameters

None.

### Return value

An exception.
