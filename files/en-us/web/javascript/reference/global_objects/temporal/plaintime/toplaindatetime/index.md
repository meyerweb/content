---
title: Temporal.PlainTime.prototype.toPlainDateTime()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainTime/toPlainDateTime
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toPlainDateTime()</code></strong> method converts a <code>{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}</code> object into a <code>{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}</code> object, by supplying a date to be used with the wall-clock time of the original <code>{{jsxref('Temporal.PlainTime','Temporal.PlainTime')}}</code></span>.</p>

## Syntax

```js
toPlainDateTime(date)
```

### Parameters

- `date`
  - : An object representing the date into which the wall-clock time should be
    placed. If date is not a
    `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
    object, then it will be converted to one as if it were passed to
    `{{jsxref('Temporal.PlainDate/from','Temporal.PlainDate.from()')}}`.

### Return value

A
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`
object that represents the combination of date and time.

## Examples

```js
time = Temporal.PlainTime.from('15:23:30.003');
date = Temporal.PlainDate.from('2006-08-24');
time.toPlainDateTime(date); // => 2006-08-24T15:23:30.003
```
