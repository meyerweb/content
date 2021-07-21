---
title: Temporal.Calendar.prototype.id
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/id
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

The **`id`** read-only property returns an unambiguous identifier for the
calendar.When subclassing
{{jsxref('Temporal/Calendar','Temporal.Calendar')}}, this
property doesn't need to be overridden because the default implementation gives
the result of calling
{{jsxref('Temporal/Calendar/toString','Temporal.Calendar.toString()')}}.

## Syntax

```js
calendar.id;
```

### Value

A string containing an unambiguous identifier for the calendar. Effectively,
this is the canonicalized version of whatever `calendarIdentifier` was passed as
a parameter to
{{jsxref('Temporal/calendar/constructor','the constructor','','nocode')}}.

## Examples

```js
date = Temporal.Calendar.from('gregory');
date.id; // => "gregory"
```
