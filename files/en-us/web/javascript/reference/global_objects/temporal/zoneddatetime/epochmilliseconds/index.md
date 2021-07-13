---
title: Temporal.ZonedDateTime.prototype.epochMilliseconds
slug: >-
  Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/epochMilliseconds
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>epochMilliseconds</code></strong> read-only property returns the number of full milliseconds between the <code>{{jsxref('Temporal.zonedDateTime','Temporal.zonedDateTime')}}</code> object and 00:00 UTC on 1970-01-01, otherwise known as the UNIX Epoch. Any fractional remainders are truncated towards zero.</span></p>

Using the value of the `epochMilliseconds` property is the easiest way to
construct a legacy `{{jsxref('Date')}}` object from a
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
object.

## Syntax

```js
datetime.epochMilliseconds
```

### Value

A number which is always an integer.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('2020-02-01T12:30+09:00[Asia/Tokyo]');
epochMs = zdt.epochMilliseconds;
  // => 1580527800000
legacyDate = new Date(epochMs);
  // => 2020-02-01T03:30:00.000Z
  // (if the system time zone is America/Los_Angeles)
```
