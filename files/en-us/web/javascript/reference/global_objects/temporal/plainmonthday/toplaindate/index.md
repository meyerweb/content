---
title: Temporal.PlainMonthDay.prototype.toPlainDate()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainMonthDay/toPlainDate
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`toPlainDate()`** method converts a
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}
object into a
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} object,
by supplying a year to be used with the month and day of the original
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}.

## Syntax

```js
toPlainDate(year)
```

### Parameters

- `year`
  - : An object representing the year into which the date should be placed. In
    most cases, this means an object with a `year` property, the value of which
    is a year in the used calendar system. In calendars where more than just a
    year is needed, such as those calendars which use eras, the object should
    contain the necessary properties.

### Return value

A {{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}
object that represents the new calendar date.

## Examples

```js
md = Temporal.PlainMonthDay.from('02-29');
md.toPlainDate({ year: 2020 }); // => 2020-02-29
md.toPlainDate({ year: 2017 }); // => 2017-02-28
```

```js
md = Temporal.PlainMonthDay.from({
  calendar: 'japanese',
  monthCode: 'M01',
  day: 1
});

date = md.toPlainDate({ era: 'reiwa', eraYear: 2 }); // => 2020-01-01[u-ca=japanese]
```
