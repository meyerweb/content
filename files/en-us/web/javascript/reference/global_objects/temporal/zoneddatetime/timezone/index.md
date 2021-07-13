---
title: Temporal.ZonedDateTime.prototype.timeZone
slug: Web/JavaScript/Reference/Global_Objects/Temporal/ZonedDateTime/timeZone
tags:
  - Class
  - Date
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>timeZone</code></strong> read-only property represents the persistent time zone of the <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> object.</span> By storing its time zone, <code>{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}</code> is able to use that time zone when deriving other values, e.g. to automatically perform DST (Daylight Saving Time) adjustment when adding or subtracting time.</p>

The time zone is a required property when creating
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
instances. If you don't know the time zone of your underlying data, use
`{{jsxref('Temporal.Instant','Temporal.Instant')}}` and/or
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`,
neither of which have awareness of time zones. To change the time zone while
keeping the exact time constant, use the
`{{jsxref('Temporal.ZonedDateTime/withTimeZone','Temporal.ZonedDateTime.withTimeZone()')}}`
method.

Usually, the time zone ID is an IANA time zone ID. However, in unusual cases, a
time zone can also be created from a time zone offset string like `+05:30`.
Offset time zones function just like IANA time zones except that their offset
can never change due to DST or political changes. This can be problematic for
many use cases because by using an offset time zone you lose the ability to
safely derive past or future dates — even in time zones without DST, offsets
sometimes change for political reasons (e.g., countries change their time zone
or stop using DST). Therefore, using an IANA time zone ID is recommended
wherever possible.

In very rare cases, you may choose to use `UTC` as your time zone ID. This is
generally not advised because no humans actually live in the UTC time zone; it's
just for computers. Also, UTC has no DST and always has a zero offset, which
means that any action you'd take with
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
would return identical results to the same action on
`{{jsxref('Temporal.PlainDateTime','Temporal.PlainDateTime')}}`
or `{{jsxref('Temporal.Instant','Temporal.Instant')}}`.
Therefore, you should almost always use
`{{jsxref('Temporal.Instant','Temporal.Instant')}}` to represent
UTC times. When you want to convert UTC time to a real time zone, that's when
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
is useful.

## Syntax

```js
datetime.timeZone
```

### Value

An object representing the time zone of the zoned date and time. This will
depend on what kind of time zone information was used to construct the
`{{jsxref('Temporal.ZonedDateTime','Temporal.ZonedDateTime')}}`
object itself. In most cases, it will be a
`{{jsxref('Temporal.TimeZone','Temporal.TimeZone')}}` object,
but it could possibly be a plain object containing time zone information.

<div class="note"><p>Developers are <strong>strongly</strong> encouraged to make sure they construct the zoned date and time using a <code>{{jsxref('Temporal.TimeZone','Temporal.TimeZone')}}</code> object, or a value that is converted to one at construction time.</p></div>

## Examples

```js
zdt = Temporal.ZonedDateTime.from('1995-12-07T03:24-08:00[America/Los_Angeles]');
`Time zone is: ${zdt.timeZone}`;
  // => "Time zone is: America/Los_Angeles"
zdt.withTimeZone('Asia/Singapore').timeZone.toString();
  // => "Asia/Singapore"
zdt.withTimeZone('Asia/Chongqing').timeZone.toString();
  // => "Asia/Shanghai"
  // (time zone IDs are normalized, e.g. Asia/Chongqing -> Asia/Shanghai)
zdt.withTimeZone('+05:00').timeZone.toString();
  // => "+05:00"
zdt.withTimeZone('+05').timeZone.toString();
  // => "+05:00"
  // (normalized to canonical form)
zdt.withTimeZone('utc').timeZone.toString();
  // => "UTC"
  // (normalized to canonical form which is uppercase)
zdt.withTimeZone('GMT').timeZone.toString();
  // => "UTC"
  // (normalized to canonical form)
```
