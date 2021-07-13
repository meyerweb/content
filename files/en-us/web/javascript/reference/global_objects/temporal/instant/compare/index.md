---
title: Temporal.Instant.compare()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/compare
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

<p class="summary"><span class="seoSummary">The <strong><code>compare()</code></strong> static method compares two points in time and returns an integer indicating which comes before the other.</span></p>

If you don't care about the order in which the two times occur, but instead
merely want to know if they're the same or not, use
`{{jsxref('Temporal/Instant/equals','Temporal.Instant.equals()')}}`
instead.

## Syntax

```js
compare(timeOne, timeTwo)
```

### Parameters

- `timeOne`

  `timeTwo`

  - : Either a
    `{{jsxref('Temporal/Instant','Temporal.Instant')}}` object,
    or a value that can be converted to one as if passed to
    `{{jsxref('Temporal/Instant.from()','Temporal.Instant.from()')}}`.

### Return value

An integer indicating whether `timeOne` comes before, comes after, or is equal
to `timeTwo`. The possible returned values are:

- `−1` if `timeOne` comes before `timeTwo`;
- `0` if `timeOne` and `timeTwo` represent the same time;
- `1` if `timeOne` comes after `timeTwo`.

## Examples

```js
one = Temporal.Instant.fromEpochSeconds(1.0e9);   // 2001-09-09T01:46:40Z
two = Temporal.Instant.fromEpochSeconds(1.1e9);   // 2004-11-09T11:33:20Z
three = Temporal.Instant.fromEpochSeconds(1.2e9); // 2008-01-10T21:20:00Z
sorted = [three, one, two].sort(Temporal.Instant.compare);
sorted.join(' < ');
// => 2001-09-09T01:46:40Z < 2004-11-09T11:33:20Z < 2008-01-10T21:20:00Z
```
