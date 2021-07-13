---
title: Temporal.Calendar.prototype.mergeFields()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/mergeFields
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>mergeFields()</code></strong> method combines a set of properties with another set of properties, resolves any conflicts between the two, removes properties that are invalidated by the conflict resolution, and returns the result.</span> In a situation where there are conflicting properties, they are resolved in favor the values supplied by the second set of properties.</p>

This method does not need to be called directly except in specialized code;
specifically, code that defines a new calendaring system. It is called
indirectly when using the `from()` and `with()` methods of the
`{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`,
`{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}`,
`{{jsxref('Temporal/PlainMonthDay','Temporal.PlainMonthDay')}}`,
`{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}`,
and
`{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}`,
classes.

## Syntax

```js
fields(fieldList, additionalFields);
```

### Parameters

- `fieldList`
  - : An object listing properties and values corresponding to components of a
    date.
- `additionalFields`
  - : Another object listing properties and values corresponding to components
    of a date.

### Return value

A new object with properties and values determined by combining _fieldList_ with
_additionalFields_.

## Examples

```js
Temporal.Calendar.from('iso8601').mergeFields(
  { year: 2006, month: 7 },
  { day: 31 }
);
// => {year: 2006, month: 7, day: 31}
```

In the following example, a new object is created by passing in an object with
`year`, `month`, and `date` properties, and a second object that specifies a
`monthCode`. When the two objects are merged, the conflict between the `month`
and `monthCode` values is resolved by adding `monthCode` and removing `month`.
Thus, the new object refers to 2006-10-31.

Note that `month` is not recalculated, but simply removed. When the resulting
object is passed to a method that constructs a new Temporal object, such as
`{{jsxref('Temporal/PlainDate/from','Temporal.PlainDate.from()')}}`,
the value of `month` will be determined (along with all the other properties of
a `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
object).

```js
Temporal.Calendar.from('iso8601').mergeFields(
  { year: 2006, month: 7, day: 31 },
  { monthCode: 'M10' }
);
// => { year: 2006, monthCode: "M10", day: 31 }
```
