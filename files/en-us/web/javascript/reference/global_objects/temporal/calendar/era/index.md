---
title: Temporal.Calendar.prototype.era()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/era
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>era()</code></strong> method returns the era component of the supplied date, as determined by the calendar system associated with that date, assuming the calendar system uses eras.</span></p>

This method is called indirectly when reading the `era` properties of the
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`,
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`,
`{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`,
`{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}`,
and
`{{jsxref('Temporal.PlainYearMonth','Temporal.PlainYearMonth')}}`
classes. It is thus rare for developers to need to call
`Temporal.Calendar.era()` directly.

## Syntax

```js
era(date);
```

### Parameters

- `date`
  - : The _date_ parameter can be one of the following Temporal objects:
    - `{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}`
    - `{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
    - `{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}`
    - `{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}`
      If the parameter's value is not one of those objects, it will be converted
      to a
      `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
      as if it were passed to
      `{{jsxref('Temporal.PlainDate.from()','Temporal.PlainDate.from()')}}`.

### Return value

A string representing the date's era as determined by the date's calendar
system, or `undefined` if there is no era associated with the date. The
`iso8601` calendar has no eras, so `Temporal.Calendar.from('iso8601').era(date)`
always returns `undefined`.

## Examples

```js
date = Temporal.Calendar.from('gregory').dateFromFields(
  { year: 2021, month: 4, day: 20 }
);
date.era; // => "ce"
```

```js
date = Temporal.Calendar.from('gregory').dateFromFields(
  { year: -2021, month: 4, day: 20 }
);
date.era; // => "bce"
```
