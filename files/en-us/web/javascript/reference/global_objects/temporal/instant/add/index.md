---
title: Temporal.Instant.prototype.add()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/add
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

<p class="summary"><span class="seoSummary">The <strong><code>add()</code></strong> method creates a new <code>{{jsxref('Temporal/Instant','Temporal.Instant')}}</code> object by adding a span of time to a <code>{{jsxref('Temporal/Instant','Temporal.Instant')}}</code> object.</span> Adding a negative duration to the instant is equivalent to {{jsxref('Temporal.Instant/subtract','subtracting')}} the absolute value of that duration.</p>

## Syntax

```js
add(duration)
```

### Parameters

- `duration`

  - : An object with properties denoting a duration, such as
    `{ hours: 5, minutes: 30 }`, or a string such as `PT5H30M`, or a
    `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object. If `duration` is not such a string nor a
    `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object, then it will be converted to one as if it were passed to
    `{{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}`.

    Note that the `years`, `months`, `weeks`, and `days` fields of `duration`
    must be zero.
    `{{jsxref('Temporal/Instant','Temporal.Instant')}}` is
    independent of time zones and calendars, and so years, months, weeks, and
    days may be different lengths depending on which calendar or time zone they
    are reckoned in. This makes an addition with those units ambiguous. If you
    need to do this, convert the
    `{{jsxref('Temporal/Instant','Temporal.Instant')}}` to a
    `{{jsxref('Temporal/PlainDateTime','Temporal.PlainDateTime')}}`
    by specifying the desired calendar and time zone, add the duration with
    `{{jsxref('Temporal/PlainDateTime/add','Temporal.PlainDateTime.add()')}}`,
    and then convert it back to
    `{{jsxref('Temporal/Instant','Temporal.Instant')}}`.

### Return value

A new `{{jsxref('Temporal/Instant','Temporal.Instant')}}` object
representing the exact time indicated by `instant` plus `duration`. If the
result is earlier or later than the range that
`{{jsxref('Temporal/Instant','Temporal.Instant')}}` can represent
(just over half a million years centered on the Unix epoch), a `RangeError` will
be thrown.

## Examples

```js
// Temporal.Instant representing five hours from now
Temporal.now.instant().add({ hours: 5 });
fiveHours = Temporal.Duration.from({ hours: 5 });
Temporal.now.instant().add(fiveHours);
```
