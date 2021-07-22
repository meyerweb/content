---
title: Temporal.PlainMonthDay constructor
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainMonthDay/constructor
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
{{jsxref('Temporal/PlainMonthDay','Temporal.PlainMonthDay')}}
object.The resulting month-and-day object is not associated with a specific
year, even if a specific year is used in its creation.

## Syntax

```js
new Temporal.PlainMonthDay(isoMonth, isoDay)
new Temporal.PlainMonthDay(isoMonth, isoDay, calendar)
new Temporal.PlainMonthDay(isoMonth, isoDay, calendar, referenceISOYear)
```

### Parameters

- `isoMonth`
  - : A number from 1 to 12 inclusive, identifying an ISO 8601 month.
    > **Note:** this is different from the legacy
    > {{jsxref('Date','Date','','nocode')}} API, where months are
    > represented by zero-based indices (0 to 11 inclusive).
- `isoDay`
  - : A number from 1 to 31 inclusive, identifying an ISO 8601 day of the month.
- `calendar` {{ optional_inline }}(see notes)
  - : A calendar to project the ISO 8601 date into, in order to reckon the date
    by that calendar's date system.
    > **Note:** if this parameter is anything other than the ISO 8601 calendar
    > (which is the default), it is **recommended** to include the
    > _referenceISOYear_ parameter.
- `referenceISOYear` {{ optional_inline }}(see note)
  - : A reference year in the ISO 8601 calendar, to be used for disambiguation.
    If this parameter is not supplied, the default value is the first leap year
    after the Unix epoch (i.e., 1972).
    > **Note:** this parameter is optional when using the ISO 8601 calendar, but
    > recommended for all other calendar systems. If you're not sure what value
    > to supply here, use
    > {{jsxref('Temporal/PlainMonthDay/from','Temporal.PlainMonthDay.from()')}}
    > instead.

The _calendar_ and _referenceISOYear_ parameters should generally be avoided
because `equals()` or `compare()` will consider
`new Temporal.PlainMonthDay(3, 14, 'iso8601', 1977)` and
`new Temporal.PlainMonthDay(3, 14, 'iso8601', 2000)` unequal, even though they
refer to the same month and day, because of the different years. When creating
instances for non-ISO-8601 calendars (except when implementing a custom
calendar) use the `from()` method which will automatically set a valid and
equals-compatible reference year.

### Return value

A new
{{jsxref('Temporal/PlainMonthDay','Temporal.PlainMonthDay')}}
object.

## Examples

```js
// Pi day
md = new Temporal.PlainMonthDay(3, 14); // => 03-14
// Leap day
md = new Temporal.PlainMonthDay(2, 29); // => 02-29
// Leap day error
```

```js example-bad
md = new Temporal.PlainMonthDay(2, 29, 'iso8601', 2021);
  // => Uncaught RangeError: value out of range: 1 <= 29 <= 28
```
