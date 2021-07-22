---
title: Temporal.PlainDateTime.prototype.getISOFields()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/getISOFields
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`getISOFields()`** method returns an object containing the ISO 8601
calendar fields and values that correspond to the date and time.This method is
mainly useful if you are implementing a custom calendar.

## Syntax

```js
getISOFields()
```

### Parameters

None.

### Return value

An object containing the `isoYear`, `isoMonth`, `isoDay`, `isoHour`,
`isoMinute`, `isoSecond`, `isoMillisecond`, `isoMicrosecond`, `isoNanosecond`,
and `calendar` properties.

## Examples

```js
pd = Temporal.PlainDateTime.from('2021-04-27');
pd.getISOFields().isoDay;   // => 27
pd.getISOFields().isoMonth; // => 4
pd.getISOFields().isoYear;  // => 2021
```

```js
pd = new Temporal.PlainDateTime(2021, 04, 27, 'iso8601');
// same results as above
```
