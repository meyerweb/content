---
title: Temporal.PlainMonthDay.prototype.toLocaleString()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/PlainMonthDay/toLocaleString
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toLocaleString()</code></strong> method returns a human-readable, language-sensitive representation of the <code>{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}</code> value.</span> This method overrides {{jsxref('Object/toLocaleString','Object.prototype.toLocaleString()')}}.</p>

The calendar in the output locale (which is given by
`new Intl.DateTimeFormat(locales, options).resolvedOptions().calendar`) **must**
match the calendar of the
`{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}`
object, or this method will throw an exception. This is because it's not
possible to convert a
`{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}`
object from one calendar to another without more information. In order to ensure
that the output always matches the `PlainMonthDay`'s internal calendar, you must
either explicitly construct the `PlainMonthDay` with the locale's calendar, or
explicitly specify the calendar in the _options_ parameter (below).

## Syntax

```js
toLocaleString()
toLocaleString(locales)
toLocaleString(options)
toLocaleString(locales, options)
```

### Parameters

- `locales` {{optional_inline}}
  - : A string with a BCP 47 language tag, or an array of such strings. To use
    the browser's default locale, pass an empty array. Unicode extension are
    supported (for example "`en-US-u-ca-buddhist`"). For the general form and
    interpretation of the `locales` argument, see the
    {{jsxref("Global_Objects/Intl", "Intl",
			"#Locale_identification_and_negotiation", 1)}}
    page. The following Unicode extension keys are allowed:
    - `nu`
      - : Numbering system. Possible values include: "`arab`", "`arabext`",
        "`bali`", "`beng`", "`deva`", "`fullwide`", "`gujr`", "`guru`",
        "`hanidec`", "`khmr`", "`knda`", "`laoo`", "`latn`", "`limb`", "`mlym`",
        "`mong`", "`mymr`", "`orya`", "`tamldec`", "`telu`", "`thai`", "`tibt`".
    - `ca`
      - : Calendar. Possible values include: "`buddhist`", "`chinese`",
        "`coptic`", "`ethiopia`", "`ethiopic`", "`gregory`", "`hebrew`",
        "`indian`", "`islamic`", "`iso8601`", "`japanese`", "`persian`",
        "`roc`".
    - `hc`
      - : Hour cycle. Possible values include: "`h11`", "`h12`", "`h23`",
        "`h24`".
