---
title: Temporal.Calendar constructor
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/constructor
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - constructor
  - Time Zone
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The constructor for a <code>{{jsxref('Temporal/Calendar','Temporal.Calendar')}}</code> object.</span>
Use this constructor directly if you have a string that is known to be a correct built-in calendar identifier. If you have an ISO 8601 date-time string with a <code>[u-ca=<var>identifier</var>]</code> annotation, use <code>{{jsxref('Temporal.Calendar/from','Temporal.Calendar.from()')}}</code> instead.</p>

## Syntax

```js
new Temporal.Calendar(calendarIdentifier)
```

### Parameters

- `calendarIdentifier`

  - : A string which corresponds to a built-in calendar system. For a list of
    calendar identifiers, see the documentation for
    `{{jsxref('Intl/Locale/calendar','Intl.Locale.prototype.calendar')}}`.
    If `CalendarIdentifier` is not a built-in calendar, then a `RangeError` is
    thrown.

    Use this constructor directly if you have a string that is known to be a
    correct built-in calendar identifier. If you have an ISO 8601 date-time
    string with a `[u-ca=identifier]` annotation, then
    `{{jsxref('Temporal/Calendar/from','Temporal.Calendar.from()')}}`
    is more convenient than parsing the identifier out of the string.

### Return value

A new `{{jsxref('Temporal/Calendar','Temporal.Calendar')}}`
object.

## Examples

```js
cal = new Temporal.Calendar('iso8601');
cal = new Temporal.Calendar('gregory');

/* WRONG */
cal = new Temporal.Calendar('discordian'); // => throws, not a built-in calendar
```
