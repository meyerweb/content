---
title: Temporal.ZonedDateTime.prototype.second
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/second
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>second</code></strong> read-only property returns a number that identifies the second component of the <code>Temporal.ZonedDateTime</code> object.</span> The number is an integer in the range 0 through 59, inclusive. If <code>60</code> (for a leap second) was provided to <code>from()</code> or <code>with()</code>, <code>59</code> is stored and will be returned by this property.</p>

## Syntax

```js
datetime.second
```

### Value

An integer representing the second component.

## Examples

```js
dt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30.000003500');
dt.second;      // => 30
```
