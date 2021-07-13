---
title: Temporal.ZonedDateTime.prototype.toInstant()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/toInstant
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toInstant()</code></strong> method returns a new <code>{{jsxref('Temporal.Instant','Temporal.Instant')}}</code> object that corresponds to the exact date and time of the <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> object.</span></p>

## Syntax

```js
toInstant()
```

### Parameters

None.

### Return value

A new `{{jsxref('Temporal/Instant','Temporal.Instant')}}` object.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30+02:00[Africa/Johannesburg]');
zdt.toInstant(); // => 1995-12-07T01:24:30Z
```
