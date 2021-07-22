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

Returns a string containing the value of the calendar's
{{jsxref('Temporal/Calendar/id','id')}} property.This method
overrides
{{jsxref('Global_Objects/Object/toString','Object.prototype.toString()')}}
on {{jsxref('Temporal.Calendar','Temporal.Calendar')}} objects.

## Syntax

```js
toString()
```

### Return value

A string representing the calendar's
{{jsxref('Temporal/Calendar/id','ID','','nocode')}}.

## Examples

```js
var newcal = Temporal.Calendar.from('gregory');
newcal.toString(); // => "gregory"
```
