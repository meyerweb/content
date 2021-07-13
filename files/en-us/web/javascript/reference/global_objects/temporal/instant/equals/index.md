---
title: Temporal.Instant.prototype.equals()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/equals
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

<p class="summary"><span class="seoSummary">This method determines whether a <code>{{jsxref('Temporal/Instant','Temporal.Instant')}}</code> object is exactly the same as another time value.</span></p>

## Syntax

```js
equals(other)
```

### Parameters

- `other`
  - : Either a
    `{{jsxref('Temporal/Instant','Temporal.Instant')}}` object,
    or a value that can be converted to one as if passed to
    `{{jsxref('Temporal/Instant.from()','Temporal.Instant.from()')}}`.

### Return value

A boolean `true` if `instant` and `other` are equal; otherwise, `false`. If you
also need to know the order in which the two times occur when not equal, use
`{{jsxref('Temporal/Instant/compare','Temporal.Instant.compare()')}}`
instead.

## Examples

```js
one = Temporal.Instant.fromEpochSeconds(1.0e9);
two = Temporal.Instant.fromEpochSeconds(1.1e9);
one.equals(two); // => false
one.equals(one); // => true
```
