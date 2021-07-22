---
title: Temporal.Calendar.prototype.fields()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/fields
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

The **`fields()`** method accepts an array of field names and returns an array
fields that are strongly associated with the original array of fields in the
current calendar.For example, passing an array of `['year']` under the Gregorian
calendar will return the array `['year', 'era', 'eraYear']`. This is because in
the Gregorian calendar, a bare year is ambiguous without also knowing the era
(i.e., Year 1 could be either 1BC or 1AD), and could be specified either by a
value for `year` or a combination of values for `era` and `eraYear`.

This method does not need to be called directly except in specialized code;
specifically, code that defines a new calendaring system. It is called
indirectly when using the `from()` and `with()` methods of the
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}},
{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}},
{{jsxref('Temporal/PlainMonthDay','Temporal.PlainMonthDay')}},
{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}},
and
{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
classes, as well as a few other methods.

## Syntax

```js
fields(fieldList);
```

### Parameters

- `fieldList`
  - : A list of field names represented as an array of strings.

### Return value

An array of a list of field names represented as strings.

## Examples

```js
// In the ISO 8601 calendar, every year value is unique
Temporal.Calendar.from('iso8601').fields(['year']);
// => [ 'year']

// In the Gregorian calendar, every year value could be specified in
// more than one way, so more fields are needed to disambiguate
Temporal.Calendar.from('gregory').fields(['year']);
// => [ 'year', 'era', 'eraYear' ]
```
