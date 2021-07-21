---
title: Temporal.Instant.prototype.epochSeconds
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Instant/epochSeconds
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

The **`epochSeconds`** read-only property returns the number of seconds between
the Unix epoch and the
{{jsxref('Temporal/Instant','Temporal.Instant')}} object.The
number of seconds since the Unix epoch is a common measure of exact time in many
computer systems. Use this property if you need to interface with such a system.

## Syntax

```js
instant.epochSeconds
```

### Value

An integer representation of the number of seconds between the Unix epoch
(midnight UTC on January 1, 1970) and `instant`. The number of seconds is
truncated towards zero.

## Examples

```js
instant = Temporal.Instant.from('2019-03-30T01:45+01:00');
instant.epochSeconds; // => 1554000300
```
