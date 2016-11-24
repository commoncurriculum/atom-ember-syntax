# Babel + Inline HTMLBars Highlighting

Adds syntax highlighting for declaring templates using tagged template strings to the [language-babel](https://github.com/gandm/language-babel) package.




### Thank You
Thank you [language-babel](https://github.com/gandm/language-babel) and [language-ember-htmlbars](https://github.com/jmurphyau/language-ember-htmlbars) for the regex patterns.


### TODO:
- [] Check if JSX has html patterns for use
- [] Change wrapping `meta.tag.htmlbars` to something more semantic?
- [x] Add appropriate comment syntax for htmlbars
- [] HTMLBars is not properly matching internal hbs props
- [x] Move htmlbars core to separate file
- [] Add real `increaseIndentPattern` && `decreaseIndentPattern` regexes in settings
- [x] Create a specific parsing rule for inline hbs instead of using quasi-js
- [x] Migrate html and htmlbars patterns to repo
