---
title: Temporal.PlainMonthDay.prototype.equals()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainMonthDay/equals
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

<p class="summary"><span class="seoSummary">The <strong><code>equals()</code></strong> method compares two <code>{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}</code> objects to determine if they are the same.</span> This method is provided because it's impossible to compare using <code>monthDay == other</code> or <code>monthDay === other</code>, due to ambiguity in the primitive representation and between Temporal types.</p>

Note that two
`{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}`s
expressed in different calendar systems will never be considered equal, because
it's impossible to tell whether they fall on the same day without knowing the
year.

## Syntax

```js
date.equals(otherDate)
```

### Parameters

- `otherDate`
  - : An object representing the date to which the original date is compared. If
    _otherDate_ is not a
    `{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}`
    object, it is converted to one as if it were passed to
    `{{jsxref('Temporal/PlainMonthDay/from','Temporal.PlainMonthDay.from()')}}`.

### Return value

A boolean.

## Examples

```js
md1 = new Temporal.PlainMonthDay(2, 29, 'iso8601');
md2 = new Temporal.PlainMonthDay(2, 29, 'gregory');
md3 = new Temporal.PlainMonthDay(2, 28);
md1.equals(md2); // => false (differing calendars)
md1.equals(md3); // => false (same calendar, different day)
```
