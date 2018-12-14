# tg-gh-lib

todgru's Github Helpers

## Usage

Github methods for:
- returning an array of pull requests
- merging `some-branch` into `some-other-branch`

Requires a [Github personal access token](https://github.com/settings/tokens/). This token needs `repo` access. An environment variable `GITHUB_TOKEN` can be set or the token can be passed in as an argument to the module.

```javascript
const gh = require("tg-gh-lib")({repo: "my-awesome-repo", name: "todgru", token: "my-token"});

(async () => {
  // merge master into feature branch
  const result = await gh.merge("master", "my-feature", "merging master into feature")
  // => returns status codes,
  // - 201 for successful update
  // - 204 for already updated
  // - 409 merge conflict
  // - etc.

  // get a list of open PR's
  const prs = await.gh.pulls()
  // => returns array of open pr's, or empty array if no pr's.

  })
```
