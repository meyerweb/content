---
title: Temporal.Duration.prototype.subtract()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/subtract
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

<p class="summary"><span class="seoSummary">The <strong><code>subtract()</code></strong> method creates a new <code>{{jsxref('Temporal/Duration','Temporal.Duration')}}</code> object by subtracting a duration from a <code>{{jsxref('Temporal/Duration','Temporal.Duration')}}</code> object.</span> Subtracting a negative duration is equivalent to {{jsxref('Temporal.Duration/add','adding')}} the absolute value of that duration.</p>

## Syntax

```js
subtract(duration)
subtract(duration, options)
```

### Parameters

- `duration`
  - : A `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object. If `duration` is not a
    `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
    object, then it will be converted to one as if it were passed to
    `{{jsxref('Temporal/Duration/from','Temporal.Duration.from()')}}`.
    This allows for values such as an object with properties appropriate for a
    duration, such as `{ hours: 5, minutes: 30 }`; or a string value such as
    `PT5H30M`.
- `options` {{optional_inline}}(see note)

  - : An object with properties representing options for the operation. The
    following option is recognized:

    - `relativeTo` \* : The starting point to use when subtracting years,
      months, weeks, and days. This is expressed as a
      `{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`
      or
      `{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
      object, or else a value convertible to one of those.

              If `relativeTo` is a `{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}` object, time zone offset changes will be taken into account when comparing days with hours. If `relativeTo` is a `{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}` object, then days are always considered equal to 24 hours.

              If `relativeTo` is neither a `{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}` nor a `{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`, it will be converted to one of the two as if it were first attempted with `{{jsxref('Temporal.ZonedDateTime/from','Temporal.ZonedDateTime.from()')}}` and then, if that fails, with `{{jsxref('Temporal.PlainDateTime/from','Temporal.PlainDateTime.from()')}}`.

      <div class="note">If any of the <code>years</code>, <code>months</code>, or <code>weeks</code> properties of either of the durations are nonzero, then the <code>relativeTo</code> option (and thus the <var>options</var> object) is <strong>required</strong>. This is because comparing durations with years, months, or weeks requires a point on the calendar to figure out how long they are.</div>

### Return value

A new `{{jsxref('Temporal/Duration','Temporal.Duration')}}`
object representing the difference of the durations.

## Examples

```js
time = Temporal.Duration.from('19:39:09.068346205');
time.subtract({ minutes: 5, nanoseconds: 800 }); // => 19:44:09.068347005
time.subtract({ hours: 12 }); // => <07:39:09.068346205>
```
