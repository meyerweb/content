---
title: Temporal.Calendar.from()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Calendar/from
tags:
  - Class
  - Date
  - JavaScript
  - Time
---
{{JSRef}}

The **`from()`** static method creates a new
{{jsxref('Temporal/Calendar','Temporal.Calendar')}} object from
another value. This function is often more convenient to use than
{{jsxref('Temporal/Calendar','new Temporal.Calendar()')}}
because it handles a wider range of input.

## Syntax

```js
from(input);
```

### Parameters

- `input`

  - : A Temporal object that implements the calendar protocol, or any value that
    can be converted to a string.

    If _input_ is another
    {{jsxref('Temporal/Calendar','Temporal.Calendar')}} object,
    or a Temporal object that implements the calendar protocol, the same object
    is returned. If the value is another Temporal object that carries a calendar
    or an object with a calendar property, such as a
    {{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}},
    the object's calendar is returned.

    Any other value is converted to a string, which is expected to be either:

    - a string that is accepted by new
      {{jsxref('Temporal/Calendar','Temporal.Calendar()')}};
      or
    - a string in the ISO 8601 format Note that an ISO 8601 string can be
      extended with a `[u-ca=identifier]` annotation appended to it. Without
      such an annotation, the calendar is assumed to be `iso8601`.

### Return value

A {{jsxref('Temporal/Calendar','Temporal.Calendar')}} object.

## Examples

```js
// Calendar names
cal = Temporal.Calendar.from('iso8601');
cal = Temporal.Calendar.from('gregory');

// ISO 8601 string with or without calendar annotation
cal = Temporal.Calendar.from('2020-01-13T16:31:00.065858086');
cal = Temporal.Calendar.from('2020-01-13T16:31:00.065858086-08:00[America/Vancouver][u-ca=iso8601]');

// Existing calendar object
cal2 = Temporal.Calendar.from(cal);

// Temporal object that carries a calendar
properties = { year: 2000, month: 1, day: 1, calendar: cal };
date = Temporal.PlainDate.from(properties);
cal3 = Temporal.Calendar.from(date);  // cal3 === cal

// Object with a calendar property
cal4 = Temporal.Calendar.from(properties);  // cal4 === cal


/* WRONG */
cal = Temporal.Calendar.from('discordian'); // => throws, not a built-in calendar
/* WRONG */
cal = Temporal.Calendar.from('[u-ca-iso8601]'); // => throws, lone annotation not a valid ISO 8601 string
```
