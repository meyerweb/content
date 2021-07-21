---
title: Temporal.PlainYearMonth.prototype.toString()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainYearMonth/toString
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

Returns a string representing the month and day in ISO 8601 format.

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
        > `PlainYearMonth`'s calendar is not the ISO 8601 calendar. By setting
        > the `calendarName` option to `"always"` or `"never"`, this can be
        > overridden to always or never show the annotation, respectively.

### Return value

A string representing the month and day in ISO 8601 format.

## Examples

```js
ym = Temporal.PlainYearMonth.from('2021-04');
ym.toString(); // => "2021-04"
```

```js
ym = Temporal.PlainYearMonth.from('2021-04');
ym.toString({calendarName: "always"}); // => "2021-04[u-ca=iso8601]"
```
