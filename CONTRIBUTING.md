# Contributing

Contributions are welcome! The below notes are intended to give a quick overview of how this package works.
The main grammar file, `Babel Language` is a copy of the atom `language-babel` primary grammar file. The only change that has been made to this file is the pattern that matches Ember tagged templates using this syntax:

``layout: hbs`Some Template` ``

See the `#ember-htmlbars` entry in `Babel Language.json` for details.

### Naming Conventions:

- Parent level span is `meta.tag.htmlbars`, can be used for writing custom CSS for HTMLBars highlighting inside JS files.
- HTMLBars matches should end in `.htmlbars`

### Top Level Patterns

After an Ember template has been matched, the following top level patterns are used:

- #htmlbars-unescaped _(flags triple curlies)_
- #htmlbars-comment
- #htmlbars-block-open
- #htmlbars-block-close
- #htmlbars-inline
- #html-tag
- #html-comment-block
- #entities _(html entities eg: &amp;)_

##### Curlies Patterns
@TODO: Attempt to combine curly regexes for simplicity.

Utility patterns:
- #htmlbars-property-name -> Use for matching on any property name (instead of plain string.unescaped)


##### HTML Patterns
The `#html-comment-block` pattern matches on any opening and closing html tag. This pattern includes all of the patterns for html attributes as well as HTMLBars:

- #htmlbars-unescaped
- #htmlbars-comment
- #htmlbars-block-open
- #htmlbars-block-close
- #htmlbars-inline
- #tag-id-attribute
- #tag-generic-attribute
- #string-double-quoted
- #string-single-quoted
- #unquoted-attribute

There are three main attribute patterns:
- #tag-id-attribute -> Match on `id=` only (Includes quoted patterns)
- #tag-generic-attribute -> Match on any other attribute that is quoted (Includes quoted patterns)
- #unquoted-attribute -> Match on any other unquoted attribute VALUE

### TODO
- [] Combine regexes for htmlbars block open/close/inline if possible
- [x] Add appropriate comment syntax for htmlbars
- [] HTMLBars is not properly matching internal hbs props
- [x] Move htmlbars core to separate file
- [] Add real `increaseIndentPattern` && `decreaseIndentPattern` regexes in settings
- [x] Create a specific parsing rule for inline hbs instead of using quasi-js
- [x] Migrate html and htmlbars patterns to repo
- [x] Switch namespace for everything to `meta.tag.htmlbars`
- [x] Change HTMLBars to `source.htmlbars.js`
- [] Fix undefined grammer config
- [] Match variable names instead of unquoted string inside `{{concat "aria-labelledby-" elementId}}`
- [] Can we use the same patterns for attributes for HTML and Components?
- [x] Why does tag id have nested double string patterns?
- [x] Single Regex for open and close html elements

### TODO Cleanup
Top Level
- [x] #htmlbars-unescaped
- [x] #htmlbars-comment
- [] #htmlbars-block-open
- [] #htmlbars-block-close
- [] #htmlbars-inline
