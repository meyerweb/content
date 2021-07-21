---
title: Temporal.ZonedDateTime.prototype.with()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/with
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

The **`with()`** method returns a new
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
object which is a modification of the original object using new property values.

## Syntax

```js
with(newValues)
with(newValues, options)
```

### Parameters

- `newValues`
  - : An object containing some of the properties accepted by
    {{jsxref('Temporal/ZonedDateTime/from','Temporal.ZonedDateTime.from()')}}.
    > **Note:** `calendar` and `timeZone` properties are not allowed on
    > _newValues_. See the methods
    > {{jsxref('Temporal/ZonedDateTime/withCalendar','withCalendar()')}}
    > and
    > {{jsxref('Temporal/ZonedDateTime/withTimeZone','withTimeZone()')}}.
- `options` {{optional_inline}}

  - : An object containing properties that represent options for constructing
    the new `Temporal.ZonedDateTime` object. These are:

    - `overflow`
      - : Determines how out-of-range values in _newValues_ are handled. There
        are two options:
        - `'constrain'` **(default)** – Out-of-range values are clamped to the
          nearest in-range value.
        - `'reject'` – Out-of-range values will cause the function to throw a
          `RangeError`.
    - `disambiguation`
      - : How to disambiguate if the date and time given by `dateTime` does not
        exist in the time zone, or exists more than once. Allowed values are:
        - `'compatible'` **(default)** – Acts like `'earlier'` for backward
          transitions and `'later'` for forward transitions.
        - `'earlier'` – The earlier of two possible times.
        - `'later'` – The later of two possible times.
        - `'reject'` – Throw a `RangeError` instead. When interoperating with
          existing code or services, `'compatible'` disambiguation matches the
          behavior of legacy {{jsxref('Date','Date','','nocode')}} as
          well as libraries like moment.js, Luxon, and date-fns. This mode also
          matches the behavior of cross-platform standards like RFC 5545
          (iCalendar).
          > **Note:** `disambiguation` is only used if there is no offset in the
          > input, or if the offset is ignored by using the `offset` option as
          > described above. If the offset in the input is used, then there is
          > no ambiguity and the `disambiguation` option is ignored.
    - `offset`

      - : How to interpret a provided time zone offset (e.g., `-02:00`) if it
        conflicts with the provided time zone (e.g., `America/Sao_Paulo`).
        Allowed values are:

        - `'use'` – Evaluate date/time values using the time zone offset if it's
          provided in the input. This will keep the exact time unchanged even if
          local time will be different than what was originally stored.
        - `'ignore'` – Never use the time zone offset provided in the input.
          Instead, calculate the offset from the time zone. This will keep local
          time unchanged but may result in a different exact time than was
          originally stored.
        - `'prefer'` **(default)** – Evaluate date/time values using the offset
          if it's valid for this time zone. If the offset is invalid, then
          calculate the offset from the time zone.
        - `'reject'` – Throw a `RangeError` if the offset is not valid for the
          provided date and time in the provided time zone. Unlike the
          {{jsxref('Temporal.ZonedDateTime/from','.from()')}}
          method where `offset` defaults to `'reject'`, the `offset` option in
          `.with()` defaults to `'prefer'`. This default prevents DST
          disambiguation from causing unexpected one-hour changes in exact time
          after making small changes to clock time fields.

        For example, if a
        {{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
        is set to the "second" 1:30AM on a day where the 1-2AM clock hour is
        repeated after a backwards DST (Daylight Saving Time) transition, then
        calling `.with({minute: 45})` will result in an ambiguity which is
        resolved using the default `offset: 'prefer'` option. Because the
        existing offset is valid for the new time, it will be retained so the
        result will be the "second" 1:45AM. However, if the existing offset is
        not valid for the new result (e.g. `.with({hour: 0})`), then the default
        behavior will change the offset to match the new local time in that time
        zone.

### Return value

A new
{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
object. If the result is earlier or later than the range of dates
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
can represent (approximately half a million years centered on the Unix epoch),
this method will throw a `RangeError` regardless of the value of `overflow`.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:00-06:00[America/Chicago]');
zdt.with({ year: 2015, minute: 31 }); // => 2015-12-07T03:31:00-06:00[America/Chicago]
```

As noted previously, if a `timeZone` or `calendar` property is included in the
`options` parameter, this function will throw an exception. To convert to a new
time zone while updating the clock time, use the
{{jsxref('Temporal/ZonedDateTime/withTimeZone','.withTimeZone()')}}
method, and to keep clock time as-is while resetting the time zone, use the
{{jsxref('Temporal/ZonedDateTime/toPlainTime','.toPlainDateTime()')}}
method instead. Examples:

```js
// update local time to match new time zone
const sameInstantInOtherTz = zdt.withTimeZone('Europe/London');
// create instance with same local time in a new time zone
const newTzSameLocalTime = zdt.toPlainDateTime().toZonedDateTime('Europe/London');
```
