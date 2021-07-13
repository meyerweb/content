---
title: Temporal.PlainYearMonth.prototype.toJSON()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/toJSON
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">Returns a string representing the year and month in ISO 8601 format.</span> This method provides a useful value when a <code>{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}</code> object is passed to <code>{{jsxref('JSON.stringify','JSON.stringify()')}}</code>. It is rarely useful in any other context. If you simply need to serialize the year and month to an ISO 8601 string, use <code>{{jsxref('Temporal/PlainYearMonth/toString','Temporal.PlainYearMonth.toString()')}}</code> instead.</p>

The reverse operation, recovering a
`{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}`
object from a string, is accomplished by using
`{{jsxref('Temporal/PlainYearMonth/from','Temporal.PlainYearMonth.from()')}}`,
but that method cannot be called automatically by
`{{jsxref('JSON.parse','JSON.parse()')}}`. If you need to rebuild a
`{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}`
object from a JSON string, then you need to know the names of the keys that
should be interpreted as
`{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}`
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
const boardMeeting = {
  id: 4,
  agenda: ['Roll call', 'Budget'],
  meetingYearMonth: Temporal.PlainYearMonth.from({ year: 2019, month: 3 })
};
const str = JSON.stringify(boardMeeting, null, 2);
console.log(str);
// =>
// {
//   "id": 4,
//   "agenda": [
//     "Roll call",
//     "Budget"
//   ],
//   "meetingYearMonth": "2019-03"
// }

// To rebuild from the string:
function reviver(key, value) {
  if (key.endsWith('YearMonth')) return Temporal.PlainYearMonth.from(value);
  return value;
}
JSON.parse(str, reviver);
```
