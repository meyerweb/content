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

<p class="summary"><span class="seoSummary">The <strong><code>toJSON()</code></strong> method returns a string representing the length of the duration in ISO 8601 format.</span> This method provides a useful value when a <code>{{jsxref('Temporal.Duration','Temporal.Duration')}}</code> object is passed to <code>{{jsxref('JSON.stringify','JSON.stringify()')}}</code>. It is rarely useful in any other context.</p>

The reverse operation, recovering a
`{{jsxref('Temporal/Duration','Temporal.Duration')}}` object
from a string, is accomplished by using
`{{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}`,
but that method cannot be called automatically by
`{{jsxref('JSON.parse','JSON.parse()')}}`. If you need to rebuild a
`{{jsxref('Temporal/Duration','Temporal.Duration')}}` object
from a JSON string, then you need to know the names of the keys that should be
interpreted as
`{{jsxref('Temporal/Duration','Temporal.Duration')}}`
properties. In that case, you can build a custom "reviver" function for your use
case.

<div class="warning"><p><strong>NOTE:</strong> If any of <code>duration.milliseconds</code>, <code>duration.microseconds</code>, or <code>duration.nanoseconds</code> are over 999, then deserializing from the result of <code>duration.toJSON()</code> will yield an equal but different object.</p></div>

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
