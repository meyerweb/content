---
title: Temporal.Instant.fromEpochMilliseconds()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/fromEpochMilliseconds
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

The **`fromEpochMilliseconds()`** static method creates a
{{jsxref('Temporal/Instant','Temporal.Instant')}} object from a
number of milliseconds from the Unix epoch.The number of milliseconds since the
Unix epoch is also returned from the `getTime()` and `valueOf()` methods of
legacy JavaScript {{jsxref('Date','Date')}} objects, as well as
`Date.now()`.

## Syntax

```js
fromEpochMilliseconds(milliseconds)
```

### Parameters

- `milliseconds`
  - : The number of milliseconds (10 <sup>-3</sup> seconds) between the Unix
    epoch (midnight UTC on January 1, 1970) and the desired time.

### Return value

A new {{jsxref('Temporal/Instant','Temporal.Instant')}} object
representing an exact time that is `milliseconds` from the Unix epoch.

## Examples

```js
instant = Temporal.Instant.fromEpochMilliseconds(1553906700000); // => 2019-03-30T00:45:00Z
epoch = Temporal.Instant.fromEpochMilliseconds(0); // => 1970-01-01T00:00Z
turnOfTheCentury = Temporal.Instant.fromEpochMilliseconds(-2208988800000); // => 1900-01-01T00:00Z

// Use fromEpochMilliseconds, for example, if you have epoch millisecond
// data stored in a file:
todayMs = Temporal.Instant.fromEpochMilliseconds(msReadFromFile);
```
