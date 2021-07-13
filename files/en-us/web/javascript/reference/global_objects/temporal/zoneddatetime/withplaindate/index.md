---
title: Temporal.ZonedDateTime.prototype.withPlainDate()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/withPlainDate
tags:
  - Class
  - JavaScript
  - Time
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>withPlainDate()</code></strong> method returns a new <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> object which is a modification of the original date and time with a new date.</span> This method is similar to <code>{{jsxref('Temporal.ZonedDateTime/with','.with()')}}</code>, but with a few important differences:</p>

- `withPlainDate()` accepts strings, Temporal objects, or objects.
  `{{jsxref('Temporal.ZonedDateTime/with','.with()')}}` only
  accepts objects, and does not accept strings nor
  `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`
  objects, because they can contain calendar information.
- `withPlainDate()` updates all date units, whereas
  `{{jsxref('Temporal.ZonedDateTime/with','.with()')}}` only
  changes units that are present in the input object.

## Syntax

```js
withPlainDate(plainDate)
```

### Parameters

- `plainDate`
  - : The date that should replace the date of the original
    `{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`
    object. Valid input to `withPlainDate()` is the same as valid input to
    `{{jsxref('Temporal.PlainDate/from','Temporal.PlainDate.from()')}}`:
    strings like `2021-04-28`, plain objects like
    `{ year: 2021, month: 4, day: 28 }`, or Temporal objects that contain date
    unit properties, including
    `{{jsxref('Temporal.PlainDate','Temporal.PlainDate')}}`,
    `{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`,
    or
    `{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`.
    All three date units (`year`, `month` or `monthCode`, and `day`) are
    required.

### Return value

A new
`{{jsxref('Temporal/ZonedDateTime','Temporal.ZonedDateTime')}}`
object.

## Examples

```js
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24:30-08:00[America/Los_Angeles]');
zdt.withPlainDate({ year: 2000, month: 6, day: 1 });
  // => 2000-06-01T03:24:30-07:00[America/Los_Angeles]
date = Temporal.PlainDate.from('2020-01-23');
zdt.withPlainDate(date);
  // => 2020-01-23T03:24:30-08:00[America/Los_Angeles]
zdt.withPlainDate('2018-09-15');
  // => 2018-09-15T03:24:30-07:00[America/Los_Angeles]

// easier for chaining
zdt.add({ hours: 12 }).withPlainDate('2000-06-01');
  // => 2000-06-01T15:24:30-07:00[America/Los_Angeles]

// result contains a non-ISO calendar if present in the input
zdt.withCalendar('japanese').withPlainDate('2008-09-06');
  // => 2008-09-06T03:24:30-07:00[America/Los_Angeles][u-ca=japanese]
zdt.withPlainDate('2017-09-06[u-ca=japanese]');
  // => 2017-09-06T03:24:30-07:00[America/Los_Angeles][u-ca=japanese]
```

```js example-bad
/* WRONG */
zdt.withCalendar('japanese').withPlainDate('2017-09-06[u-ca=hebrew]');
  // => RangeError (calendar conflict)
```
