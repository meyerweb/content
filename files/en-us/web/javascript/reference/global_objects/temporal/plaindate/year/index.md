---
title: Temporal.PlainDate.prototype.year
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/year
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>year</code></strong> read-only property returns a number that identifies the year in which the date occurs.</span></p>

## Syntax

```js
date.year
```

### Value

A signed integer representing the number of years relative to a
calendar-specific anchor date.

<div class="note"><p>For calendars that use eras, the anchor is usually aligned with the latest era so that <code>eraYear === year</code> for all dates in that era. However, some calendars (like Japanese) may use a different anchor.</p></div>

## Examples

```js
date = Temporal.PlainDate.from('2019-02-23');
date.year; // => 2019

date = Temporal.PlainDate.from('2019-02-23[u-ca=hebrew]');
date.year; // => 5779
```
