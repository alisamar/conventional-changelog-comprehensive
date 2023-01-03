# conventionalcommits.org convention

A concrete implementation of the specification described at
[conventionalcommits.org](https://conventionalcommits.org/) for automated
CHANGELOG generation and version management.

## Installing conventional-changelog-comprehensive

### As a local ``npm run`` script

Install and add to devDependencies:

```bash
npm install --save-dev conventional-changelog-comprehensive
```

## Indirect Usage (as preset)

Use the [Conventional Changelog CLI Quick Start](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-cli#quick-start) with the `-p comprehensive` option.

## Direct Usage (as a base preset so you can customize it)

If you want to use this package directly and pass options, you can use the [Conventional Changelog CLI Quick Start](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-cli#quick-start) and with the `--config` or `-n` parameter, pass a js config that looks like this

```js
'use strict'
const config = require('conventional-changelog-comprehensive')

module.exports = config({
    "issuePrefixes": ["TEST-"],
    "issueUrlFormat": "https://myBugTracker.com/{{prefix}}{{id}}"
})
```

or json config like that:
```js
{
    "options": {
        "preset": {
            "name": "comprehensive",
            "issuePrefixes": ["TEST-"],
            "issueUrlFormat": "https://myBugTracker.com/{{prefix}}{{id}}"
        }
    }
}
```
This last json config way passes the `preset` object to the `conventional-changelog-preset-loader` package, that in turn, passes this same `preset` object as the config for the `conventional-changelog-comprehensive`.



See [conventional-changelog-config-spec](https://github.com/conventional-changelog/conventional-changelog-config-spec) for available configuration options.

