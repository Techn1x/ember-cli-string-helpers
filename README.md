# ember-cli-string-helpers
![Download count all time](https://img.shields.io/npm/dt/ember-cli-string-helpers.svg) [![CircleCI](https://circleci.com/gh/romulomachado/ember-cli-string-helpers.svg?style=shield)](https://circleci.com/gh/romulomachado/ember-cli-string-helpers) [![npm version](https://badge.fury.io/js/ember-cli-string-helpers.svg)](https://badge.fury.io/js/ember-cli-string-helpers) [![Ember Observer Score](http://emberobserver.com/badges/ember-cli-string-helpers.svg)](http://emberobserver.com/addons/ember-cli-string-helpers)

String helpers for Ember. Extracted from the great [DockYard's ember-composable-helpers](https://github.com/DockYard/ember-composable-helpers/).

To install:

```no-highlight
ember install ember-cli-string-helpers
```

## Configuration

If you don't need all the helpers, you can specify which to whitelist or blacklist using `only` or `except` within your `ember-cli-build.js`:

```js
module.exports = function(defaults) {
  var app = new EmberApp(defaults, {
    'ember-cli-string-helpers': {
      only: ['dasherize', 'underscore'],
      except: ['titleize', 'capitalize']
    }
  });
};
```

Both `only` and `except` can be safely used together (the addon computes the diff), although it's best if you only use one for your own sanity.

```js
except: ['camelize'] // imports all helpers except `camelize`
only: ['camelize'] // imports only `camelize`
```

## Available helpers

* [`camelize`](#camelize)
* [`capitalize`](#capitalize)
* [`classify`](#classify)
* [`dasherize`](#dasherize)
* [`html-safe`](#html-safe)
* [`humanize`](#humanize)
* [`includes`](#includes)
* [`lowercase`](#lowercase)
* [`titleize`](#titleize)
* [`trim`](#trim)
* [`truncate`](#truncate)
* [`underscore`](#underscore)
* [`uppercase`](#uppercase)
* [`w`](#w)

## Usage

#### `camelize`
Camelizes a string using `Ember.String.camelize`.

```hbs
{{camelize "hello jim bob"}}
{{camelize stringWithDashes}}
```

**[⬆️ back to top](#available-helpers)**

#### `capitalize`
Capitalizes a string using `Ember.String.capitalize`.

```hbs
{{capitalize "hello jim bob"}}
{{capitalize fullName}}
```

**[⬆️ back to top](#available-helpers)**

#### `classify`
Classifies a string using `Ember.String.classify`.

```hbs
{{classify "hello jim bob"}}
{{classify stringWithDashes}}
```

**[⬆️ back to top](#available-helpers)**

#### `dasherize`
Dasherizes a string using `Ember.String.dasherize`.

```hbs
{{dasherize "whatsThat"}}
{{dasherize phrase}}
```

**[⬆️ back to top](#available-helpers)**

#### `html-safe`
Mark a string as safe for unescaped output with Ember templates using `Ember.String.htmlSafe`.

```hbs
{{html-safe "<div>someString</div>"}}
{{html-safe unsafeString}}
```

**[⬆️ back to top](#available-helpers)**

#### `humanize`
Removes dashes and underscores from a string, capitalizes the first letter and makes the rest of the string lower case.

```hbs
{{humanize "some-string"}}
{{humanize phrase}}
```

**[⬆️ back to top](#available-helpers)**

#### `includes`
Check whether a phrase contains a substring. The phrase can also be a string array.

```hbs
{{includes "some" "this is some string right here"}}
{{includes "some" (array "this" "is" "some" "string" "right" "here")}}
{{includes string phrase}}
```

**[⬆️ back to top](#available-helpers)**


#### `lowercase`
Lowercases a string.

```hbs
{{lowercase "People Person's Paper People"}}
{{lowercase phrase}}
```

**[⬆️ back to top](#available-helpers)**

#### `titleize`
Capitalizes every word separated by a white space or a dash.

```hbs
{{titleize "my big fat greek wedding"}}
{{titleize phrase}}
```

**[⬆️ back to top](#available-helpers)**

#### `trim`
Trim a string.

```hbs
{{trim "  Lorem ipsum dolor sit amet, consectetur adipiscing elit.   "}}
{{trim phrase}}
```

#### `truncate`
Truncates a string with a characterLimit and optionally adds an ellipsis to the end.

```hbs
{{truncate "Lorem ipsum dolor sit amet, consectetur adipiscing elit." 20 true}}
{{truncate phrase characterLimit useEllipsis}}
```

**[⬆️ back to top](#available-helpers)**

#### `underscore`
Capitalizes a string using `Ember.String.underscore`.

```hbs
{{underscore "whatsThat"}}
{{underscore phrase}}
```

**[⬆️ back to top](#available-helpers)**

#### `uppercase`
Uppercases a string.

```hbs
{{uppercase "loud noises"}}
{{uppercase phrase}}
```

**[⬆️ back to top](#available-helpers)**

#### `w`
Splits a string on whitespace and/or turns multiple words into an array.

```hbs
{{#each (w "First" "Second" "Last") as |rank|}}
  Our {{rank}} place winner is ...
{{/each}}
```

or:

```hbs
{{#each (w "First Second Last") as |rank|}}
  Our {{rank}} place winner is ...
{{/each}}
```

See also: [Ember `w` documentation](http://emberjs.com/api/classes/Ember.String.html#method_w)

**[⬆️ back to top](#available-helpers)**

## See also:

* [ember-composable-helpers](https://github.com/dockyard/ember-composable-helpers)
* [ember-truth-helpers](https://github.com/jmurphyau/ember-truth-helpers)

## Legal

[Licensed under the MIT license](http://www.opensource.org/licenses/mit-license.php)
