# Ember HTMLBars Highlighting

This package provides HMLBars/Glimmer syntax highlighting for template (`.hbs`)
files as well as inline template declaration in JS files.

### Template File Highlighting

To activate syntax highlighting in template files select `Ember HTMLBars` as the language.

### Inline Template Highlighting

##### With `language-babel`

If you're using the [language-babel](https://github.com/gandm/language-babel)
package you can continue using `language-babel` to highlight your JavaScript and
add support for inline templates using the _JavaScript Tagged Template Literal
Grammar Extensions_ feature in `language-babel`. This feature adds syntax
highlighting to any tagged template strings preceded by a pattern you specify.
Simply add:

`hbs:source.htmlbars`

**`language-babel` has a 10 second debounce on generating new grammar extensions,
  be sure to wait until the confirmation notice pops up!**

_(This will target any template literal with `hbs` preceding it, and apply the
  `source.htmlbars` grammar to the contents.)_

##### Without `language-babel`

If you're not using the language-babel extension, then select`ES6
JavaScript (Babel) + JSX && Ember HTMLBars` as your JS default language.

### Using Inline Template Declaration

Ember component test files are automatically generated set up for the tagged template string syntax, eg:

```javascript
this.render(hbs`
  {{#some-component}}
    Syntax highlighting is the best.
  {{/some-component}}
`);
```

You can also declare templates for components using a tagged template string and the `layout` property:

```javascript
import Ember from 'ember';
import hbs from 'htmlbars-inline-precompile';

export default Ember.component.extend({
  // Component layout using tagged template string:
  layout: hbs`
    <span>Hello there, {{name}}</span>
  `
});
```

### Features

- Maintains [language-babel](https://github.com/gandm/language-babel) ES6 && JSX syntax highlighting
- HTMLBars Comment Block Bindings on `Cmd + /`
- Unescaped output (triple curlies) is flagged with wrapping `.unescaped.block.htmlbars`
- Property/Component/Helper names flagged as `string.of.property.function.component.name.htmlbars`
- All framework Ember helpers flagged as `support.function.builtin.inline.htmlbars`

![Screenshot](https://raw.githubusercontent.com/DHedgecock/language-ember/master/screenshot.png)

See `CONTRIBUTING.md` for technical details.

### Thank You
Thank you [language-babel](https://github.com/gandm/language-babel) and [language-ember-htmlbars](https://github.com/jmurphyau/language-ember-htmlbars) for the regex patterns.
