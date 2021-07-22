---
title: Temporal.PlainTime.prototype.toJSON()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/toJSON
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`toJSON()`** method returns a string representing the wall-clock time in
ISO 8601 format.This method provides a useful value when a
{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}} object
is passed to {{jsxref('JSON.stringify','JSON.stringify()')}}.
It is rarely useful in any other context.

The reverse operation, recovering a
{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}} object
from a string, is accomplished by using
{{jsxref('Temporal/PlainTime/from','Temporal.PlainTime.from()')}},
but that method cannot be called automatically by
{{jsxref('JSON.parse','JSON.parse()')}}. If you need to rebuild a
{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}} object
from a JSON string, then you need to know the names of the keys that should be
interpreted as
{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}
properties. In that case, you can build a custom "reviver" function for your use
case.

## Syntax

```js
toJSON()
```

### Parameters

None.

### Return value

A string representing the year and month in ISO 8601 format.

## Examples

```js
const workBreak = {
  type: 'mandatory',
  name: 'Lunch',
  startTime: Temporal.PlainTime.from({ hour: 12 }),
  endTime: Temporal.PlainTime.from({ hour: 13 })
};
const str = JSON.stringify(workBreak, null, 2);
console.log(str);
// =>
// {
//   "type": "mandatory",
//   "name": "Lunch",
//   "startTime": "12:00",
//   "endTime": "13:00"
// }

// To rebuild from the string:
function reviver(key, value) {
  if (key.endsWith('Time')) return Temporal.PlainTime.from(value);
  return value;
}
JSON.parse(str, reviver);
```
