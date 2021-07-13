---
title: Temporal.ZonedDateTime.prototype.startOfDay
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/startOfDay
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>startOfDay</code></strong> read-only property returns a new <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> instance representing the earliest valid local clock time during the given calendar day and time zone.</span> The local time of the result is almost always <code>00:00</code>, but in rare cases it could be a later time e.g. if DST (Daylight Saving Time) starts at midnight in a time zone.</p>

## Syntax

```js
datetime.startOfDay
```

### Value

An
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
object.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('2020-01-01T12:00-08:00[America/Los_Angeles]').startOfDay;
  // => 2020-01-01T00:00:00-08:00[America/Los_Angeles]
zdt = Temporal.ZonedDateTime.from('2018-11-04T12:00-02:00[America/Sao_Paulo]').startOfDay;
  // => 2018-11-04T01:00:00-02:00[America/Sao_Paulo]
  // Note the 1:00AM start time because the first clock hour was skipped due to DST transition
  // that started at midnight.
```
