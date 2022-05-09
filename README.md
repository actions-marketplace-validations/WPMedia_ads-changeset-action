# ADS Changesets Release Action

This action is a fork of the [official Changesets action](https://github.com/changesets/action). This fork adds functionality to publish snapshot releases when there are changesets existing in `main`. Or in other words, when the action updates the PR for release it will now also publish snapshots.

See below for **changes only specific for this fork**. See original documentation otherwise.

## Usage

### Outputs

Additional outputs:
- `snapshotPublished` - A boolean value to indicate whether a snapshot publish has happened or not
- `releaseMessage` - A string containing a formatted message about the packages that were released