# Kosmos T3 updates

Kosmos T3 does not follow every upstream commit automatically.

## Weekly check

`Kosmos - Check for T3 updates` runs each Monday. When official T3 has changed, it:

1. replays the Kosmos changes onto the newest official source;
2. opens a review pull request;
3. triggers the `Kosmos - Quality gate`, which checks formatting, code quality, types, and tests.

Nothing is merged or installed automatically.

## Approved Windows release

After an update pull request is reviewed and merged, run
`Kosmos - Build approved Windows update`. It:

1. repeats the quality checks;
2. creates a uniquely versioned Windows installer;
3. configures that installer to read updates only from `kole-labs/t3code`;
4. publishes the installer and update metadata as the latest Kosmos release.

The first protected release must be installed manually. Later protected releases can be found by
the app through the Kosmos update feed.

## Recovery

Keep the previous GitHub release available. If a new upstream version fails, do not merge its
update pull request and continue using the last known-good Kosmos release.
