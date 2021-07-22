---
title: Temporal.PlainMonthDay.prototype.toJSON()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainMonthDay/toJSON
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

Returns a string representing the month and day in ISO 8601 format.This method
provides a useful value when a
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}
object is passed to
{{jsxref('JSON.stringify','JSON.stringify()')}}. It is rarely
useful in any other context. If you simply need to serialize the month and day
to an ISO 8601 string, use
{{jsxref('Temporal/PlainMonthDay/toString','Temporal.PlainMonthDay.toString()')}}
instead.

The reverse operation, recovering a
{{jsxref('Temporal/PlainMonthDay','Temporal.PlainMonthDay')}}
object from a string, is accomplished by using
{{jsxref('Temporal/PlainMonthDay/from','Temporal.PlainMonthDay.from()')}},
but that method cannot be called automatically by
{{jsxref('JSON.parse','JSON.parse()')}}. If you need to rebuild a
{{jsxref('Temporal/PlainMonthDay','Temporal.PlainMonthDay')}}
object from a JSON string, then you need to know the names of the keys that
should be interpreted as
{{jsxref('Temporal/PlainMonthDay','Temporal.PlainMonthDay')}}
properties. In that case, you can build a custom "reviver" function for your use
case.

## Syntax

```js
toJSON()
```

### Parameters

None.

### Return value

A string representing the month and day in ISO 8601 format.

## Examples

```js
const holiday = {
  name: 'Canada Day',
  holidayMonthDay: Temporal.PlainMonthDay.from({ monthCode: 'M07', day: 1 })
};
const str = JSON.stringify(holiday, null, 2);
console.log(str);
// =>
// {
//   "name": "Canada Day",
//   "holidayMonthDay": "07-01"
// }

// To rebuild from the string:
function reviver(key, value) {
  if (key.endsWith('MonthDay')) return Temporal.PlainMonthDay.from(value);
  return value;
}
JSON.parse(str, reviver);
```
