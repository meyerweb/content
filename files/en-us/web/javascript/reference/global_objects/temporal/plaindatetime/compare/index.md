---
title: Temporal.PlainDateTime.compare()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/compare
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

The **`compare()`** static method compares two dates with times and returns an
integer indicating which comes before the other.

If you don't care about the order in which the two dates and times occur, but
instead merely want to know if they're the same or not, use
{{jsxref('Temporal/PlainDateTime/equals','Temporal.PlainDateTime.equals()')}}
instead.

## Syntax

```js
compare(dateTimeOne, dateTimeTwo)
```

### Parameters

- `dateTimeOne`

  `dateTimeTwo`

  - : Either a
    {{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
    object, or a value that can be converted to one as if passed to
    {{jsxref('Temporal/PlainDateTime/from','Temporal.PlainDateTime.from()')}}.

### Return value

An integer indicating whether `dateTimeTwo` comes before, comes after, or is
equal to `dateTimeTwo`. The possible returned values are:

- `−1` if `dateTimeOne` comes before `dateTimeTwo`;
- `0` if `dateTimeOne` and `dateTimeTwo` represent the same date;
- `1` if `dateTimeOne` comes after `dateTimeTwo`.

## Examples

```js
one = Temporal.PlainDateTime.from('2006-08-24');
two = Temporal.PlainDateTime.from('2015-07-14');
Temporal.PlainDateTime.compare(one, two); // => -1
```

In the following example, `compare()` is used to sort an array of
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
objects.

```js
one = Temporal.PlainDateTime.from('1995-12-07T03:24');
two = Temporal.PlainDateTime.from('1995-12-07T01:24');
three = Temporal.PlainDateTime.from('2015-12-07T01:24');
sorted = [one, two, three].sort(Temporal.PlainDateTime.compare);
sorted.join(' | ');
// => '1995-12-07T01:24:00 | 1995-12-07T03:24:00 | 2015-12-07T01:24:00'
```
