---
title: Temporal.PlainTime.compare()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/compare
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

<p class="summary"><span class="seoSummary">The <strong><code>compare()</code></strong> static method compares two times and returns an integer indicating which comes before the other.</span></p>

If you don't care about the order in which the two times occur, but instead
merely want to know if they're the same or not, use
`{{jsxref('Temporal/PlainTime/equals','Temporal.PlainTime.equals()')}}`
instead.

## Syntax

```js
compare(timeOne, timeTwo)
```

### Parameters

- `timeOne`

  `timeTwo`

  - : Either a
    `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
    object, or a value that can be converted to one as if passed to
    `{{jsxref('Temporal/PlainTime/from','Temporal.PlainTime.from()')}}`.

### Return value

An integer indicating whether `timeOne` comes before, comes after, or is equal
to `timeTwo`. The possible returned values are:

- `−1` if `timeOne` comes before `timeTwo`;
- `0` if `timeOne` and `timeTwo` represent the same time and year;
- `1` if `timeOne` comes after `timeTwo`.

## Examples

```js
one = Temporal.PlainTime.from('03:24');
two = Temporal.PlainTime.from('01:24');
Temporal.PlainTime.compare(one, two); // => 1
```

In the following example, `compare()` is used to sort an array of
`{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}`
objects.

```js
one = Temporal.PlainTime.from('03:24');
two = Temporal.PlainTime.from('01:24');
three = Temporal.PlainTime.from('01:24:05');
sorted = [one, two, three].sort(Temporal.PlainTime.compare);
sorted.join(' | '); // => "01:24:00 | 01:24:05 | 03:24:00"
```
