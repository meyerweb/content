---
title: Temporal.PlainDate.prototype.era
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainDate/era
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

The **`era`** read-only property returns a string of the era in which the date
occurs, in calendar systems that use eras.

## Syntax

```js
date.era
```

### Value

A string rendering of the era's label, or `undefined` in calendar systems that
do not use eras.

## Examples

```js
date = Temporal.PlainDate.from('2019-02-23');
date.era; // => undefined

date = Temporal.PlainDate.from('2019-02-23[u-ca=gregory]');
date.era; // => "ce"
```
