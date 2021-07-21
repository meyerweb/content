---
title: Temporal.PlainDateTime.prototype.equals()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/equals
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

This method determines whether a
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object is exactly the same as another date.This function exists because it's not
possible to compare using `PlainDateTime == other` or `PlainDateTime === other`,
due to ambiguity in the primitive representation and between Temporal types.

If you also need to know the order in which the two times occur when they are
not equal, use
{{jsxref('Temporal/PlainDateTime/compare','Temporal.PlainDateTime.compare()')}}
instead.

## Syntax

```js
equals(otherDateTime)
```

### Parameters

- `otherDateTime`
  - : Another date to compare. Either a
    {{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
    object, or a value that can be converted to one as if passed to
    {{jsxref('Temporal/PlainDateTime.from()','Temporal.PlainDateTime.from()')}}.

### Return value

A boolean `true` if the two dates and times are equal; otherwise, `false`. Note
that this function will return `false` if the two date-and-time objects have
different calendar properties, even if the actual dates and times are equal.

## Examples

```js
dt1 = Temporal.PlainDateTime.from('1995-12-07T03:24:30.000003500');
dt2 = Temporal.PlainDateTime.from('2019-01-31T15:30');
dt1.equals(dt2); // => false
dt1.equals(dt1); // => true
```
