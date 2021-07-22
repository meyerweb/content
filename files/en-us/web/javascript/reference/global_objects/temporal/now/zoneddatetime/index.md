---
title: Temporal.now.zonedDateTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/now/zoneddatetime
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

The **`plainDateTime()`** method gets the current system date, time, time zone,
and time zone offset according to the system settings. Optionally, a time zone
can be given in which the time is computed, instead of the current system time
zone.

## Syntax

```js
zonedDateTime(calendar)
zonedDateTime(calendar, timeZone)
```

### Parameters

- `calendar`
  - : Defines the calendar system to get the current date and time in. Either a
    `Temporal.calendar` object, an object that implements the Temporal calendar
    protocol, or a string.
- `timeZone` {{optional_inline}}
  - : The time zone to get the current date and time in. Either a
    `Temporal.TimeZone` object, an object that implements the Temporal time zone
    protocol, or a string. If omitted, the current system time zone is used.

### Return value

A `Temporal.ZonedDateTime` object representing the current system date, time,
time zone, and time zone offset in the reckoning of the given calendar. If you
only want to use the [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)
calendar, use
{{jsxref("Temporal/now/zonedDateTimeISO","Temporal.now.zonedDateTimeISO()")}}.

## Example

```js
financialCentres = {
  'New York': 'America/New_York',
  London: 'Europe/London',
  Tokyo: 'Asia/Tokyo'
};
console.log(`Here: ${Temporal.now.zonedDateTime('gregory')}`);
Object.entries(financialCentres).forEach(([name, timeZone]) => {
  console.log(`${name}: ${Temporal.now.zonedDateTime('gregory',timeZone)}`);
});
// example output:
// Here: 2020-09-18T01:17:48.431957915-07:00[America/Los_Angeles][u-ca=gregory]
// New York: 2020-09-18T04:17:48.435068431-04:00[America/New_York][u-ca=gregory]
// London: 2020-09-18T09:17:48.438068435+01:00[Europe/London][u-ca=gregory]
// Tokyo: 2020-09-18T17:17:48.441068438+09:00[Asia/Tokyo][u-ca=gregory]
```
