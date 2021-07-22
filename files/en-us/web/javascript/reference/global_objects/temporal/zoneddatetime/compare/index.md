---
title: Temporal.ZonedDateTime.compare()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/compare
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

The **`compare()`** static method compares two dates and times, and returns an
integer indicating which comes before the other.

If you don't care about the order in which the two date occur, but instead
merely want to know if they're the same or not, use
{{jsxref('Temporal/ZonedDateTime/equals','Temporal.ZonedDateTime.equals()')}}
instead.

## Syntax

```js
compare(dateTimeOne, dateTimeTwo)
```

### Parameters

- `dateTimeOne`

  `dateTimeTwo`

  - : Either a
    {{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
    object, or a value that can be converted to one as if passed to
    {{jsxref('Temporal/ZonedDateTime/from','Temporal.ZonedDateTime.from()')}}.

### Return value

An integer indicating whether `dateTimeTwo` comes before, comes after, or is
equal to `dateTimeTwo`. The possible returned values are:

- `−1` if `dateTimeOne` comes before `dateTimeTwo`;
- `0` if `dateTimeOne` and `dateTimeTwo` represent the same exact time;
- `1` if `dateTimeOne` comes after `dateTimeTwo`.

The comparison uses exact time, not clock time, because sorting is almost always
based on when events happened in the real world. During the hour before and
after DST (Daylight Saving Time) transitions, sorting of clock time may not
match the order the events actually occurred.

## Examples

```js
one = Temporal.ZonedDateTime.from('2020-11-01T01:45-07:00[America/Los_Angeles]');
two = Temporal.ZonedDateTime.from('2020-11-01T01:15-08:00[America/Los_Angeles]');
Temporal.ZonedDateTime.compare(one, two);
  // => -1
  // (because `one` is earlier in the real world)
Temporal.PlainDateTime.compare(one.toPlainDateTime(), two.toPlainDateTime());
  // => 1
  // (because `one` is later in clock time)
Temporal.Instant.compare(one.toInstant(), two.toInstant());
  // => -1
  // (because `Temporal.Instant` and `Temporal.ZonedDateTime` both compare real-world exact times)
```
