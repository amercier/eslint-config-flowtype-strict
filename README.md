# eslint-config-flowtype-strict

> ESLint [shareable config] for [eslint-plugin-flowtype]: [recommended] + more rules.

[![Latest Stable Version](https://img.shields.io/npm/v/eslint-config-flowtype-strict.svg)](https://www.npmjs.com/package/eslint-config-flowtype-strict)
[![Build Status](https://img.shields.io/travis/amercier/eslint-config-flowtype-strict/master.svg)](https://travis-ci.org/amercier/eslint-config-flowtype-strict)
[![Greenkeeper](https://badges.greenkeeper.io/amercier/eslint-config-flowtype-strict.svg)](https://github.com/amercier/eslint-config-flowtype-strict/issues?q=label%3Agreenkeeper)

## Rules

In addition to [plugin:flowtype/recommended][recommended], the following rules are in effect:

- [flowtype/newline-after-flow-annotation]
- [flowtype/no-dupe-keys]
- [flowtype/no-existential-type]
- [flowtype/no-flow-fix-me-comments]
- [flowtype/no-primitive-constructor-types]
- [flowtype/no-weak-types]
- [flowtype/require-exact-type]
- [flowtype/require-parameter-type]
- [flowtype/require-return-type]
- [flowtype/require-types-at-top]
- [flowtype/require-valid-file-annotation]
- [flowtype/semi]
- [flowtype/type-import-style]

## Examples

Example of valid code:

```js
import React, { Component } from "react";

type InputEvent = SyntheticInputEvent<HTMLInputElement>;

type ActivatorProps = {|
  what: string,
  onClick: (event: InputEvent) => void
|};

class Activator extends Component<AppProps, {}> {
  render() {
    const { what, onClick } = this.props;
    return <button onclick={onClick}>Activate {what}</button>;
  }
}
```

Example of invalid code:

```js
type ActivatorProps = { // flowtype/require-exact-type
  what: string,
  onClick: function, // flowtype/no-weak-types
};
```

See the [full config] for more details.

## Installation

Prerequisites:

- [Node.js] 4+, **npm** 3+
- [ESLint] 4+

> **Important:** please note [ESLint], [babel-eslint] and [eslint-plugin-flowtype] need to be
> installed alongside this module. Latest versions are recommended. This is because this module uses
> [peer dependencies] to be more flexible. For Node 4 and 5, use `eslint@4` and `babel-eslint@8`.

```sh
npm install --save-dev eslint
npm install --save-dev babel-eslint
npm install --save-dev eslint-plugin-flowtype
npm install --save-dev eslint-config-flowtype-strict
```

[![Dependency Status](https://img.shields.io/david/amercier/eslint-config-flowtype-strict.svg)](https://david-dm.org/amercier/eslint-config-flowtype-strict)
[![devDependency Status](https://img.shields.io/david/dev/amercier/eslint-config-flowtype-strict.svg)](https://david-dm.org/amercier/eslint-config-flowtype-strict#info=devDependencies)
[![peerDependency Status](https://img.shields.io/david/peer/amercier/eslint-config-flowtype-strict.svg)](https://david-dm.org/amercier/eslint-config-flowtype-strict#info=devDependencies)

## Usage

Add this to your `.eslintrc.json`:

```json
{
  "extends": ["flowtype-strict"]
}
```

## Contributing

Please read [guidelines for contributing].

## License

[![License](https://img.shields.io/npm/l/eslint-config-flowtype-strict.svg)][license]

[shareable config]: https://eslint.org/docs/developer-guide/shareable-configs
[eslint-plugin-flowtype]: https://github.com/gajus/eslint-plugin-flowtype
[recommended]: https://github.com/gajus/eslint-plugin-flowtype#recommended
[flowtype/newline-after-flow-annotation]: https://github.com/gajus/eslint-plugin-flowtype#eslint-plugin-flowtype-rules-newline-after-flow-annotation
[flowtype/no-dupe-keys]: https://github.com/gajus/eslint-plugin-flowtype#eslint-plugin-flowtype-rules-no-dupe-keys
[flowtype/no-existential-type]: https://github.com/gajus/eslint-plugin-flowtype#eslint-plugin-flowtype-rules-no-existential-type
[flowtype/no-flow-fix-me-comments]: https://github.com/gajus/eslint-plugin-flowtype#eslint-plugin-flowtype-rules-no-flow-fix-me-comments
[flowtype/no-primitive-constructor-types]: https://github.com/gajus/eslint-plugin-flowtype#eslint-plugin-flowtype-rules-no-primitive-constructor-types
[flowtype/no-weak-types]: https://github.com/gajus/eslint-plugin-flowtype#eslint-plugin-flowtype-rules-no-weak-types
[flowtype/require-exact-type]: https://github.com/gajus/eslint-plugin-flowtype#eslint-plugin-flowtype-rules-require-exact-type
[flowtype/require-parameter-type]: https://github.com/gajus/eslint-plugin-flowtype#eslint-plugin-flowtype-rules-require-parameter-type
[flowtype/require-return-type]: https://github.com/gajus/eslint-plugin-flowtype#eslint-plugin-flowtype-rules-require-return-type
[flowtype/require-types-at-top]: https://github.com/gajus/eslint-plugin-flowtype#eslint-plugin-flowtype-rules-require-types-at-top
[flowtype/require-valid-file-annotation]: https://github.com/gajus/eslint-plugin-flowtype#eslint-plugin-flowtype-rules-require-valid-file-annotation
[flowtype/semi]: https://github.com/gajus/eslint-plugin-flowtype#eslint-plugin-flowtype-rules-semi
[flowtype/type-import-style]: https://github.com/gajus/eslint-plugin-flowtype#eslint-plugin-flowtype-rules-type-import-style
[full config]: index.json
[babel-eslint]: https://github.com/babel/babel-eslint
[peer dependencies]: https://nodejs.org/en/blog/npm/peer-dependencies/
[node.js]: https://nodejs.org/
[eslint]: https://eslint.org/
[guidelines for contributing]: CONTRIBUTING.md
[license]: LICENSE.md
