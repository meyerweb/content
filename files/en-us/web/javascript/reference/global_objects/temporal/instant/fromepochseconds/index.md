---
title: Temporal.Instant.fromEpochSeconds()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/fromEpochSeconds
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

<p class="summary"><span class="seoSummary">The <strong><code>fromEpochSeconds()</code></strong> static method creates a <code>{{jsxref('Temporal/Instant','Temporal.Instant')}}</code> object from a number of seconds from the Unix epoch.</span> The number of seconds since the Unix epoch is a common measure of exact time in many computer systems. Use this method if you need to interface with such a system.</p>

## Syntax

```js
fromEpochSeconds(seconds)
```

### Parameters

- `seconds`
  - : The number of seconds between the Unix epoch (midnight UTC on January
    1, 1970) and the desired time.

### Return value

A new `{{jsxref('Temporal/Instant','Temporal.Instant')}}` object
representing an exact time that is `seconds` from the Unix epoch.

## Examples

```js
// Same examples as in new Temporal.Instant(), but with seconds precision
instant = Temporal.Instant.fromEpochSeconds(1553906700); // => 2019-03-30T00:45:00Z
epoch = Temporal.Instant.fromEpochSeconds(0); // => 1970-01-01T00:00Z
turnOfTheCentury = Temporal.Instant.fromEpochSeconds(-2208988800); // => 1900-01-01T00:00Z
```
