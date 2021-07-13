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

<p class="summary"><span class="seoSummary">The <strong><code>getISOFields()</code></strong> method returns an object containing the ISO 8601 calendar fields and values that correspond to the year and month.</span> This method is mainly useful if you are implementing a custom calendar.</p>

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
`{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}`
object was
{{jsxref('Temporal/PlainYearMonth/constructor','constructed')}}.

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
