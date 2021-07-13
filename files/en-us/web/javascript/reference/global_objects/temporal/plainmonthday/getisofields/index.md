---
title: Temporal.PlainMonthDay.prototype.getISOFields()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainMonthDay/getISOFields
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>getISOFields()</code></strong> method returns an object containing the ISO 8601 calendar fields and values that correspond to the month and day.</span> This method is mainly useful if you are implementing a custom calendar.</p>

## Syntax

```js
getISOFields()
```

### Parameters

None.

### Return value

An object containing the `isoYear`, `isoMonth`, `isoDay`, and `calendar`
properties. The value of the `isoYear` property will be equal to the
`referenceISOYear` constructor argument passed when the
`{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}`
object was
{{jsxref('Temporal/PlainMonthDay/constructor','constructed')}}.

## Examples

```js
md = Temporal.PlainMonthDay.from('04-22');
md.getISOFields().isoDay;   // => 22
md.getISOFields().isoMonth; // => 4
md.getISOFields().isoYear;  // => 1972
```

```js
md = new Temporal.PlainMonthDay(4, 22, 'iso8601', 2021);
md.getISOFields().isoDay;   // => 22
md.getISOFields().isoMonth; // => 4
md.getISOFields().isoYear;  // => 2021
```
