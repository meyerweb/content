---
title: Temporal.PlainDate.prototype.toString()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/toString
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

The **`toString()`** method returns a string representing the date in ISO 8601
format.This method overrides the
{{jsxref('Object.toString','Object.prototype.toString()')}}
method and provides a convenient, unambiguous string representation of a date.
The string can be passed to
{{jsxref('Temporal.PlainDate/from','Temporal.PlainDate.from()')}}
to create a new
{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}} object.

## Syntax

```js
toString()
toString(options)
```

### Parameters

- `options` {{optional_inline}}
  - : An object with properties influencing the formatting. The following
    options are recognized:
    - `calendarName`
      - : Whether to show the calendar annotation in the return value. Valid
        values are `"auto"`, `"always"`, and `"never"`. The default is `"auto"`.
        > **Note:** Normally, a calendar annotation is shown when the
        > `PlainDate`'s calendar is not the ISO 8601 calendar. By setting the
        > `calendarName` option to `"always"` or `"never"`, this can be
        > overridden to always or never show the annotation, respectively.

### Return value

A string representing the date in ISO 8601 format.

## Examples

```js
date = Temporal.PlainDate.from('2021-04-27');
date.toString(); // => "2021-04-27"
```

```js
date = Temporal.PlainDate.from('2021-04-27');
date.toString({calendarName: "always"}); // => "2021-04-27[u-ca=iso8601]"
```
