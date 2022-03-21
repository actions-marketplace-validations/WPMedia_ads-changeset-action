# ADS Changesets Release Action

This action is a fork of the [official Changesets action](https://github.com/changesets/action). This fork adds functionality to publish snapshot releases when there are changesets existing in `main`. Or in other words, when the action updates the PR for release it will now also publish snapshots.

This action for [Changesets](https://github.com/atlassian/changesets) creates a pull request with all of the package versions updated and changelogs updated and when there are new changesets on master, the PR will be updated. When you're ready, you can merge the pull request and you can either publish the packages to npm manually or setup the action to do it for you.

 See below for **changes only specific for this fork**. See original documentation otherwise.

## Usage

### Outputs

Additional outputs:
- `snapshotPublished` - A boolean value to indicate whether a snapshot publish has happened or not
- `releaseMessage` - A string containing a formatted message about the packages that were released

### Example Workflow

#### With Publishing

This fork contains an addition to the publishing workflow. You can now provide a snapshot command. This command will be run in addition to the creation of the proposed release PR created by the action and populate the `publishedPackages` key in the action's output.

```yml
name: Release

on:
  push:
    branches:
      - master

concurrency: ${{ github.workflow }}-${{ github.ref }}

jobs:
  release:
    name: Release
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repo
        uses: actions/checkout@v2
        with:
          # This makes Actions fetch all Git history so that Changesets can generate changelogs with the correct commits
          fetch-depth: 0

      - name: Setup Node.js 12.x
        uses: actions/setup-node@v2
        with:
          node-version: 12.x

      - name: Install Dependencies
        run: yarn

      - name: Create Release Pull Request or Publish to npm
        id: changesets
        uses: @wpmedia/ads-changeset-action@v1
        with:
          # This expects you to have a script called release which does a build for your packages and calls changeset publish
          publish: yarn release
          # This expects you to have a script called release:beta which publishes snapshot releases for your packages (with changeset publish)
          snapshot: yarn release:beta
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          NPM_TOKEN: ${{ secrets.NPM_TOKEN }}

      - name: Send a Slack notification if a publish happens
        if: steps.changesets.outputs.published == 'true'
        # You can do something when a publish happens.
        run: my-slack-bot send-notification --message "A new version of ${GITHUB_REPOSITORY} was published!"
```
