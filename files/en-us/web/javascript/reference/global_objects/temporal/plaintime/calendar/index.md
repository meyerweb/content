---
title: Temporal.PlainTime.prototype.calendar
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/calendar
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>calendar</code></strong> read-only property returns a {{jsxref('Temporal/Calendar','Temporal.Calendar')}} object containing the ISO 8601 calendar.</span> No other calendars are currently possible for <code>{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}</code>, but the property exists for purposes of future compatibility.</p>

## Syntax

```js
time.calendar
```

### Value

A {{jsxref('Temporal/Calendar','Temporal.Calendar')}} object
containing the ISO 8601 calendar.

## Examples

```js
time = Temporal.PlainTime.from('19:39:09.068346205');
time.calendar.id;  // => iso8601
// (the only possible calendar for PlainTime)
```
