---
title: Temporal.ZonedDateTime.from()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/from
tags: – Class – JavaScript – date
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>from()</code></strong> static method creates a new <code>{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}</code> object from another value.</span></p>

## Syntax

```js
from(dateTime)
from(dateTime, options)
```

### Parameters

- `dateTime`

  - : A representation of the desired date and time, either as an object or as a
    string in valid ISO 8601 format. If the value is another
    `{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
    object, a new object representing the same date is returned.

    If the value is any other object, it must contain, at a minimum:

    - A `year` or `eraYear` property.

      - If `eraYear` is used, an `era` must also be supplied.

    - Either a `month` or a `monthCode` property.
    - A `day` property.
    - A `timeZone` property. The object may also contain a `calendar` property;
      if omitted, the ISO 8601 calendar is used. For non-ISO 8601 calendars, the
      calendar is also parsed in addition to year and month.

    Any non-object, non-string value will be converted to a string, which is
    expected to be in ISO 8601 format. Missing optional properties' values
    default to `0`. Any other parts of the string, such as those relating to
    time or time zone, are optional. If the string is invalid according to ISO
    8601, then a `RangeError` will be thrown regardless of the value of the
    `overflow` option (see next).

- `options` {{optional_inline}}
  - : An object containing properties that represent options for constructing
    the new `Temporal.ZonedDateTime` object. These are:
    - `overflow`
      - : Determines how out-of-range values in _dateTime_ are handled. There
        are two options:
        - `'constrain'` **(default)** – Out-of-range values are clamped to the
          nearest in-range value.
        - `'reject'` – Out-of-range values will cause the function to throw a
        `RangeError`.
        <div class="note"><p>If <var>dateTime</var> is a string, the <code>overflow</code> property's value is ignored.</p></div>
        <div class="warning"><strong>NOTE:</strong> Although Temporal does not deal with leap seconds, times coming from other software may have a <code>second</code> value of <code>60</code>. In the default <code>constrain</code> mode, this will be converted to <code>59</code>. In <code>reject</code> mode, the constructor will throw, so if you have to interoperate with times that may contain leap seconds, don't use <code>reject</code>. However, if parsing an ISO 8601 string with a seconds component of <code>:60</code>, then it will always result in a <code>second</code> value of <code>59</code>, in accordance with POSIX.</div>
    - `disambiguation`
      - : How to disambiguate if the date and time given by `dateTime` does not
        exist in the time zone, or exists more than once. Allowed values are:
        - `'compatible'` **(default)** – Acts like `'earlier'` for backward
          transitions and `'later'` for forward transitions.
        - `'earlier'` – The earlier of two possible times.
        - `'later'` – The later of two possible times.
        - `'reject'` – Throw a `RangeError` instead. When interoperating with
        existing code or services, `'compatible'` disambiguation matches the
        behavior of legacy {{jsxref('Date','Date')}} as well as libraries
        like moment.js, Luxon, and date-fns. This mode also matches the behavior
        of cross-platform standards like RFC 5545 (iCalendar).
        <div class="note"><p><code>disambiguation</code> is only used if there is no offset in the input, or if the offset is ignored by using the <code>offset</code> option as described above. If the offset in the input is used, then there is no ambiguity and the <code>disambiguation</code> option is ignored.</p></div>
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
        - `'prefer'` – Evaluate date/time values using the offset if it's valid
          for this time zone. If the offset is invalid, then calculate the
          offset from the time zone. This option is rarely used when calling
          `from()`. See the documentation of
          `{{jsxref('Temporal.ZonedDateTime/with','with()')}}`
          for more details about why this option is used.
        - `'reject'` **(default)** – Throw a `RangeError` if the offset is not
          valid for the provided date and time in the provided time zone.

### Return value

A new
`{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}`
object. If the result is earlier or later than the range of dates
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
can represent (approximately half a million years centered on the Unix epoch),
this function will throw a `RangeError` regardless of the value of `overflow`.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30+02:00[Africa/Cairo]');
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30+02:00[Africa/Cairo][u-ca=islamic]');
zdt = Temporal.ZonedDateTime.from({
    timeZone: 'America/Los_Angeles',
    year: 1995,
    month: 12,
    day: 7,
    hour: 3,
    minute: 24,
    second: 30,
    millisecond: 0,
    microsecond: 3,
    nanosecond: 500
});  // => 1995-12-07T03:24:30.0000035-08:00[America/Los_Angeles]

zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30+02:00[+02:00]');  // OK (offset time zone) but rarely used

// Different overflow modes
zdt = Temporal.ZonedDateTime.from({ timeZone: 'Europe/Paris', year: 2001, month: 13, day: 1 }, { overflow: 'constrain' })
  // => 2001-12-01T00:00:00+01:00[Europe/Paris]
```

```js example-bad
zdt = Temporal.ZonedDateTime.from({ timeZone: 'Europe/Paris', year: 2001, month: 13, day: 1 }, { overflow: 'reject' })
  // => throws RangeError: value out of range

zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30');
  // => throws RangeError: time zone ID required

zdt = Temporal.ZonedDateTime.from('1995-12-07T01:24:30Z');
  // => throws RangeError: time zone ID required

zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30+02:00');
  // => throws RangeError: time zone ID required

zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30+03:00[Africa/Cairo]');
  // => RangeError: Offset is invalid for '1995-12-07T03:24:30' in 'Africa/Cairo'. Provided: +03:00, expected: +02:00.
```
