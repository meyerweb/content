---
title: Temporal.ZonedDateTime.prototype.withTimeZone()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/withTimeZone
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

The **`withTimeZone()`** method returns a
{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}
object of a zoned date and time projected into a specified time zone.

## Syntax

```js
withTimeZone(timezone)
```

### Parameters

- `timezone`
  - : The time zone into which to project the zoned date and time. Can be
    represented by a
    {{jsxref('Temporal.TimeZone','Temporal.TimeZone')}} object,
    an object that implements the Temporal time zone protocol, or a string
    identifying a calendar.

### Return value

A new
{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}
object.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30+09:00[Asia/Tokyo]');
zdt.toString(); // => '1995-12-07T03:24:30+09:00[Asia/Tokyo]'
zdt.withTimeZone('Africa/Accra').toString(); // => '1995-12-06T18:24:30+00:00[Africa/Accra]'
```
