---
title: Temporal.PlainDateTime.prototype.microsecond
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/microsecond
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>microsecond</code></strong> read-only property returns a number that identifies the microsecond component of the <code>PlainDateTime</code> object.</span></p>

## Syntax

```js
datetime.microsecond
```

### Value

An integer representing the microsecond component.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dt.microsecond; // => 3
```
