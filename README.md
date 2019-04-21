# semantic-release-config

Sharable configuration for [semantic release](https://semantic-release.gitbook.io).

## Features

Currently, this config is only a slight modification of the default config:

- Deploy from `next` branch instead of `master`
- Add [@semantic-release/git](https://github.com/semantic-release/git) plugin to publish updated `package.json` to repository after deployment

## Installation

Add the following to the `extends` property of your [semantic release configuration](https://semantic-release.gitbook.io/semantic-release/usage/configuration#configuration-file):

```json
{
  "extends": "@adfinis-sygroup/semantic-release-config"
}
```

This repo also contains [commitlint](https://github.com/conventional-changelog/commitlint) which checks that commit messagesas are formatted according to the [conventional commit format](https://www.conventionalcommits.org). Set up a pre-commit hook to integrate it; e.g. by installing [husky](https://github.com/typicode/husky):

```bash
yarn add husky --dev
```

and adding the following section to `package.json`:

```json
  "husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
    }
  },
```

## CI Configuration

- Add credentials for GitHub and npm as described [here](https://semantic-release.gitbook.io/semantic-release/usage/ci-configuration))
- Run semantic-release in the deploy stage as described [here](https://semantic-release.gitbook.io/semantic-release/recipes/recipes/travis)
