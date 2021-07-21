---
title: Temporal.PlainDateTime.prototype.withPlainDate()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDateTime/withPlainDate
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

The **`withPlainDate()`** method returns a new
{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
object which is a modification of the original date and time with a new
date.This method is similar to
{{jsxref('Temporal.PlainDateTime/with','with()')}}, but with a
few important differences:

- `withPlainDate()` accepts strings, Temporal objects, or objects.
  {{jsxref('Temporal.PlainDateTime/with','with()')}} only
  accepts objects, and does not accept strings nor
  {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
  objects, because they can contain calendar information.
- `withPlainDate()` updates all date units, whereas
  {{jsxref('Temporal.PlainDateTime/with','with()')}} only
  changes units that are present in the input object.

## Syntax

```js
withPlainDate(plainDate)
```

### Parameters

- `plainDate`
  - : The date that should replace the date of the original
    {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}
    object. Valid input to `withPlainDate()` is the same as valid input to
    {{jsxref('Temporal.PlainDateTime/from','Temporal.PlainDateTime.from()')}}:
    strings like `2021-04-28`, plain objects like
    `{ year: 2021, month: 4, day: 28 }`, or Temporal objects that contain date
    unit properties, including
    {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}},
    {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}},
    or
    {{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}.
    All three date units (`year`, `month`, and `day`) are required.

### Return value

A new
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
object.

## Examples

```js
dt = Temporal.PlainDateTime.from('1995-12-07T03:24:30');
dt.withPlainDate({ year: 2000, month: 6, day: 1 }); // => 2000-06-01T03:24:30
// easier for chaining
dt.add({ hours: 12 }).withPlainDate('2000-06-02'); // => 2000-06-02T15:24:30
dt.withPlainDate('2018-09-15'); // => 2018-09-15T03:24:30

date = Temporal.PlainDate.from('2020-01-23');
dt.withPlainDate(date); // => 2020-01-23T03:24:30

// result contains a non-ISO calendar if present in the input
dt.withCalendar('japanese').withPlainDate('2008-09-06');
  // => 2008-09-06T03:24:30[u-ca=japanese]
dt.withPlainDate('2017-09-06[u-ca=japanese]');
  // => 2017-09-06T03:24:30[u-ca=japanese]
```

```js example-bad
/* WRONG */
dt.withCalendar('japanese').withPlainDate('2017-09-06[u-ca=hebrew]');
  // => RangeError (calendar conflict)
```
