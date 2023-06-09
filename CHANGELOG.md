# @changesets/action

## 1.4.2

### Patch Changes

- [`99cd00e`](https://github.com/changesets/action/commit/99cd00e58cad628812aeb44ab58c39b1b4bb9e8e) Thanks [@camdub](https://github.com/camdub)! - Reset branch after snapshot deploy so that we can change branches for version PR update.

## 1.4.1

### Patch Changes

- [`b3e6f35`](https://github.com/changesets/action/commit/b3e6f35010b8ec1812588de3d39094521314536d) Thanks [@camdub](https://github.com/camdub)! - Remove branch deletion

## 1.4.0

### Minor Changes

- [`13cce38`](https://github.com/changesets/action/commit/13cce385f1cecd399b42a2c118a33b90ce157d51) Thanks [@camdub](https://github.com/camdub)! - Ensure that both a snapshot and a version PR can be ran together by ensuring both run in separate branches.

## 1.3.0

### Minor Changes

- [`a09ec98`](https://github.com/changesets/action/commit/a09ec98f535bf3fcbeffd5ac6b2eea1a083f7a28) Thanks [@camdub](https://github.com/camdub)! - Provide a formatted release message as an additional output

## 1.2.3

### Patch Changes

- [`f2b7b60`](https://github.com/changesets/action/commit/f2b7b608f6dc2082092806d5bb9cb5c0d7014ca1) Thanks [@camdub](https://github.com/camdub)! - Add ability to publish snapshot packages if project has changesets

## 1.2.2

### Patch Changes

- [#161](https://github.com/changesets/action/pull/161) [`52c9ce7`](https://github.com/changesets/action/commit/52c9ce75d9d8a14ea2d75e4157b0c15b7a4ac313) Thanks [@bicknellr](https://github.com/bicknellr)! - Change directory to `cwd` before running git user setup. This fixes an issue when the action starts its execution not in a git repository.

## 1.2.1

### Patch Changes

- [#144](https://github.com/changesets/action/pull/144) [`898d125`](https://github.com/changesets/action/commit/898d125cee6ba00c6a11b6cadca512752c6c910c) Thanks [@Andarist](https://github.com/Andarist)! - Updated all Changesets dependencies. This should fix parsing issues for completely empty summaries that has been fixed in `@changesets/parse@0.3.11`.

## 1.2.0

### Minor Changes

- [#130](https://github.com/changesets/action/pull/130) [`5c0997b`](https://github.com/changesets/action/commit/5c0997b25e175ecf5e1723ba07210bbcea5d92fb) Thanks [@akphi](https://github.com/akphi)! - Added `createGithubReleases` input option (defaults to `true`) to control whether to create Github releases during publish or not.

* [#134](https://github.com/changesets/action/pull/134) [`1ed9bc2`](https://github.com/changesets/action/commit/1ed9bc24b7a56462c183eb815c8f4bdf0e2e5785) Thanks [@dmregister](https://github.com/dmregister)! - Added `cwd` input option that can be used in projects that are not in the root directory.

## 1.1.0

### Minor Changes

- [#128](https://github.com/changesets/action/pull/128) [`1937303`](https://github.com/changesets/action/commit/19373036c4bad4b0183344b6f2623a3b0e42da6c) Thanks [@dhruvdutt](https://github.com/dhruvdutt)! - Setup the git user in the local config instead of the global one.

* [#131](https://github.com/changesets/action/pull/131) [`d3db9ec`](https://github.com/changesets/action/commit/d3db9eceaf41d42c56d5370d504c86851627188f) Thanks [@jacklesliewise](https://github.com/jacklesliewise)! - Added `setupGitUser` option to enable or disable setting up a default git user

## 1.0.0

### Major Changes

- [#118](https://github.com/changesets/action/pull/118) [`05c863d`](https://github.com/changesets/action/commit/05c863d3f980125585016a593b5cb45b27d19c2c) Thanks [@Andarist](https://github.com/Andarist)! - From now on this action will be released using the Changesets-based workflow (using itself). Thanks to that we'll have a good release history. The users will be able to find specific versions of the action and will be able to track changes over time. It also improves the security as the build artifact will always get built in the CI environment, using a frozen lockfile.
