---
title: Temporal.now.instant()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/now/instant
tags:
  - Class
  - Date
  - Epoch
  - JavaScript
  - Time
  - now
  - Unix Epoch
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>instant()</code></strong> method returns an object representing the current system time. It works like the old-style JavaScript {{jsxref("date/now","<code>Date.now()</code>")}}, but with accuracy in nanoseconds instead of milliseconds.</span></p>

## Syntax

```js
instant()
```

### Parameters

None.

### Return value

A `Temporal.Instant` object representing the current system time, **without**
regard to calendar or time zone, measured in nanoseconds.

## Examples

```js
var timestamp = Temporal.now.instant();
```

```js
function log(topic, ...args) {
  const timestamp = Temporal.now.instant();
  console.log(`[${topic}] ${timestamp}: ${args.join(' ')}`);
}
log('info', 'You just logged a message with a timestamp');
// example output:
//   [info] 2021-05-17T21:27:46.071862989Z: You just logged a message with a timestamp
```
