# tg-gh

todgru's Github Helpers

## Usage

A [Github personal access token](https://github.com/settings/tokens/), `GITHUB_TOKEN`, can be set in the environment or `token` can be passed in as one of the options. This token needs `repo` access.

```javascript
const gh = require("tg-gh")({repo: "my-awesome-repo", name: "todgru", token: "my-token"});

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
