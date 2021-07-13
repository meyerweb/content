---
title: Temporal.Duration.prototype.toLocaleString()
slug: Web/JavaScript/Reference/Global_Objects/Temporal/Duration/toLocaleString
tags:
  - Class
  - Date
  - Time
  - JavaScript
  - timeStamp
---
{{JSRef}}

<p class="summary"><span class="seoSummary">The <strong><code>toLocaleString()</code></strong> method returns a human-readable, language-sensitive representation of the <code>{{jsxref('Temporal.Duration','Temporal.Duration')}}</code> value.</span> This method overrides {{jsxref('Object/toLocaleString','Object.prototype.toLocaleString()')}}.</p>

<div class="warning"><p>This method requires that your JavaScript environment supports <code>Intl.DurationFormat</code>. If <code>`Intl.DurationFormat`</code> is not available, then the output of this method is the same as that of <code>{{jsxref('Temporal/Duration/toString','Temporal.Duration.toString()')}}</code>, and the <code>locales</code> and <code>options</code> arguments are ignored.</p></div>

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
- `options` {{optional_inline}}
  - : An object with some or all of the following properties:
    - `style`
      - : The formatting style to use when calling `format()`. Possible values
        include:
        - "`long`"
        - "`short`"
        - "`narrow`"
        - "`digital`"
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
    - `smallestUnit`
      - : <!-- TK -->This is still being determined in the
        \`Intl.DurationFormat\` proposal.
    - `largestUnit`
      - : <!-- TK -->This is still being determined in the
        \`Intl.DurationFormat\` proposal.
    - `hideZeroValued`
      - : <!-- TK -->This is still being determined in the
        \`Intl.DurationFormat\` proposal.

### Return value

A string containing a language-sensitive, localized representation of the
duration.

## Examples

```js
d = Temporal.Duration.from('P1DT6H30M');
d.toLocaleString(); // example output: '1 day 6 hours 30 minutes'
d.toLocaleString('de-DE'); // example output: '1 Tag 6 Stunden 30 Minuten'
d.toLocaleString('en-US', { smallestUnit: 'hour' }); // example output: '1 day 6 hours'
```
