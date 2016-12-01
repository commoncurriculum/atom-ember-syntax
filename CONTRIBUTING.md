# Contributing

Contributions are welcome! The below notes are intended to give a quick overview of how this package works.
The main grammar file, `Babel Language` is a copy of the atom `language-babel` primary grammar file. The only change that has been made to this file is the pattern that matches Ember tagged templates using this syntax:

``layout: hbs`Some Template` ``

See the `#ember-htmlbars` entry in `Babel Language.json` for details.

### Naming Conventions:

- `.hbs` file scopeName is `.source.htmlbars`
- `.js` template string scope is `meta.tag.htmlbars`
- HTMLBars matches should end in `.htmlbars`

### Top Level Patterns

After an Ember template has been matched, the following top level patterns are used:

- #htmlbars-unescaped _(triple curlies)_
- #htmlbars-comment _(htmlbars comments)_
- #htmlbars-block _(htmlbars block && inline)_
- #html-tag _(any html tag)_
- #html-comment-block _(html comments)_
- #entities _(html entities eg: &amp;)_

##### Curlies Patterns

- #as-keyword
- #as-params
- #htmlbars-subexp
- #htmlbars-property
- #htmlbars-property-value
- #string-single-quoted
- #string-double-quoted


##### HTML Patterns
The `#html-tag` pattern matches on any opening or closing html tag. This pattern
includes all of the patterns for html attributes as well as HTMLBars expressions
for attribute values.

- #htmlbars-unescaped
- #htmlbars-comment
- #htmlbars-block
- #html-attribute
- #string-double-quoted
- #string-single-quoted
- #unquoted-attribute-value

The contents of any html tag will match first on htmlbars expressions, then
attributes, then the values of attributes will match on either strings or
unquoted. If the value of an attribute is an htmlbars expression it will have
already matched on the htmlbars patterns.

### TODO
- [] Cleanup htmlbars component names vs props vs helpers patterns: htmlbars-property-name, variable
- [x] Combine regexes for htmlbars block open/close/inline if possible
- [x] Add appropriate comment syntax for htmlbars
- [x] Move htmlbars core to separate file
- [] Add real `increaseIndentPattern` && `decreaseIndentPattern` regexes in settings
- [x] Create a specific parsing rule for inline hbs instead of using quasi-js
- [x] Migrate html and htmlbars patterns to repo
- [x] Switch namespace for everything to `meta.tag.htmlbars`
- [x] Change HTMLBars to `source.htmlbars.js`
- [] Match variable names instead of unquoted string inside `{{concat "aria-labelledby-" elementId}}`
- [] Can we use the same patterns for attributes for HTML and Components?
- [x] Why does tag id have nested double string patterns?
- [x] Single Regex for open and close html elements
