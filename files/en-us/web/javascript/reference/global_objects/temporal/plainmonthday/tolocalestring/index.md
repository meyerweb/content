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

The **`toLocaleString()`** method returns a human-readable, language-sensitive
representation of the
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}
value. This method overrides
{{jsxref('Object/toLocaleString','Object.prototype.toLocaleString()')}}.

The calendar in the output locale (which is given by
`new Intl.DateTimeFormat(locales, options).resolvedOptions().calendar`) **must**
match the calendar of the
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}
object, or this method will throw an exception. This is because it's not
possible to convert a
{{jsxref('Temporal.PlainMonthDay','Temporal.PlainMonthDay')}}
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
    - `dateStyle`
      - : The date formatting style to use when calling `format()`. Possible
        values include:
        - "`full`"
        - "`long`"
        - "`medium`"
        - "`short`"
          > **Note:** `dateStyle` can be used with `timeStyle`, but not with
          > other options (e.g. `weekday`, `hour`, `month`, etc.).
    - `timeStyle`
      - : The time formatting style to use when calling `format()`. Possible
        values include:
        - "`full`"
        - "`long`"
        - "`medium`"
        - "`short`"
          > **Note:** `timeStyle` can be used with `dateStyle`, but not with
          > other options (e.g. `weekday`, `hour`, `month`, etc.).
    - `calendar`
      - : Calendar. Possible values include: "`buddhist`", "`chinese`", "
        `coptic`", "`ethiopia`", "`ethiopic`", "`gregory`", " `hebrew`",
        "`indian`", "`islamic`", "`iso8601`", " `japanese`", "`persian`",
        "`roc`".
    - `dayPeriod`
      - : The way day periods should be expressed. Possible values include:
        "`narrow`", "`short`", " `long`".
    - `numberingSystem`
      - : Numbering System. Possible values include: "`arab`", "`arabext`", "
        `bali`", "`beng`", "`deva`", "`fullwide`", " `gujr`", "`guru`",
        "`hanidec`", "`khmr`", " `knda`", "`laoo`", "`latn`", "`limb`",
        "`mlym`", " `mong`", "`mymr`", "`orya`", "`tamldec`", " `telu`",
        "`thai`", "`tibt`".
    - `localeMatcher`
      - : The locale matching algorithm to use. Possible values are "`lookup`"
        and "`best fit`"; the default is "`best fit`". For information about
        this option, see the
        {{jsxref("Global_Objects/Intl", "Intl", "#Locale_negotiation", 1)}}
        page.
    - `timeZone`
      - : The time zone to use. The only value implementations must recognize is
        "`UTC`"; the default is the runtime's default time zone. Implementations
        may also recognize the time zone names of the
        [IANA time zone database](https://www.iana.org/time-zones), such as
        "`Asia/Shanghai`", "`Asia/Kolkata`", "`America/New_York`".
    - `hour12`
      - : Whether to use 12-hour time (as opposed to 24-hour time). Possible
        values are `true` and `false`; the default is locale dependent. This
        option overrides the `hc` language tag and/or the `hourCycle` option in
        case both are present.
    - `hourCycle`
      - : The hour cycle to use. Possible values are "`h11`", "`h12`", "`h23`",
        or "`h24`". This option overrides the `hc` language tag, if both are
        present, and the `hour12` option takes precedence in case both options
        have been specified.
    - `formatMatcher` \* : The format matching algorithm to use. Possible values
      are "`basic`" and "`best fit`"; the default is "`best fit`". See the
      following paragraphs for information about the use of this property. The
      following properties describe the date-time components to use in formatted
      output, and their desired representations. Implementations are required to
      support at least the following subsets:
    - `weekday`, `year`, `month`, `day`, `hour`, `minute`, `second`
    - `weekday`, `year`, `month`, `day`
    - `year`, `month`, `day`
    - `year`, `month`
    - `month`, `day`
    - `hour`, `minute`, `second`
    - `hour`, `minute` Implementations may support other subsets, and requests
      will be negotiated against all available subset-representation
      combinations to find the best match. Two algorithms are available for this
      negotiation and selected by the `formatMatcher` property: A
      [fully specified "`basic`" algorithm](https://www.ecma-international.org/ecma-402/1.0/#BasicFormatMatcher)
      and an implementation-dependent "`best fit`" algorithm.
    - `weekday`
      - : The representation of the weekday. Possible values are:
        - "`long`" (e.g., `Thursday`)
        - "`short`" (e.g., `Thu`)
        - "`narrow`" (e.g., `T`). Two weekdays may have the same narrow style
          for some locales (e.g. `Tuesday`'s narrow style is also `T`).
    - `era`
      - : The representation of the era. Possible values are:
        - "`long`" (e.g., `Anno Domini`)
        - "`short`" (e.g., `AD`)
        - "`narrow`" (e.g., `A`)
    - `year`
      - : The representation of the year. Possible values are:
        - "`numeric`" (e.g., `2012`)
        - "`2-digit`" (e.g., `12`)
    - `month`
      - : The representation of the month. Possible values are:
        - "`numeric`" (e.g., `2`)
        - "`2-digit`" (e.g., `02`)
        - "`long`" (e.g., `March`)
        - "`short`" (e.g., `Mar`)
        - "`narrow`" (e.g., `M`). Two months may have the same narrow style for
          some locales (e.g. `May`'s narrow style is also `M`).
    - `day`
      - : The representation of the day. Possible values are:
        - "`numeric`" (e.g., `1`)
        - "`2-digit`" (e.g., `01`)
    - `hour`
      - : The representation of the hour. Possible values are "`numeric`",
        "`2-digit`".
    - `minute`
      - : The representation of the minute. Possible values are "`numeric`",
        "`2-digit`".
    - `second`
      - : The representation of the second. Possible values are "`numeric`",
        "`2-digit`".
    - `fractionalSecondDigits`
      - : The number of digits used to represent fractions of a second (any
        additional digits are truncated). Possible values are:
        - `0` (Fractional part dropped.)
        - `1` (Fractional part represented as 1 digit. For example, 736 is
          formatted as `7`.)
        - `2` (Fractional part represented as 2 digits. For example, 736 is
          formatted as `73`.)
        - `3` (Fractional part represented as 3 digits. For example, 736 is
          formatted as `736`.)
    - `timeZoneName` _ : The representation of the time zone name. Possible
      values are: _ "`long`" (e.g., `British Summer Time`) \* "`short`" (e.g.,
      `GMT+1`) The default value for each date-time component property is
      {{jsxref("undefined")}}, but if all component properties are
      {{jsxref("undefined")}}, then `year`, `month`, and `day` are
      assumed to be "`numeric`".

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
