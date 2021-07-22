---
title: Temporal.PlainYearMonth constructor
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/constructor
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - constructor
  - Time Zone
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

The constructor for a
{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}
object.The resulting year-and-month object is not associated with a specific day
in that month, even if a specific reference day is used in its creation.

It is **strongly** recommended that this constructor **SHOULD NOT** be used
except when implementing a custom calendar, or when only using the ISO 8601
calendar. For other calendars, use
{{jsxref('Temporal.PlainYearMonth/from','Temporal.PlainYearMonth.from()')}}.

## Syntax

```js
new Temporal.PlainYearMonth(isoYear, isoMonth)
new Temporal.PlainYearMonth(isoYear, isoMonth, calendar)
new Temporal.PlainYearMonth(isoYear, isoMonth, calendar, referenceISODay)
```

### Parameters

- `isoYear`
  - : A year.
- `isoMonth`
  - : A number from 1 to 12 inclusive, identifying an ISO 8601 month.
    > **Note:** this is different from the legacy
    > {{jsxref('Date','Date','','nocode')}} API, where months are
    > represented by zero-based indices (0 to 11 inclusive).
- `calendar` {{ optional_inline }}(see notes)
  - : A calendar to project the ISO 8601 date into, in order to reckon the date
    by that calendar's date system.
    > **Note:** if this parameter is anything other than the default value of
    > the ISO 8601 calendar, it is also **recommended** to include the
    > _referenceISODay_ parameter.
- `referenceISODay` {{ optional_inline }}(see note)
  - : A reference day, used for disambiguation when implementing calendar
    systems. For the ISO 8601 calendar, this parameter will default to `1`, if
    omitted. For other calendars, this parameter must be set to the ISO-calendar
    day corresponding to the first day of the desired calendar year and month.
    > **Note:** To avoid infinite recursion, `referenceISODay` is accepted
    > as-is, without validating that the day provided is actually the first day
    > of the month in the desired calendar system. This lack of validation means
    > that
    > {{jsxref('Temnporal.PlainYearMonth/equals','equals()')}}
    > or
    > {{jsxref('Temnporal.PlainYearMonth/compare','compare()')}}
    > may return `false` for `Temporal.PlainYearMonth` instances where the year
    > and month and day are identical, but the reference days don't match. By
    > contrast,
    > {{jsxref('Temporal.PlainYearMonth/from','Temporal.PlainYearMonth.from()')}}
    > will always correctly set the `referenceISODay` to the first of the month
    > when constructing the new object.

### Return value

A new
{{jsxref('Temporal/PlainYearMonth','Temporal.PlainYearMonth')}}
object. All values are given as reckoned in the ISO 8601 calendar. If _isoYear_
or _isoMonth_ are outside of the range of allowed values, then a `RangeError` is
thrown.

## Examples

```js
// The June 2019 meeting
ym = new Temporal.PlainYearMonth(2019, 6);
// => 2019-06
```
