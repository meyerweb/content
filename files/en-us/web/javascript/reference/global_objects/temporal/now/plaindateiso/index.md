---
title: Temporal.now.plainDateISO()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/now/plaindateiso
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

<p class="summary"><span class="seoSummary">The <strong><code>plainDateISO()</code></strong> method gets the current calendar date according to the system settings, reckoned using the ISO 8601 calendar. Optionally, a time zone can be given in which the time is computed, instead of the current system time zone.</span></p>

## Syntax

```js
plainDateISO()
plainDateISO(timeZone)
```

### Parameters

- `timeZone` {{optional_inline}}
  - : The time zone to get the current date in. Either a `Temporal.TimeZone`
    object, an object that implements the Temporal time zone protocol, or a
    string. If omitted, the current system time zone is used.

### Return value

A `Temporal.PlainDate` object representing the current system date in the
reckoning of the ISO 8601 calendar. If you want to get the date according to any
other calendar, use
`{{jsxref("Temporal/now/plainDate","Temporal.now.plainDate()")}}`.

## Example

```js
// Is it New Year in the ISO 8601 calendar?
var date = Temporal.now.plainDateISO();
if (date.month === 1 && date.day === 1) console.log('New year!');
```
