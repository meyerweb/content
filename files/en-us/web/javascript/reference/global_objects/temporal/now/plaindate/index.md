---
title: Temporal.now.plainDate()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/now/plaindate
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

<p class="summary"><span class="seoSummary">The <strong><code>plainDate()</code></strong> method gets the current calendar date according to the system settings. Optionally, a time zone can be given in which the time is computed, instead of the current system time zone.</span></p>

## Syntax

```js
plainDate(calendar)
plainDate(calendar, timeZone)
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

A `Temporal.PlainDate` object representing the current system date in the
reckoning of the given calendar. If you only want to use the ISO 8601 calendar,
use
`{{jsxref("Temporal/now/plainDateISO", "Temporal.now.plainDateISO()")}}`.

## Example

```js
// Is it Nowruz (New Year in the Persian calendar)?
var date = Temporal.now.plainDate('persian');
if (date.month === 1 && date.day === 1) console.log('New year!');
```
