# Babel + Inline HTMLBars Highlighting

Adds syntax highlighting for declaring templates using tagged template strings to the [language-babel](https://github.com/gandm/language-babel) package.

### Thank You
Thank you [language-babel](https://github.com/gandm/language-babel) and [language-ember-htmlbars](https://github.com/jmurphyau/language-ember-htmlbars) for the regex patterns.

## Features

- Comment Block Bindings
- Unescaped output (triple curlies) is flagged with wrapping `.unescaped.block.htmlbars`
- Property/Component/Helper names flagged as `string.of.property.function.component.name.htmlbars`
- All ember helpers flagged as `support.function.builtin.inline.htmlbars`
