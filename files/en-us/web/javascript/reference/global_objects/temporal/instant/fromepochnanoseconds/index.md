---
title: Temporal.Instant.fromEpochNanoseconds()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/fromEpochNanoseconds
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

<p class="summary"><span class="seoSummary">The <strong><code>fromEpochNanoseconds()</code></strong> static method creates a <code>{{jsxref('Temporal/Instant','Temporal.Instant')}}</code> object from a number of nanoseconds from the Unix epoch.</span> Equivalent to <code>new Temporal.Instant(<var>nanoseconds</var>)</code>.</p>

## Syntax

```js
fromEpochNanoseconds(nanoseconds)
```

### Parameters

- `nanoseconds`
  - : The number of nanoseconds (10 <sup>-9</sup> seconds) between the Unix
    epoch (midnight UTC on January 1, 1970) and the desired time. `nanoseconds`
    **must** be typed as a {{jsxref('BigInt','BigInt')}} value, even
    if the value is small enough to be a regular integer.

### Return value

A new `{{jsxref('Temporal/Instant','Temporal.Instant')}}` object
representing an exact time that is `nanoseconds` from the Unix epoch.

## Examples

```js
instant = Temporal.Instant.fromEpochNanoseconds(BigInt(1553906700000000000)); // => 2019-03-30T00:45:00Z
epoch = Temporal.Instant.fromEpochNanoseconds(BigInt(0)); // => 1970-01-01T00:00Z
turnOfTheCentury = Temporal.Instant.fromEpochNanoseconds(BigInt(-2208988800000000000)); // => 1900-01-01T00:00Z
```
