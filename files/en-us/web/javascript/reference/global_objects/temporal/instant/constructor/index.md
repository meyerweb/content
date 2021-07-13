---
title: Temporal.Instant() constructor
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/constructor
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - constructor
  - Time Zone
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>Temporal.Instant()</code></strong> constructor creates a new <code>{{jsxref('Temporal/Instant','Temporal.Instant')}}</code> object which represents a specific instant in time.</span></p>

Use this constructor directly if you know the precise number of nanoseconds
already and have it in bigint form, for example from a database. Otherwise, use
`{{jsxref('Temporal/Instant/from','Temporal.Instant.from()')}}`;
or, use
`{{jsxref('Temporal/Instant/fromEpochSeconds','Temporal.Instant.fromEpochSeconds()')}}`,
`{{jsxref('Temporal/Instant/fromEpochMilliseconds','Temporal.Instant.fromEpochMilliseconds()')}}`,
or
`{{jsxref('Temporal/Instant/fromEpochMicroseconds','Temporal.Instant.fromEpochMicroseconds()')}}`
if you have a different unit than nanoseconds.

## Syntax

```js
new Temporal.Instant(epochNanoseconds)
```

### Parameters

- `epochNanoseconds`
  - : A {{jsxref('BigInt','BigInt')}} value of the number of
    nanoseconds (10 <sup>−9</sup> seconds) between the Unix epoch (midnight UTC
    on January 1, 1970) and the desired exact time. The range of allowed values
    for `epochNanoseconds` is the same as the old-style JavaScript
    {{jsxref('Date','Date')}}, 100 million (10 <sup>8</sup> ) days before
    or after the Unix epoch. This range covers just over half a million years.
    If `epochNanoseconds` is outside of this range, a `RangeError` will be
    thrown.

### Return value

A new `{{jsxref('Temporal/Instant','Temporal.Instant')}}` object.

## Examples

```js
instant = new Temporal.Instant(1553906700000000000n);
// When was the Unix epoch?
epoch = new Temporal.Instant(0n); // => 1970-01-01T00:00Z
// Dates before the Unix epoch are negative
turnOfTheCentury = new Temporal.Instant(-2208988800000000000n); // => 1900-01-01T00:00Z
```
