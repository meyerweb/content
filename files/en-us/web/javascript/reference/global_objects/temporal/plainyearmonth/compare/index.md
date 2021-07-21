---
title: Temporal.PlainYearMonth.compare()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/compare
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

The **`compare()`** static method compares two months and returns an integer
indicating which comes before the other.

If you don't care about the order in which the two months occur, but instead
merely want to know if they're the same or not, use
{{jsxref('Temporal/PlainYearMonth/equals','Temporal.PlainYearMonth.equals()')}}
instead.

## Syntax

```js
compare(monthOne, monthTwo)
```

### Parameters

- `monthOne`

  `monthTwo`

  - : Either a
    {{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}
    object, or a value that can be converted to one as if passed to
    {{jsxref('Temporal/PlainYearMonth/from','Temporal.PlainYearMonth.from()')}}.

### Return value

An integer indicating whether `monthTwo` comes before, comes after, or is equal
to `monthTwo`. The possible returned values are:

- `−1` if `monthOne` comes before `monthTwo`;
- `0` if `monthOne` and `monthTwo` represent the same month and year;
- `1` if `monthOne` comes after `monthTwo`.

## Examples

```js
one = Temporal.PlainYearMonth.from('2006-08');
two = Temporal.PlainYearMonth.from('2015-07');
Temporal.PlainYearMonth.compare(one, two); // => -1
```

In the following example, `compare()` is used to sort an array of
{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}
objects.

```js
one = Temporal.PlainYearMonth.from('2006-08');
two = Temporal.PlainYearMonth.from('2015-07');
three = Temporal.PlainYearMonth.from('1930-02');
sorted = [one, two, three].sort(Temporal.PlainYearMonth.compare);
sorted.join(' | '); // => "1930-02 | 2006-08 | 2015-07"
```
