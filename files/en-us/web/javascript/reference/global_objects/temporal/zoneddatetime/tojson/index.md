---
title: Temporal.ZonedDateTime.prototype.toJSON()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/toJSON
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toJSON()</code></strong> method returns a string representing the date and time in ISO 8601 format.</span> This method provides a useful value when a <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> object is passed to <code>{{jsxref('JSON.stringify','JSON.stringify()')}}</code>. It is rarely useful in any other context.</p>

The reverse operation, recovering a
`{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}`
object from a string, is accomplished by using
`{{jsxref('Temporal/ZonedDateTime/from','Temporal.ZonedDateTime.from()')}}`,
but that method cannot be called automatically by
`{{jsxref('JSON.parse','JSON.parse()')}}`. If you need to rebuild a
`{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}`
object from a JSON string, then you need to know the names of the keys that
should be interpreted as
`{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}`
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
const event = {
  id: 311,
  name: 'FictionalConf 2018',
  openingZonedDateTime: Temporal.ZonedDateTime.from('2018-07-06T10:00+05:30[Asia/Kolkata]'),
  closingZonedDateTime: Temporal.ZonedDateTime.from('2018-07-08T18:15+05:30[Asia/Kolkata]')
};
const str = JSON.stringify(event, null, 2);
console.log(str);
// =>
// {
//   "id": 311,
//   "name": "FictionalConf 2018",
//   "openingZonedDateTime": "2018-07-06T10:00+05:30[Asia/Kolkata]",
//   "closingZonedDateTime": "2018-07-08T18:15+05:30[Asia/Kolkata]"
// }

// To rebuild from the string:
function reviver(key, value) {
  if (key.endsWith('ZonedDateTime')) return Temporal.ZonedDateTime.from(value);
  return value;
}
JSON.parse(str, reviver);
```
