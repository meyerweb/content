---
title: Temporal.ZonedDateTime.prototype.withCalendar()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/withCalendar
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>withCalendar()</code></strong> method returns a <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> object of a zoned date and time projected into a specified calendar.</span></p>

## Syntax

```js
withCalendar(calendar)
```

### Parameters

- `calendar`
  - : The calendar into which to project the zoned date and time. Can be
    represented by a
    `{{jsxref('Temporal.Calendar','Temporal.Calendar')}}`
    object, an object that implements the Temporal calendar protocol, or a
    string identifying a calendar.

### Return value

A new
`{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}`
object.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30.000003500+09:00[Asia/Tokyo][u-ca=japanese]');
`${zdt.era} ${zdt.eraYear}`; // => 'heisei 7'
zdt.withCalendar('gregory').eraYear; // => 1995
```
