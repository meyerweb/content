---
title: Temporal.PlainDate.prototype.equals()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/equals
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

<p class="summary"><span class="seoSummary">This method determines whether a <code>{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}</code> object is exactly the same as another date.</span> This function exists because it's not possible to compare using <code>PlainDate == other</code> or <code>PlainDate === other</code>, due to ambiguity in the primitive representation and between Temporal types.</p>

If you also need to know the order in which the two times occur when they are
not equal, use
`{{jsxref('Temporal/PlainDate/compare','Temporal.PlainDate.compare()')}}`
instead.

## Syntax

```js
equals(otherDate)
```

### Parameters

- `otherDate`
  - : Another date to compare. Either a
    `{{jsxref('Temporal/PlainDate','Temporal.PlainDate')}}`
    object, or a value that can be converted to one as if passed to
    `{{jsxref('Temporal/PlainDate.from()','Temporal.PlainDate.from()')}}`.

### Return value

A boolean `true` if the two dates are equal; otherwise, `false`. Note that this
function will return `false` if the two date objects have different calendar
properties, even if the actual dates are the same day.

## Examples

```js
date = Temporal.PlainDate.from('2006-08-24');
other = Temporal.PlainDate.from('2019-01-31');
date.equals(other); // => false
date.equals(date); // => true
```
