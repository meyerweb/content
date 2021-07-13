---
title: Temporal.PlainTime
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">A <code>Temporal.PlainTime</code> object represents a wall-clock time, with a precision in nanoseconds, and without any time zone.</span> "Wall-clock time" refers to the concept of a time as expressed in everyday usage; that is, the time that you read off the clock on the wall. For example, it could be used to represent an event that happens daily at a certain time, no matter what the time zone. If you need to refer to a specific time on a specific day, use <code>{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}</code>.</p>

## Constructor

- `new {{jsxref('Temporal/PlainTime/constructor','Temporal.PlainTime()')}}`
  - : Creates a new `Temporal.PlainTime` object which represents a wall-clock
    time.

## Instance Properties

- `{{jsxref('Temporal/PlainTime/hour','hour')}}`
  {{readonlyinline}}
  - : A number that identifies the hour component of the `Temporal.PlainTime`
    object.
- `{{jsxref('Temporal/PlainTime/minute','minute')}}`
  {{readonlyinline}}
  - : A number that identifies the minute component of the `Temporal.PlainTime`
    object.
- `{{jsxref('Temporal/PlainTime/second','second')}}`
  {{readonlyinline}}
  - : A number that identifies the second component of the `Temporal.PlainTime`
    object.
- `{{jsxref('Temporal/PlainTime/millisecond','millisecond')}}`
  {{readonlyinline}}
  - : A number that identifies the millisecond component of the
    `Temporal.PlainTime` object.
- `{{jsxref('Temporal/PlainTime/microsecond','microsecond')}}`
  {{readonlyinline}}
  - : A number that identifies the microsecond component of the
    `Temporal.PlainTime` object.
- `{{jsxref('Temporal/PlainTime/nanosecond','nanosecond')}}`
  {{readonlyinline}}
  - : A number that identifies the nanosecond component of the
    `Temporal.PlainTime` object.
- `{{jsxref('Temporal/PlainTime/calendar','calendar')}}`
  {{readonlyinline}}
  - : A {{jsxref('Temporal/Calendar','Temporal.Calendar')}}
    object containing the ISO 8601 calendar.

## Static Methods

- `{{jsxref('Temporal/PlainTime/from','from()')}}`
  - : Creates a new
    `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
    object from another value.
- `{{jsxref('Temporal/PlainTime/compare','compare()')}}`
  - : Compares two times and returns an integer indicating which comes before
    the other.

## Instance Methods

- `{{jsxref('Temporal/PlainTime/with','with()')}}`
  - : Returns a new
    `{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}`
    object which is a modification of the original object using new property
    values.
- `{{jsxref('Temporal/PlainTime/add','add()')}}`
  - : Creates a new
    `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
    object by adding a duration to a
    `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
    object.
- `{{jsxref('Temporal/PlainTime/subtract','subtract()')}}`
  - : Creates a new
    `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
    object by subtracting a duration from a
    `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
    object.
- `{{jsxref('Temporal/PlainTime/until','until()')}}`
  - : Computes the elapsed time from the month represented by `PlainTime` until
    another wall-clock time, optionally rounds it, and returns it as a
    `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object.
- `{{jsxref('Temporal/PlainTime/since','since()')}}`
  - : Computes the elapsed time from the wall-clock time represented by
    `PlainTime` since another wall-clock time, optionally rounds it, and returns
    it as a
    `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object.
- `{{jsxref('Temporal/PlainTime/round','round()')}}`
  - : Creates a new
    `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
    object by rounding the time.
- `{{jsxref('Temporal/PlainTime/equals','equals()')}}`
  - : Determines whether a
    `{{jsxref('Temporal/PlainTime','Temporal.PlainTime')}}`
    object is exactly the same as another wall-clock time.
- `{{jsxref('Temporal/PlainTime/toZonedDateTime','toZonedDateTime()')}}`
  - : Converts a
    `{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}`
    object into a
    `{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
    object.
- `{{jsxref('Temporal/PlainTime/toPlainDateTime','toPlainDateTime()')}}`
  - : Converts a
    `{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}`
    object into a
    `{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`
    object, by supplying a date to be used with the wall-clock time of the
    original
    `{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}`.
- `{{jsxref('Temporal/PlainTime/toLocaleString','toLocaleString()')}}`
  - : Returns a human-readable, language-sensitive representation of the
    `{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}`
    value.
- `{{jsxref('Temporal/PlainTime/toString','toString()')}}`
  - : Returns a string representing the wall-clock time in ISO 8601 format.
- `{{jsxref('Temporal/PlainTime/toJSON','toJSON()')}}`
  - : Returns a string representing the wall-clock time in ISO 8601 format.
- `{{jsxref('Temporal/PlainTime/getISOFields','getISOFields()')}}`
  - : Returns an object containing the ISO 8601 calendar fields and values that
    correspond to the wall-clock time.
- `{{jsxref('Temporal/PlainTime/valueOf','valueOf()')}}`
  - : Overrides
    `{{jsxref('Object/valueOf','Object.prototype.valueOf()')}}`
    and **always** throws an exception.
