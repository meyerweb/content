---
title: Temporal.ZonedDateTime.prototype.year
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/year
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`year`** read-only property returns a number that identifies the year in
which the date and time occurs.

## Syntax

```js
datetime.year
```

### Value

A signed integer representing the number of years relative to a
calendar-specific anchor date.

> **Note:** For calendars that use eras, the anchor is usually aligned with the
> latest era so that `eraYear === year` for all dates in that era. However, some
> calendars (like Japanese) may use a different anchor.

## Examples

```js
datetime = Temporal.ZonedDateTime.from('2019-02-23');
datetime.year; // => 2019

datetime = Temporal.ZonedDateTime.from('2019-02-23[u-ca=hebrew]');
datetime.year; // => 5779
```
