---
title: Temporal.Instant.fromEpochMicroseconds()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/fromEpochMicroseconds
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

<p class="summary"><span class="seoSummary">The <strong><code>fromEpochMicroseconds()</code></strong> static method creates a <code>{{jsxref('Temporal/Instant','Temporal.Instant')}}</code> object from a number of microseconds from the Unix epoch.</span></p>

## Syntax

```js
fromEpochMicroseconds(microseconds)
```

### Parameters

- `microseconds`
  - : The number of microseconds (10 <sup>-6</sup> seconds) between the Unix
    epoch (midnight UTC on January 1, 1970) and the desired time. `microseconds`
    **must** be typed as a {{jsxref('BigInt','BigInt')}} value, even
    if the value is small enough to be a regular integer.

### Return value

A new `{{jsxref('Temporal/Instant','Temporal.Instant')}}` object
representing an exact time that is `microseconds` from the Unix epoch.

## Examples

```js
instant = Temporal.Instant.fromEpochMicroseconds(BigInt(1553906700000000)); // => 2019-03-30T00:45:00Z
epoch = Temporal.Instant.fromEpochMicroseconds(BigInt(0)); // => 1970-01-01T00:00Z
turnOfTheCentury = Temporal.Instant.fromEpochMicroseconds(BigInt(-2208988800000000)); // => 1900-01-01T00:00Z
```
