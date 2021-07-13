---
title: Temporal.Calendar.prototype.toString()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/toString
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

<p class="summary"><span class="seoSummary">Returns a string containing the value of the calendar's <code>{{jsxref('Temporal/Calendar/id','id')}}</code> property.</span>
This method overrides <code>{{jsxref('Global_Objects/Object/toString','Object.prototype.toString()')}}</code> on <code>{{jsxref('Temporal.Calendar','Temporal.Calendar')}}</code> objects.</p>

## Syntax

```js
toString()
```

### Return value

A string representing the calendar's
{{jsxref('Temporal/Calendar/id','ID')}}.

## Examples

```js
var newcal = Temporal.Calendar.from('gregory');
newcal.toString(); // => "gregory"
```
