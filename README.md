# remark-kbd-simple
## Syntax

```md
Press [[ctrl]] + [[c]]!
```

## AST (see [mdast](https://github.com/syntax-tree/mdast/blob/master/readme.md) specification)

For example, the following markdown:

`[[ctrl]]`

Yields:

```js
{
    type: 'kbd',
    data: {
        hName: 'kbd',
    },
    children: [{
        type: 'text',
        value: 'ctrl'
    }]
}
```

## Rehype

This plugin is compatible with [rehype][https://github.com/rehypejs/rehype]. `kbd` mdast nodes (e.g. `[[ctrl]]`) will become `<kbd>ctrl</kbd>`.

## Installation

```bash
yarn add remark-kbd-simple
```

## Usage

Dependencies:

```javascript
const unified = require('unified')
const remarkParse = require('remark-parse')
const stringify = require('rehype-stringify')
const remark2rehype = require('remark-rehype')

const remarkKbd = require('remark-kbd-simple')
```

Usage:

```javascript
unified()
  .use(remarkParse)
  .use(remarkKbd)
  .use(remark2rehype)
  .use(stringify)
```
