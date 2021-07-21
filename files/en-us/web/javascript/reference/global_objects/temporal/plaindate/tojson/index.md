---
title: Temporal.PlainDate.prototype.toJSON()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/toJSON
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`toJSON()`** method returns a string representing the date in ISO 8601
format.This method provides a useful value when a
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} object
is passed to {{jsxref('JSON.stringify','JSON.stringify()')}}.
It is rarely useful in any other context.

The reverse operation, recovering a
{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}} object
from a string, is accomplished by using
{{jsxref('Temporal/PlainDate/from','Temporal.PlainDate.from()')}},
but that method cannot be called automatically by
{{jsxref('JSON.parse','JSON.parse()')}}. If you need to rebuild a
{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}} object
from a JSON string, then you need to know the names of the keys that should be
interpreted as
{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}
properties. In that case, you can build a custom "reviver" function for your use
case.

## Syntax

```js
toJSON()
```

### Parameters

None.

### Return value

A string representing the date in ISO 8601 format.

## Examples

```js
const student = {
  id: 429,
  name: 'Emilia Connor',
  birthDate: Temporal.PlainDate.from('1997-09-08')
};
const str = JSON.stringify(student, null, 2);
console.log(str);
// =>
// {
//   "id": 429,
//   "name": "Emilia Connor",
//   "birthDate": "1997-09-08"
// }

// To rebuild from the string:
function reviver(key, value) {
  if (key.endsWith('Date')) return Temporal.PlainDate.from(value);
  return value;
}
JSON.parse(str, reviver);
```
