---
title: Temporal.PlainDate.compare()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/compare
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

The **`compare()`** static method compares two dates and returns an integer
indicating which comes before the other.

If you don't care about the order in which the two date occur, but instead
merely want to know if they're the same or not, use
{{jsxref('Temporal/PlainDate/equals','Temporal.PlainDate.equals()')}}
instead.

## Syntax

```js
compare(dateOne, dateTwo)
```

### Parameters

- `dateOne`

  `dateTwo`

  - : Either a
    {{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}
    object, or a value that can be converted to one as if passed to
    {{jsxref('Temporal/PlainDate/from','Temporal.PlainDate.from()')}}.

### Return value

An integer indicating whether `dateTwo` comes before, comes after, or is equal
to `dateTwo`. The possible returned values are:

- `−1` if `dateOne` comes before `dateTwo`;
- `0` if `dateOne` and `dateTwo` represent the same date;
- `1` if `dateOne` comes after `dateTwo`.

## Examples

```js
one = Temporal.PlainDate.from('2006-08-24');
two = Temporal.PlainDate.from('2015-07-14');
Temporal.PlainDate.compare(one, two); // => -1
```

In the following example, `compare()` is used to sort an array of
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
objects.

```js
one = Temporal.PlainDate.from('2006-08-24');
two = Temporal.PlainDate.from('2015-07-14');
three = Temporal.PlainDate.from('1930-02-18');
sorted = [one, two, three].sort(Temporal.PlainDate.compare);
sorted.join(' | '); // => '1930-02-18 | 2006-08-24 | 2015-07-14'
```
