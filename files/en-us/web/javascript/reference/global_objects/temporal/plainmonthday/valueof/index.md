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

<p class="summary"><span class="seoSummary">The <strong><code>valueOf()</code></strong> method overrides <code>{{jsxref('Object/valueOf','Object.prototype.valueOf()')}}</code> and <strong>always</strong> throws an exception.</span> This method exists because it's not possible to compare <code>{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}</code> objects with the relational operators <code>&#x3C;</code>, <code>&#x3C;=</code>, <code>></code>, or <code>>=</code>. Instead, use <code>{{jsxref('Temporal/PlainMonthDay/equals','Temporal.PlainMonthDay.equals()')}}</code> to check for equality.</p>

## Syntax

```js
valueOf()
```

### Parameters

None.

### Return value

An exception.
