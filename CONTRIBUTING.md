# Contributing

Contributions are welcome!

### TODO:
- [] Check if JSX has html patterns for use
- [] Change wrapping `meta.tag.htmlbars` to something more semantic?
- [x] Add appropriate comment syntax for htmlbars
- [] HTMLBars is not properly matching internal hbs props
- [x] Move htmlbars core to separate file
- [] Add real `increaseIndentPattern` && `decreaseIndentPattern` regexes in settings
- [x] Create a specific parsing rule for inline hbs instead of using quasi-js
- [x] Migrate html and htmlbars patterns to repo
- [x] Switch namespace for everything to `meta.tag.htmlbars`
- [] Change HTMLBars to `source.htmlbars.js`
- [] Fix undefined grammer

Notes on Package:

##### Entry
Grammar entry begins with the Ember Language file which is a copy of the Language Babel file. There is a single entry, `ember-htmlbars`, that is the top level matching pattern for the Ember HTMLBars highlighting using: `hbs`. All htmlbars highlighting will be nested inside of a `meta.tag.htmlbars` span. This is the top pattern for the Ember tagged template highlighting.

The top level pattern includes the internals:

`source.htmlbars.js`
`internal.text.inline.htmlbars`

(These can be combined into a single file)

HTMLBars entry patterns:

- #htmlbars-unescaped
- #htmlbars-comment
- #htmlbars-block-open
- #htmlbars-block-close
- #htmlbars-inline


Utility patterns:
- #htmlbars-property-name -> Use for matching on any property name (instead of plain string.unescaped)



### Naming Conventions:

- Parent level span is `meta.tag.htmlbars`, can be used for writing custom CSS for HTMLBars highlighting inside JS files.
- HTMLBars matches should end in `.htmlbars`
