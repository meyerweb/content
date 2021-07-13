---
title: Temporal.now.plainDateTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/now/plaindatetime
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

<p class="summary"><span class="seoSummary">The <strong><code>plainDateTime()</code></strong> method gets the current system date and time according to the system settings. Optionally, a time zone can be given in which the time is computed, instead of the current system time zone.</span></p>

## Syntax

```js
plainDateTime(calendar)
plainDateTime(calendar, timeZone)
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

A `Temporal.PlainDateTime` object representing the current system date and time
in the reckoning of the given calendar. If you only want to use the
[ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) calendar, use
`{{jsxref("Temporal/now/plainDateTimeISO","Temporal.now.plainDateTimeISO()")}}`.

## Example

```js
financialCentres = {
  'New York': 'America/New_York',
  'London': 'Europe/London',
  'Tokyo': 'Asia/Tokyo',
};
console.log(`Here: ${Temporal.now.plainDateTime('gregory')}`);
Object.entries(financialCentres).forEach(([name, timeZone]) => {
  console.log(`${name}: ${Temporal.now.plainDateTime('gregory',timeZone)}`);
});
// example output:
// Here: 2020-01-24T21:51:02.142905166[u-ca=gregory]
// New York: 2020-01-25T00:52:14.756462142[u-ca=gregory]
// London: 2020-01-25T05:52:14.758534756[u-ca=gregory]
// Tokyo: 2020-01-25T14:52:14.759534758[u-ca=gregory]
```
