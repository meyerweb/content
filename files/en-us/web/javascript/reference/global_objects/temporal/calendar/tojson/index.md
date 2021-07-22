---
title: Temporal.Calendar.prototype.toJSON()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/toJSON
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

Returns a string containing the value of the calendar's
{{jsxref('Temporal/Calendar/id','id')}} property.This method
provides a useful value when a
{{jsxref('Temporal.Calendar','Temporal.Calendar')}} object is
passed to {{jsxref('JSON.stringify','JSON.stringify()')}}. It
is rarely useful in any other context. If you simply need a string containing
the calendar's ID, use
{{jsxref('Temporal/Calendar/toString','Temporal.Calendar.toString()')}}
instead.

The reverse operation, recovering a
{{jsxref('Temporal/Calendar','Temporal.Calendar')}} object from
a string, is accomplished by using
{{jsxref('Temporal/Calendar/from','Temporal.Calendar.from()')}},
but that method cannot be called automatically by
{{jsxref('JSON.parse','JSON.parse()')}}. If you need to rebuild a
{{jsxref('Temporal/Calendar','Temporal.Calendar')}} object from
a JSON string, then you need to know the names of the keys that should be
interpreted as
{{jsxref('Temporal/Calendar','Temporal.Calendar')}} properties.
In that case, you can build a custom "reviver" function for your use case.

## Syntax

```js
toJSON()
```

### Return value

A string representing the calendar's
{{jsxref('Temporal/Calendar/id','ID','','nocode')}}.

## Examples

```js
var newcal = Temporal.Calendar.from('gregory');
newcal.toJSON(); // => 'gregory'
```
