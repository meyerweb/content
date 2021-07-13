---
title: Temporal.TimeZone.prototype.toString()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/TimeZone/toString
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

<p class="summary"><span class="seoSummary">The <strong><code>toString()</code></strong> method returns the time zone's ID as a string.</span> This method overrides <code>Object.prototype.toString()</code> and returns the same string as the time zone's <code>{{jsxref('Temporal/TimeZone/id','id')}}</code> property.</p>

## Syntax

```js
toString()
```

### Parameters

None.

### Return value

The string given by
`{{jsxref('Temporal/TimeZone/id','timeZone.id')}}`.

## Examples

```js
var tz = Temporal.TimeZone.from('Pacific/Rarotonga');
tz.toString();  // => "Pacific/Rarotonga"
```
