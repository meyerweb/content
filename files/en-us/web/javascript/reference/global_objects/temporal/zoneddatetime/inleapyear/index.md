---
title: Temporal.ZonedDateTime.prototype.inLeapYear
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/inLeapYear
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>inLeapYear</code></strong> read-only property indicates whether the date occurs in a leap year.</span></p>

## Syntax

```js
datetime.inLeapYear
```

### Value

A boolean value of `true` if the date occurs in a leap year, or `false` if not.

## Examples

```js
datetime = Temporal.ZonedDateTime.from('2019-02-23T01:23:45');
datetime.inLeapYear; // => false

datetime = Temporal.ZonedDateTime.from('2019-02-23T01:23:45[u-ca=hebrew]');
datetime.inLeapYear; // => true
```
