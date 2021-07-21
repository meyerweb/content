---
title: Temporal.Duration
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - Duration
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

A `Temporal.Duration` object represents a span of time that can be used in
date/time arithmetic.A `Temporal.Duration` object can be constructed directly,
or returned from
{{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}.
It can also be obtained from the `since()` method of any other Temporal type
that supports arithmetic, and is used in those types' `add()` and `subtract()`
methods.

When printed, a `Temporal.Duration` object produces a string conforming to the
ISO 8601 notation for durations. Briefly, the ISO 8601 notation consists of a
`P` character, followed by years, months, weeks, and days, followed by a `T`
character, followed by hours, minutes, and seconds with a decimal part, each
with a single-letter suffix that indicates the unit. Any zero components may be
omitted. For more detailed information, see the ISO 8601 standard or
[the Wikipedia page](https://en.wikipedia.org/wiki/ISO_8601#Durations).

> **Warning:** According to the ISO 8601-1 standard, weeks are not allowed to
> appear together with any other units, and durations can only be positive, in
> string notation. As extensions to the standard, ISO 8601-2 allows a sign
> character at the start of the string, and allows combining weeks with other
> units, in string notation. If you intend to use strings such as `P3W1D`,
> `+P1M`, or `-PT2H`, this may cause interoperability problems with legacy
> codebases.

## Constructor

- {{jsxref('Temporal/Duration/constructor','new Temporal.Duration()')}}
  - : Creates a new `Temporal.Duration` object which represents a span of time.

## Instance Properties

- {{jsxref('Temporal/Duration/years','years')}}
  {{readonlyinline}}
  - : The value of the years component of the `Temporal.Duration` object.
- {{jsxref('Temporal/Duration/months','months')}}
  {{readonlyinline}}
  - : The value of the months component of the `Temporal.Duration` object.
- {{jsxref('Temporal/Duration/weeks','weeks')}}
  {{readonlyinline}}
  - : The value of the weeks component of the `Temporal.Duration` object.
- {{jsxref('Temporal/Duration/days','days')}}
  {{readonlyinline}}
  - : The value of the days component of the `Temporal.Duration` object.
- {{jsxref('Temporal/Duration/hours','hours')}}
  {{readonlyinline}}
  - : The value of the hours component of the `Temporal.Duration` object.
- {{jsxref('Temporal/Duration/minutes','minutes')}}
  {{readonlyinline}}
  - : The value of the minutes component of the `Temporal.Duration` object.
- {{jsxref('Temporal/Duration/seconds','seconds')}}
  {{readonlyinline}}
  - : The value of the seconds component of the `Temporal.Duration` object.
- {{jsxref('Temporal/Duration/milliseconds','milliseconds')}}
  {{readonlyinline}}
  - : The value of the milliseconds component of the `Temporal.Duration` object.
- {{jsxref('Temporal/Duration/microseconds','microseconds')}}
  {{readonlyinline}}
  - : The value of the microseconds component of the `Temporal.Duration` object.
- {{jsxref('Temporal/Duration/nanoseconds','nanoseconds')}}
  {{readonlyinline}}
  - : The value of the nanoseconds component of the `Temporal.Duration` object.
- {{jsxref('Temporal/Duration/sign','sign')}}
  {{readonlyinline}}
  - : Indicates the sign of the `Temporal.Duration` object.
- {{jsxref('Temporal/Duration/blank','blank')}}
  {{readonlyinline}}
  - : Indicates whether the `Temporal.Duration` object represents a duration of
    zero length.

## Static Methods

- {{jsxref('Temporal/Duration/from','from()')}}
  - : Creates a new `Temporal.Duration` object from another value.
- {{jsxref('Temporal/Duration/compare','compare()')}}
  - : Compares two durations and returns an integer indicating whether the first
    is shorter, longer, or the same as the second.

## Instance Methods

- {{jsxref('Temporal/Duration/with','with()')}}
  - : Returns a new `Temporal.Duration` object which is a modification of the
    original `Temporal.Duration` object using new property values.
- {{jsxref('Temporal/Duration/add','add()')}}
  - : Creates a new `Temporal.Duration` object by adding a duration to a
    `Temporal.Duration` object.
- {{jsxref('Temporal/Duration/subtract','subtract()')}}
  - : Creates a new `Temporal.Duration` object by subtracting a duration from a
    `Temporal.Duration` object.
- {{jsxref('Temporal/Duration/negated','negated()')}}
  - : Creates a new `Temporal.Duration` object by inverting the sign of the
    original duration.
- {{jsxref('Temporal/Duration/abs','abs()')}}
  - : Creates a new `Temporal.Duration` object equal to the absolute value of
    the original duration.
- {{jsxref('Temporal/Duration/round','round()')}}
  - : Creates a new `Temporal.Duration` object by rounding the original.
- {{jsxref('Temporal/Duration/total','total()')}}
  - : The number of instances of a particular time unit equal to the
    `Temporal.Duration` object.
- {{jsxref('Temporal/Duration/toLocaleString','toLocaleString()')}}
  - : Returns a human-readable, language-sensitive representation of the
    {{jsxref('Temporal.Duration','Temporal.Duration')}} value.
- {{jsxref('Temporal/Duration/toString','toString()')}}
  - : Returns a string representing the duration length in ISO 8601 format.
- {{jsxref('Temporal/Duration/toJSON','toJSON()')}}
  - : Returns a string representing the duration length in ISO 8601 format.
- {{jsxref('Temporal/Duration/valueOf','valueOf()')}}
  - : Overrides
    {{jsxref('Object/valueOf','Object.prototype.valueOf()')}}
    and **always** throws an exception.
