---
title: Temporal.now.zonedDateTimeISO()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/now/zoneddatetimeiso
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

<p class="summary"><span class="seoSummary">The <strong><code>zonedDateTimeISO()</code></strong> method gets the current system date, time, time zone, and time zone offset according to the system settings, reckoned using the ISO 8601 calendar. Optionally, a time zone can be given in which the time is computed, instead of the current system time zone.</span></p>

## Syntax

```js
zonedDateTimeISO()
zonedDateTimeISO(timeZone)
```

### Parameters

- `timeZone` {{optional_inline}}
  - : The time zone to get the current date and time in. Either a
    `Temporal.TimeZone` object, an object that implements the Temporal time zone
    protocol, or a string. If omitted, the current system time zone is used.

### Return value

A `Temporal.ZonedDateTime` object representing the current system date, time,
time zone, and time zone offset in the reckoning of the ISO 8601 calendar. If
you want to get that information according to any other calendar, use
`{{jsxref("Temporal/now/zonedDateTime","Temporal.now.zonedDateTime()")}}`.

## Example

```js
financialCentres = {
  'New York': 'America/New_York',
  London: 'Europe/London',
  Tokyo: 'Asia/Tokyo'
};
console.log(`Here: ${Temporal.now.zonedDateTimeISO()}`);
Object.entries(financialCentres).forEach(([name, timeZone]) => {
  console.log(`${name}: ${Temporal.now.zonedDateTimeISO(timeZone)}`);
});
// example output:
// Here: 2020-09-18T01:17:48.431957915-07:00[America/Los_Angeles]
// New York: 2020-09-18T04:17:48.435068431-04:00[America/New_York]
// London: 2020-09-18T09:17:48.438068435+01:00[Europe/London]
// Tokyo: 2020-09-18T17:17:48.441068438+09:00[Asia/Tokyo]
```
