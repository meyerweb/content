---
title: Temporal.PlainTime.compare()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/compare
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

The **`compare()`** static method compares two times and returns an integer
indicating which comes before the other.

If you don't care about the order in which the two times occur, but instead
merely want to know if they're the same or not, use
{{jsxref('Temporal/PlainTime/equals','Temporal.PlainTime.equals()')}}
instead.

Note that time zone offset transitions, such as when Daylight Saving Time starts
or ends, can produce unexpected results when comparing times. This is because in
those situations, clock times can be skipped or repeated. Therefore,
{{jsxref('Temporal.ZonedDateTime.compare','Temporal.ZonedDateTime.compare')}}
(not `Temporal.PlainTime.compare`) should be used if the caller's actual intent
is to compare specific instants; e.g., the arrivals of two airplane flights.

## Syntax

```js
compare(timeOne, timeTwo)
```

### Parameters

- `timeOne`

  `timeTwo`

  - : Either a
    {{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}
    object, or a value that can be converted to one as if passed to
    {{jsxref('Temporal/PlainTime/from','Temporal.PlainTime.from()')}}.

### Return value

An integer indicating whether `timeOne` comes before, comes after, or is equal
to `timeTwo`. The possible returned values are:

- `−1` if `timeOne` comes before `timeTwo`;
- `0` if `timeOne` and `timeTwo` represent the same time and year;
- `1` if `timeOne` comes after `timeTwo`.

## Examples

```js
one = Temporal.PlainTime.from('03:24');
two = Temporal.PlainTime.from('01:24');
Temporal.PlainTime.compare(one, two); // => 1
```

In the following example, `compare()` is used to sort an array of
{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}
objects.

```js
one = Temporal.PlainTime.from('03:24');
two = Temporal.PlainTime.from('01:24');
three = Temporal.PlainTime.from('01:24:05');
sorted = [one, two, three].sort(Temporal.PlainTime.compare);
sorted.join(' | '); // => "01:24:00 | 01:24:05 | 03:24:00"
```

The following examples demonstrate differences between
`Temporal.PlainTime.compare` and
{{jsxref('Temporal.ZonedDateTime.compare','Temporal.ZonedDateTime.compare')}}.

```js
// Backward transitions will repeat clock times
zdtDst = Temporal.ZonedDateTime.from('2020-11-01T01:45-07:00[America/Los_Angeles]');
zdtStandard = Temporal.ZonedDateTime.from('2020-11-01T01:30-08:00[America/Los_Angeles]');
// The "first" 1:45 (in Daylight Time) is earlier than the "second" 1:30 (in Standard Time)
Temporal.ZonedDateTime.compare(zdtDst, zdtStandard); // => -1
// 1:45 is later than 1:30 when looking at a wall clock
Temporal.PlainTime.compare(zdtDst, zdtStandard); // => 1

// Forward transitions will skip clock times. Skipped times will be disambiguated.
zdtBase = Temporal.ZonedDateTime.from('2020-03-08[America/Los_Angeles]');
timeSkipped = Temporal.PlainTime.from('02:30');
timeValid = Temporal.PlainTime.from('03:30');
zdtSkipped = zdtBase.withPlainTime(timeSkipped);
zdtValid = zdtBase.withPlainTime(timeValid);
// The skipped time 2:30AM is disambiguated to 3:30AM, so the instants are equal
Temporal.ZonedDateTime.compare(zdtSkipped, zdtValid); // => 0
// 2:30 is earlier than 3:30 on a wall clock
Temporal.PlainTime.compare(timeSkipped, timeValid); // => -1
```
