---
title: Temporal.Instant.prototype.toJSON()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/toJSON
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`toJSON()`** method returns a string representing the date and time in ISO
8601 format.This method provides a useful value when a
{{jsxref('Temporal.Instant','Temporal.Instant')}} object is
passed to {{jsxref('JSON.stringify','JSON.stringify()')}}. It
is rarely useful in any other context.

The reverse operation, recovering a
{{jsxref('Temporal/Instant','Temporal.Instant')}} object from a
string, is accomplished by using
{{jsxref('Temporal/Instant/from','Temporal.Instant.from()')}},
but that method cannot be called automatically by
{{jsxref('JSON.parse','JSON.parse()')}}. If you need to rebuild a
{{jsxref('Temporal/Instant','Temporal.Instant')}} object from a
JSON string, then you need to know the names of the keys that should be
interpreted as {{jsxref('Temporal/Instant','Temporal.Instant')}}
properties. In that case, you can build a custom "reviver" function for your use
case.

## Syntax

```js
toJSON()
```

### Parameters

None.

### Return value

A string representing the date and time in ISO 8601 format.

## Examples

```js
const meeting = {
  id: 355,
  name: 'Budget review',
  location: 'https://meet.jit.si/ObjectiveTomatoesJokeSurely',
  startInstant: Temporal.Instant.from('2020-03-30T15:00-04:00[America/New_York]'),
  endInstant: Temporal.Instant.from('2020-03-30T16:00-04:00[America/New_York]')
};
const str = JSON.stringify(meeting, null, 2);
console.log(str);
// =>
// {
//   "id": 355,
//   "name": "Budget review",
//   "location": "https://meet.jit.si/ObjectiveTomatoesJokeSurely",
//   "startInstant": "2020-03-30T19:00Z",
//   "endInstant": "2020-03-30T20:00Z"
// }

// To rebuild from the string:
function reviver(key, value) {
  if (key.endsWith('Instant')) return Temporal.Instant.from(value);
  return value;
}
JSON.parse(str, reviver);
```
