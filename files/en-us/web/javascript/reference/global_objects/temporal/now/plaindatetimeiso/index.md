---
title: Temporal.now.plainDateTimeISO()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/now/plaindatetimeiso
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

The **`plainDateTimeISO()`** method gets the current calendar date and time
according to the system settings, reckoned using the ISO 8601 calendar.
Optionally, a time zone can be given in which the time is computed, instead of
the current system time zone.

## Syntax

```js
plainDateTimeISO()
plainDateTimeISO(timeZone)
```

### Parameters

- `timeZone` {{optional_inline}}
  - : The time zone to get the current date and time in. Either a
    `Temporal.TimeZone` object, an object that implements the Temporal time zone
    protocol, or a string. If omitted, the current system time zone is used.

### Return value

A `Temporal.PlainDateTime` object representing the current system date and time
in the reckoning of the ISO 8601 calendar. If you want to get the date and time
according to any other calendar, use
{{jsxref("Temporal/now/plainDateTime","Temporal.now.plainDateTime()")}}.

## Example

```js
financialCentres = {
  'New York': 'America/New_York',
  'London': 'Europe/London',
  'Tokyo': 'Asia/Tokyo',
};
console.log(`Here: ${Temporal.now.plainDateTimeISO()}`);
Object.entries(financialCentres).forEach(([name, timeZone]) => {
  console.log(`${name}: ${Temporal.now.plainDateTimeISO(timeZone)}`);
});
// example output:
// Here: 2020-01-24T21:51:02.142905166
// New York: 2020-01-25T00:52:14.756462142
// London: 2020-01-25T05:52:14.758534756
// Tokyo: 2020-01-25T14:52:14.759534758
```
