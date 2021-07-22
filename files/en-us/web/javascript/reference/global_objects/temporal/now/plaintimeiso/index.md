---
title: Temporal.now.plainTimeISO()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/now/plaintimeiso
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - now
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

The **`plainTimeISO()`** method gets the current time, excluding any date
information, according to the system settings, reckoned using the ISO 8601
calendar. Optionally, a time zone can be given in which the time is computed,
instead of the current system time zone.

## Syntax

```js
plainTimeISO()
plainTimeISO(timeZone)
```

### Parameters

- `timeZone` {{optional_inline}}
  - : The time zone to get the current date and time in. Either a
    `Temporal.TimeZone` object, an object that implements the Temporal time zone
    protocol, or a string. If omitted, the current system time zone is used.

### Return value

A `Temporal.PlainTime` object representing the current system time in the
reckoning of the ISO 8601 calendar. Note: There is no corresponding
**`plainTime()`**.

## Example

```js
// Is it lunchtime?
time = Temporal.now.plainTimeISO();
if (time.hour === 12) console.log('Lunchtime!');
```
