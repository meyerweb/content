---
title: Temporal.PlainTime.prototype.equals()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/equals
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

<p class="summary"><span class="seoSummary">This method determines whether a <code>{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}</code> object is exactly the same as another wall-clock time.</span></p>

This function exists because it's not possible to compare using
`plainTime == other` or `plainTime === other`, due to ambiguity in the primitive
representation and between Temporal types.

## Syntax

```js
equals(other)
```

### Parameters

- `other`
  - : Another wall-clock time to compare. Either a
    `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
    object, or a value that can be converted to one as if passed to
    `{{jsxref('Temporal/PlainTime.from()','Temporal.PlainTime.from()')}}`.

### Return value

A boolean `true` if `PlainTime` and `other` are equal; otherwise, `false`. If
you also need to know the order in which the two times occur when they are not
equal, use
`{{jsxref('Temporal/PlainTime/compare','Temporal.PlainTime.compare()')}}`
instead.

## Examples

```js
time = Temporal.PlainTime.from('19:39:09.068346205');
other = Temporal.PlainTime.from('20:13:20.971398099');
time.equals(other); // => false
time.equals(time); // => true
```
