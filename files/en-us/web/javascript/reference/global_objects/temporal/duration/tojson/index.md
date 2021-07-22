---
title: Temporal.Duration.prototype.toJSON()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/toJSON
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`toJSON()`** method returns a string representing the length of the
duration in ISO 8601 format.This method provides a useful value when a
{{jsxref('Temporal.Duration','Temporal.Duration')}} object is
passed to {{jsxref('JSON.stringify','JSON.stringify()')}}. It
is rarely useful in any other context.

The reverse operation, recovering a
{{jsxref('Temporal/Duration','Temporal.Duration')}} object from
a string, is accomplished by using
{{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}},
but that method cannot be called automatically by
{{jsxref('JSON.parse','JSON.parse()')}}. If you need to rebuild a
{{jsxref('Temporal/Duration','Temporal.Duration')}} object from
a JSON string, then you need to know the names of the keys that should be
interpreted as
{{jsxref('Temporal/Duration','Temporal.Duration')}} properties.
In that case, you can build a custom "reviver" function for your use case.

> **Warning:** If any of `duration.milliseconds`, `duration.microseconds`, or
> `duration.nanoseconds` are over 999, then deserializing from the result of
> `duration.toJSON()` will yield an equal but different object.

## Syntax

```js
calendar.toJSON()
```

### Parameters

None.

### Return value

A string representing the year and month in ISO 8601 format.

## Examples

```js
const ban = {
  reason: 'cooldown',
  banDuration: Temporal.Duration.from({ hours: 48 })
};
const str = JSON.stringify(ban, null, 2);
console.log(str);
// =>
// {
//   "reason": "cooldown",
//   "banDuration": "PT48H"
// }

// To rebuild from the string:
function reviver(key, value) {
  if (key.endsWith('Duration')) return Temporal.Duration.from(value);
  return value;
}
JSON.parse(str, reviver);
```