- `options` {{optional_inline}}
  - : An object with some or all of the following properties:
    <dl><dt><code>dateStyle</code></dt><dd>The date formatting style to use when calling <code>format()</code>.
    Possible values include:<ul><li>"<code>full</code>"</li><li>"<code>long</code>"</li><li>"<code>medium</code>"</li><li>"<code>short</code>"</li></ul><div class="notecard note"><p><code>dateStyle</code> can be used with <code>timeStyle</code>, but
    not with other options (e.g. <code>weekday</code>,
    <code>hour</code>, <code>month</code>, etc.).</p></div></dd><dt><code>timeStyle</code></dt><dd>The time formatting style to use when calling <code>format()</code>.
    Possible values include:<ul><li>"<code>full</code>"</li><li>"<code>long</code>"</li><li>"<code>medium</code>"</li><li>"<code>short</code>"</li></ul></dd><dd><div class="notecard note"><p><code>timeStyle</code> can be used with <code>dateStyle</code>, but
    not with other options (e.g. <code>weekday</code>,
    <code>hour</code>, <code>month</code>, etc.).</p></div></dd><dt><code>calendar</code></dt><dd>Calendar. Possible values include: "<code>buddhist</code>",
    "<code>chinese</code>", " <code>coptic</code>", "<code>ethiopia</code>",
    "<code>ethiopic</code>", "<code>gregory</code>", " <code>hebrew</code>",
    "<code>indian</code>", "<code>islamic</code>", "<code>iso8601</code>", "
    <code>japanese</code>", "<code>persian</code>", "<code>roc</code>".</dd><dt><code>dayPeriod</code></dt><dd>The way day periods should be expressed. Possible values include:
    "<code>narrow</code>", "<code>short</code>", " <code>long</code>".</dd><dt><code>numberingSystem</code></dt><dd>Numbering System. Possible values include: "<code>arab</code>",
    "<code>arabext</code>", " <code>bali</code>", "<code>beng</code>",
    "<code>deva</code>", "<code>fullwide</code>", " <code>gujr</code>",
    "<code>guru</code>", "<code>hanidec</code>", "<code>khmr</code>", "
    <code>knda</code>", "<code>laoo</code>", "<code>latn</code>",
    "<code>limb</code>", "<code>mlym</code>", " <code>mong</code>",
    "<code>mymr</code>", "<code>orya</code>", "<code>tamldec</code>", "
    <code>telu</code>", "<code>thai</code>", "<code>tibt</code>".</dd><dt><code>localeMatcher</code></dt><dd>The locale matching algorithm to use. Possible values are
    "<code>lookup</code>" and "<code>best fit</code>"; the default is
    "<code>best fit</code>". For information about this option, see the
    {{jsxref("Global_Objects/Intl", "Intl", "#Locale_negotiation", 1)}} page.</dd><dt><code>timeZone</code></dt><dd>The time zone to use. The only value implementations must recognize is
    "<code>UTC</code>"; the default is the runtime's default time zone.
    Implementations may also recognize the time zone names of the <a href="https://www.iana.org/time-zones">IANA time zone database</a>,
    such as "<code>Asia/Shanghai</code>", "<code>Asia/Kolkata</code>",
    "<code>America/New_York</code>".</dd><dt><code>hour12</code></dt><dd>Whether to use 12-hour time (as opposed to 24-hour time). Possible values
    are <code>true</code> and <code>false</code>; the default is locale
    dependent. This option overrides the <code>hc</code> language tag and/or
    the <code>hourCycle</code> option in case both are present.</dd><dt><code>hourCycle</code></dt><dd>The hour cycle to use. Possible values are "<code>h11</code>",
    "<code>h12</code>", "<code>h23</code>", or "<code>h24</code>". This option
    overrides the <code>hc</code> language tag, if both are present, and the
    <code>hour12</code> option takes precedence in case both options have been
    specified.</dd><dt><code>formatMatcher</code></dt><dd>The format matching algorithm to use. Possible values are
    "<code>basic</code>" and "<code>best fit</code>"; the default is
    "<code>best fit</code>". See the following paragraphs for information
    about the use of this property.</dd></dl>
    The following properties describe the date-time components to use in formatted
    output, and their desired representations. Implementations are required to
    support at least the following subsets:
    *   `weekday`, `year`, `month`,
        `day`, `hour`, `minute`,
        `second`
    *   `weekday`, `year`, `month`,
        `day`
    *   `year`, `month`, `day`
    *   `year`, `month`
    *   `month`, `day`
    *   `hour`, `minute`, `second`
    *   `hour`, `minute`
    Implementations may support other subsets, and requests will be negotiated
    against all available subset-representation combinations to find the best
    match. Two algorithms are available for this negotiation and selected by the
    `formatMatcher` property: A [fully
    specified "`basic`" algorithm](http://www.ecma-international.org/ecma-402/1.0/#BasicFormatMatcher) and an
    implementation-dependent "`best fit`" algorithm.
    *   `weekday`
        *   : The representation of the weekday. Possible values are:
            *   "`long`" (e.g., `Thursday`)
            *   "`short`" (e.g., `Thu`)
            *   "`narrow`" (e.g., `T`). Two weekdays may
                have the same narrow style for some locales (e.g.
                `Tuesday`'s narrow style is also `T`).
    *   `era`
        *   : The representation of the era. Possible values are:
            *   "`long`" (e.g., `Anno Domini`)
            *   "`short`" (e.g., `AD`)
            *   "`narrow`" (e.g., `A`)
    *   `year`
        *   : The representation of the year. Possible values are:
            *   "`numeric`" (e.g., `2012`)
            *   "`2-digit`" (e.g., `12`)
    *   `month`
        *   : The representation of the month. Possible values are:
            *   "`numeric`" (e.g., `2`)
            *   "`2-digit`" (e.g., `02`)
            *   "`long`" (e.g., `March`)
            *   "`short`" (e.g., `Mar`)
            *   "`narrow`" (e.g., `M`). Two months may have
                the same narrow style for some locales (e.g. `May`'s
                narrow style is also `M`).
    *   `day`
        *   : The representation of the day. Possible values are:
            *   "`numeric`" (e.g., `1`)
            *   "`2-digit`" (e.g., `01`)
    *   `hour`
        *   : The representation of the hour. Possible values are
            "`numeric`", "`2-digit`".
    *   `minute`
        *   : The representation of the minute. Possible values are
            "`numeric`", "`2-digit`".
    *   `second`
        *   : The representation of the second. Possible values are
            "`numeric`", "`2-digit`".
    *   `fractionalSecondDigits`
        *   : The number of digits used to represent fractions of a second (any
            additional digits are truncated). Possible values are:
            *   `0` (Fractional part dropped.)
            *   `1` (Fractional part represented as 1 digit. For
                example, 736 is formatted as `7`.)
            *   `2` (Fractional part represented as 2 digits. For
                example, 736 is formatted as `73`.)
            *   `3` (Fractional part represented as 3 digits. For
                example, 736 is formatted as `736`.)
    *   `timeZoneName`
        *   : The representation of the time zone name. Possible values are:
            *   "`long`" (e.g., `British Summer Time`)
            *   "`short`" (e.g., `GMT+1`)
    <p class="noinclude">The default value for each date-time component property is
    {{jsxref("undefined")}}, but if all component properties are
    {{jsxref("undefined")}}, then <code>year</code>, <code>month</code>, and
    <code>day</code> are assumed to be "<code>numeric</code>".</p>

### Return value

A string representation of the date in a localized format.

## Examples

```js
let calendar;
({ calendar } = new Intl.DateTimeFormat().resolvedOptions());
md = Temporal.PlainMonthDay.from({ monthCode: 'M08', day: 24, calendar });
md.toLocaleString(); // example output: '8/24'
// Same as above, but explicitly specifying the calendar:
md.toLocaleString(undefined, { calendar }); // example output: '8/24'

md.toLocaleString('de-DE', { calendar }); // => '24.8.'
md.toLocaleString('de-DE', { month: 'long', day: 'numeric', calendar }); // => '24. August'
md.toLocaleString(`en-US-u-nu-fullwide-ca-${calendar}`); // => '８/２４'
```
