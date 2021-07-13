---
title: Temporal.TimeZone.prototype.getNextTransition()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/TimeZone/getNextTransition
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

<p class="summary"><span class="seoSummary">The <strong><code>getNextTransition()</code></strong> method returns a <code>{{jsxref('Temporal/Instant','Temporal.Instant')}}</code> object representing the next DST (Daylight Saving Time) transition in a given time zone.</span></p>

When subclassing
`{{jsxref('Temporal/TimeZone','Temporal.TimeZone')}}`, this
method should be overridden if the time zone changes offsets. Single-offset time
zones can use the default implementation, which returns `null`.

## Syntax

```js
getNextTransition(startingInstant)
```

### Parameters

- `startingInstant`
  - : Time after which to find the next DST transition. If `startingInstant` is
    not a `{{jsxref('Temporal/Instant','Temporal.Instant')}}`
    object, then it will be converted to one as if it were passed to
    `{{jsxref('Temporal/Instant/from','Temporal.Instant.from()')}}`.

### Return value

A `{{jsxref('Temporal/Instant','Temporal.Instant')}}` object
representing the next DST transition in this time zone, or `null` if no
transitions later than `startingInstant` could be found. Note that if the time
zone was constructed from a UTC offset, there will be no DST transitions.

## Examples

```js
// How long until the next DST change from now, in the current location?
tz = Temporal.now.timeZone();
now = Temporal.now.instant();
nextTransition = tz.getNextTransition(now);
duration = nextTransition.since(now);
duration.toLocaleString(); // output will vary
```
