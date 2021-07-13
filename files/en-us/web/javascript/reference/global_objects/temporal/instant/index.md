---
title: Temporal.Instant
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - now
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>Temporal.Instant</code></strong> class provides an interface to create, compare, and manipulate single points in time (called <dfn>"exact time"</dfn>), with a precision in nanoseconds. No time zone or calendar information is present. As such <code>Temporal.Instant</code> has no concept of years, months, or even days.</span></p>

## Constructor

- `{{jsxref('Temporal/Instant/constructor','Temporal.Instant()')}}`
  - : Creates a new `Temporal.Instant` object which represents a specific
    instant in time.

## Instance Properties

- `{{jsxref('Temporal/Instant/epochSeconds','epochSeconds')}}`
  {{readonlyinline}}
  - : The number of seconds between the Unix epoch and the `Temporal.Instant`
    object's time.
- `{{jsxref('Temporal/Instant/epochMilliseconds','epochMilliseconds')}}`
  {{readonlyinline}}
  - : The number of milliseconds between the Unix epoch and the
    `Temporal.Instant` object's time.
- `{{jsxref('Temporal/Instant/epochMicroseconds','epochMicroseconds')}}`
  {{readonlyinline}}
  - : The number of microseconds between the Unix epoch and the
    `Temporal.Instant` object's time.
- `{{jsxref('Temporal/Instant/epochNanoseconds','epochNanoseconds')}}`
  {{readonlyinline}}
  - : The number of nanoseconds between the Unix epoch and the
    `Temporal.Instant` object's time.

## Static Methods

- `{{jsxref('Temporal/Instant/from','from()')}}`
  - : Creates a new `Temporal.Instant` object from another such object, or a
    string representing a point in time.
- `{{jsxref('Temporal/Instant/fromEpochSeconds','fromEpochSeconds()')}}`
  - : Creates a new `Temporal.Instant` object from a number of seconds from the
    Unix epoch.
- `{{jsxref('Temporal/Instant/fromEpochMilliseconds','fromEpochMilliseconds()')}}`
  - : Creates a new `Temporal.Instant` object from a number of milliseconds from
    the Unix epoch.
- `{{jsxref('Temporal/Instant/fromEpochMicroseconds','fromEpochMicroseconds()')}}`
  - : Creates a new `Temporal.Instant` object from a number of microseconds from
    the Unix epoch.
- `{{jsxref('Temporal/Instant/fromEpochNanoseconds','fromEpochNanoseconds()')}}`
  - : Creates a new `Temporal.Instant` object from a number of nanoseconds from
    the Unix epoch.
- `{{jsxref('Temporal/Instant/compare','compare()')}}`
  - : Compares two points in time and returns an integer indicating which comes
    before the other.

## Instance Methods

- `{{jsxref('Temporal/Instant/toZonedDateTime','toZonedDateTime()')}}`
  - : Converts a `Temporal.Instant` object into a
    `{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
    object.
- `{{jsxref('Temporal/Instant/toZonedDateTimeISO','toZonedDateTimeISO()')}}`
  - : Converts a `Temporal.Instant` object into a
    `{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
    object using the ISO 8601 calendar.
- `{{jsxref('Temporal/Instant/add','add()')}}`
  - : Adds an amount of time and a `Temporal.Instant` object together to yield a
    new `Temporal.Instant` object.
- `{{jsxref('Temporal/Instant/equals','equals()')}}`
  - : Determines whether a `Temporal.Instant` object is exactly the same as
    another time value.
- `{{jsxref('Temporal/Instant/round','round()')}}`
  - : Creates a new `Temporal.Instant` object by rounding the current
    `Temporal.Instant` object.
- `{{jsxref('Temporal/Instant/since','since()')}}`
  - : Computes the elapsed time between the `Temporal.Instant` exact time and
    another, optionally rounds it, and returns it as a
    `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object.
- `{{jsxref('Temporal/Instant/subtract','subtract()')}}`
  - : Subtracts an amount of time from a `Temporal.Instant` object to yield a
    new `Temporal.Instant` object.
- `{{jsxref('Temporal/Instant/until','until()')}}`
  - : Computes the elapsed time between the `Temporal.Instant` exact time and
    another exact time, optionally rounds it, and returns it as a
    `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object.
- `{{jsxref('Temporal/Instant/toLocaleString','toLocaleString()')}}`
  - : Returns a human-readable, language-sensitive representation of the
    instant.
- `{{jsxref('Temporal/Instant/toJSON','toJSON()')}}`
  - : Returns a string representing the instant in ISO 8601 format.
- `{{jsxref('Temporal/Instant/toString','toString()')}}`
  - : Returns a string representing the instant in ISO 8601 format.
- `{{jsxref('Temporal/Instant/valueOf','valueOf()')}}`
  - : Overrides
    `{{jsxref('Object/valueOf','Object.prototype.valueOf')}}`.
    **Always** throws an exception.
