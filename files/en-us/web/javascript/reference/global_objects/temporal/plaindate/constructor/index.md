---
title: Temporal.PlainDate constructor
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/constructor
tags:
  - Class
  - JavaScript
  - Time
  - constructor
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The constructor for a <code>{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}</code> object.</span> Use this constructor if you have the correct parameters for the date as individual number values in the ISO 8601 calendar. Otherwise, use <code>{{jsxref('Temporal.PlainDate/from','Temporal.PlainDate.from()')}}</code>, which accepts more kinds of input and allows control of value overflow behaviour.</p>

## Syntax

```js
new Temporal.PlainDate(isoYear, isoMonth, isoDay)
new Temporal.PlainDate(isoYear, isoMonth, isoDay, calendar)
```

### Parameters

All values are given as reckoned in the ISO 8601 calendar. Together, `isoYear`,
`isoMonth`, and `isoDay` must represent a valid date in that calendar, even if
you are passing a different calendar as the `calendar` parameter.

- `isoYear`
  - : A year.
- `isoMonth`
  - : A number from 1 to 12 inclusive, identifying an ISO 8601 month.
    > **Note:** this is different from the legacy {{jsxref('Date')}} API,
    > where months are represented by zero-based indices (0 to 11 inclusive).
- `isoDay`
  - : A number from 1 to 31 inclusive, identifying an ISO 8601 day.
- `calendar` {{ optional_inline }}
  - : A calendar to project the ISO 8601 date into, in order to reckon the date
    by that calendar's date system.

### Return value

A new `{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}`
object.

## Examples

```js
// Pi day in 2021
date = new Temporal.PlainDate(2021, 3, 14); // => 2021-03-14
```
