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

<p class="summary"><span class="seoSummary">Returns a string representing the month and day in ISO 8601 format.</span></p>

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
        <div class="note"><p>Normally, a calendar annotation is shown when the <code>PlainYearMonth</code>'s calendar is not the ISO 8601 calendar. By setting the <code>calendarName</code> option to <code>"always"</code> or <code>"never"</code>, this can be overridden to always or never show the annotation, respectively.</p></div>

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
