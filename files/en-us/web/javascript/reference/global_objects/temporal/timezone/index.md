---
title: Temporal.TimeZone
slug: Web/JavaScript/Reference/Global_Objects/Temporal/TimeZone
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

The **`Temporal.TimeZone`** class provides an interface to working with IANA
time zones, a specific UTC offset, or UTC itself.Time zones translate from a
date/time in UTC to a local date/time. Because of this,
{{jsxref('Temporal/TimeZone','Temporal.TimeZone')}} can be used
to convert between
{{jsxref('Temporal/Instant','Temporal.Instant')}} and
{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
as well as finding out the offset at a specific
{{jsxref('Temporal/Instant','Temporal.Instant')}}.

## Constructor

- {{jsxref('Temporal/TimeZone/constructor','Temporal.Timezone()')}}
  - : Creates a new `Temporal.TimeZone` object which represents a specific time
    zone.

## Instance Properties

- {{jsxref('Temporal/TimeZone/id','id')}} {{readonlyinline}}
  - : Returns an unambigious time zone identifier from a `Temporal.TimeZone`
    object.

## Static Methods

- {{jsxref('Temporal/TimeZone/from','from()')}}
  - : A static method to create a new `Temporal.TimeZone` object from another
    value.

## Instance Methods

- {{jsxref('Temporal/TimeZone/getOffsetNanosecondsFor','getOffsetNanosecondsFor()')}}
  - : A method to return a number indicating the UTC offset of a given time in
    nanoseconds.
- {{jsxref('Temporal/TimeZone/getOffsetStringFor','getOffsetStringFor()')}}
  - : A method to return a formatted string indicating the UTC offset of a given
    time.
- {{jsxref('Temporal/TimeZone/getPlainDateTimeFor','getPlainDateTimeFor()')}}
  - : A method to return a
    {{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}
    object indicating the calendar date and wall-clock time of a given point in
    time.
- {{jsxref('Temporal/TimeZone/getInstantFor','getInstantFor()')}}
  - : A method to find the exact time in a time zone at the time of a given
    calendar date and wall-clock time, even those which may be "skipped" by a
    change to or from Daylight Saving Time (DST).
- {{jsxref('Temporal/TimeZone/getPossibleInstantsFor','getPossibleInstantsFor()')}}
  - : A method to find all the possible exact times that could correspond to a
    given calendar date and wall-clock time, even those which may be "skipped"
    by a change to or from Daylight Saving Time (DST)..
- {{jsxref('Temporal/TimeZone/getNextTransition','getNextTransition()')}}
  - : A method to return a
    {{jsxref('Temporal/Instant','Temporal.Instant')}} object
    representing the next DST (Daylight Saving Time) transition in a given time
    zone.
- {{jsxref('Temporal/TimeZone/getPreviousTransition','getPreviousTransition()')}}
  - : A method to return a
    {{jsxref('Temporal/Instant','Temporal.Instant')}} object
    representing the most recent past DST (Daylight Saving Time) transition in a
    given time zone.
- {{jsxref('Temporal/TimeZone/toString','toString()')}}
  - : A method that returns the string of the time zone's ID.
- {{jsxref('Temporal/TimeZone/toJSON','toJSON()')}}
  - : A method that returns the string of the time zone's ID.
