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

The **`year`** read-only property returns a number that identifies the year in
which the date occurs.

## Syntax

```js
date.year
```

### Value

A signed integer representing the number of years relative to a
calendar-specific anchor date.

> **Note:** For calendars that use eras, the anchor is usually aligned with the
> latest era so that `eraYear === year` for all dates in that era. However, some
> calendars (like Japanese) may use a different anchor.

## Examples

```js
date = Temporal.PlainDate.from('2019-02-23');
date.year; // => 2019

date = Temporal.PlainDate.from('2019-02-23[u-ca=hebrew]');
date.year; // => 5779
```
