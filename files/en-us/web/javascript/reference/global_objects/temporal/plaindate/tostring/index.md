---
title: Temporal.PlainDate.prototype.toString()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/toString
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toString()</code></strong> method returns a string representing the date in ISO 8601 format.</span> This method overrides the <code>{{jsxref('Object.toString','Object.prototype.toString()')}}</code> method and provides a convenient, unambiguous string representation of a date. The string can be passed to <code>{{jsxref('Temporal.PlainDate/from','Temporal.PlainDate.from()')}}</code> to create a new <code>{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}</code> object.</p>

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
        <div class="note"><p>Normally, a calendar annotation is shown when the <code>PlainDate</code>'s calendar is not the ISO 8601 calendar. By setting the <code>calendarName</code> option to <code>"always"</code> or <code>"never"</code>, this can be overridden to always or never show the annotation, respectively.</p></div>

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
