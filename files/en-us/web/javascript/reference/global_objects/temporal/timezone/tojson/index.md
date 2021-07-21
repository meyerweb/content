---
title: Temporal.TimeZone.prototype.toJSON()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/TimeZone/toJSON
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

The **`toJSON()`** method returns the time zone's ID as a string.It is usually
not called directly, but it can be called automatically by `JSON.stringify()`.
The reverse operation, recovering a
{{jsxref('Temporal/TimeZone','Temporal.TimeZone')}} object from
a string, is
{{jsxref('Temporal/TimeZone/from','Temporal.TimeZone.from()')}},
but it cannot be called automatically by `JSON.parse()`.

When subclassing
{{jsxref('Temporal/TimeZone','Temporal.TimeZone')}}, this
method doesn't need to be overridden because the default implementation returns
the result of calling `timeZone.toString()`.

## Syntax

```js
toJSON()
```

### Parameters

None.

### Return value

The string given by
{{jsxref('Temporal/TimeZone/id','timeZone.id')}}.

## Examples

```js
const user = {
  id: 775,
  username: 'robotcat',
  password: 'hunter2', // Note: Don't really store passwords like that
  userTimeZone: Temporal.TimeZone.from('Europe/Madrid')
};
const str = JSON.stringify(user, null, 2);
console.log(str);
// =>
// {
//   "id": 775,
//   "username": "robotcat",
//   "password": "hunter2",
//   "userTimeZone": "Europe/Madrid"
// }

// To rebuild from the string:
function reviver(key, value) {
  if (key.endsWith('TimeZone')) return Temporal.TimeZone.from(value);
  return value;
}
JSON.parse(str, reviver);
```
