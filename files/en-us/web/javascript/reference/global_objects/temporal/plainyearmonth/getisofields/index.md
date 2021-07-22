---
title: Temporal.PlainYearMonth.prototype.getISOFields()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/getISOFields
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`getISOFields()`** method returns an object containing the ISO 8601
calendar fields and values that correspond to the year and month.This method is
mainly useful if you are implementing a custom calendar.

## Syntax

```js
getISOFields()
```

### Parameters

None.

### Return value

An object containing the `isoYear`, `isoMonth`, `isoDay`, and `calendar`
properties. The value of the `isoDay` property will be equal to the
`referenceISODay` constructor argument passed when the
{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}
object was
{{jsxref('Temporal/PlainYearMonth/constructor','constructed','','nocode')}}.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2021-04');
ym.getISOFields().isoDay;   // => 1
ym.getISOFields().isoMonth; // => 4
ym.getISOFields().isoYear;  // => 2021
```

```js
ym = new Temporal.PlainYearMonth(2021, 04, 'iso8601', 24);
ym.getISOFields().isoDay;   // => 24
ym.getISOFields().isoMonth; // => 4
ym.getISOFields().isoYear;  // => 2021
```
