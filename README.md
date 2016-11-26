# Babel + Inline HTMLBars Highlighting

Extends the [language-babel](https://github.com/gandm/language-babel) package to add syntax highlighting for declaring Ember templates using tagged template strings. All HTMLBars highlighting will be nested inside of a `meta.tag.htmlbars` span.

Ember component test files are automatically generated set up for the tagged template string syntax, eg:

```javascript
this.render(hbs`
  {{#some-component}}
    Syntax highlighting is the best.
  {{/some-component}}
`);
```

You can also declare your components for components using a tagged template string and the `layout` property:

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

_Note: If you are using the `language-babel` package you may have to disable it for this package to take effect._

## Features

- Maintains [language-babel](https://github.com/gandm/language-babel) ES6 && JSX syntax highlighting
- HTMLBars Comment Block Bindings on `Cmd + /`
- Unescaped output (triple curlies) is flagged with wrapping `.unescaped.block.htmlbars`
- Property/Component/Helper names flagged as `string.of.property.function.component.name.htmlbars`
- All framework Ember helpers flagged as `support.function.builtin.inline.htmlbars`

![Screenshot](https://raw.githubusercontent.com/DHedgecock/language-ember/master/screenshot.png)

See `CONTRIBUTING.md` for technical details.

### Thank You
Thank you [language-babel](https://github.com/gandm/language-babel) and [language-ember-htmlbars](https://github.com/jmurphyau/language-ember-htmlbars) for the regex patterns.
