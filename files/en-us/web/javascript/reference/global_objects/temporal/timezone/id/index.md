---
title: Temporal.TimeZone.prototype.id
slug: Web/JavaScript/Reference/Global_Objects/Temporal/TimeZone/id
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

The **`id`** read-only property returns an unambigious time zone identifier from
a {{jsxref('Temporal/TimeZone','Temporal.TimeZone')}}
object.When subclassing
{{jsxref('Temporal/TimeZone','Temporal.TimeZone')}}, this
property doesn't need to be overridden because the default implementation gives
the result of calling `toString()`.

## Syntax

```js
timeZone.id
```

### Value

A string containing an unambiguous identifier for the time zone. Effectively,
this is the canonicalized version of whatever `timeZoneIdentifier` was passed as
a parameter to the constructor.

## Examples

```js
var tz = Temporal.TimeZone.from('Asia/Jakarta');
tz.id;  // => "Asia/Jakarta"
```
