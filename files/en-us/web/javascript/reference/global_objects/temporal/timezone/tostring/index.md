---
title: Temporal.TimeZone.prototype.toString()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/TimeZone/toString
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - Time Zone
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

The **`toString()`** method returns the time zone's ID as a string.This method
overrides `Object.prototype.toString()` and returns the same string as the time
zone's {{jsxref('Temporal/TimeZone/id','id')}} property.

## Syntax

```js
toString()
```

### Parameters

None.

### Return value

The string given by
{{jsxref('Temporal/TimeZone/id','timeZone.id')}}.

## Examples

```js
var tz = Temporal.TimeZone.from('Pacific/Rarotonga');
tz.toString();  // => "Pacific/Rarotonga"
```
