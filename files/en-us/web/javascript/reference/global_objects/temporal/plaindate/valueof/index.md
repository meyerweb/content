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

<p class="summary"><span class="seoSummary">The <strong><code>valueOf()</code></strong> method overrides {{jsxref('Object/valueOf','Object.prototype.valueOf')}} and <strong>always</strong> throws an exception.</span> This is because it's not possible to compare <code>{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}</code> objects with the relational operators <code>&#x3C;</code>, <code>>=</code>, <code>></code>, or <code>>=</code>. Use <code>{{jsxref('Temporal/PlainDate/compare','Temporal.PlainDate.compare()')}}</code> for this, or <code>{{jsxref('Temporal/PlainDate/equals','Temporal.PlainDate.equals()')}}</code> for equality.</p>

## Syntax

```js
valueOf()
```

### Parameters

None.

### Return value

An exception.
