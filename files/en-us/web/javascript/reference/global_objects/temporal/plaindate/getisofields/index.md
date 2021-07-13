---
title: Temporal.PlainDate.prototype.getISOFields()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/getISOFields
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>getISOFields()</code></strong> method returns an object containing the ISO 8601 calendar fields and values that correspond to the date.</span> This method is mainly useful if you are implementing a custom calendar.</p>

## Syntax

```js
getISOFields()
```

### Parameters

None.

### Return value

An object containing the `isoYear`, `isoMonth`, `isoDay`, and `calendar`
properties.

## Examples

```js
pd = Temporal.PlainDate.from('2021-04-27');
pd.getISOFields().isoDay;   // => 27
pd.getISOFields().isoMonth; // => 4
pd.getISOFields().isoYear;  // => 2021
```

```js
pd = new Temporal.PlainDate(2021, 04, 27, 'iso8601');
// same results as above
```
