# Dragonfly Client (Blaxel Fork)

This public fork of the [Dragonfly Client](https://github.com/dragonflyoss/client)
(a.k.a. `dfdaemon`, `dfget`, `dfcache`, `dfstore`, `dfctl`, and `dfinit`)
can be used to stage features for upstream PRs or, if need be,
to maintain Blaxel-specific functionality (but consider visibility when doing so).

## Usage

The head of the fork is maintained on the `blaxel-fork` branch.
Always rebase rather than merge when incorporating upstream changes back into the fork.

At any given time, there should be a minimal number of focused commits on top of the upstream head.
Much of the automated GitHub-specific infrastructure (dependabot, release workflow, templates, etc.)
has been removed from this fork.
The idea is to instead rely on the upstream repository to incorporate dependabot suggestions
and rebase on those changes here.

### Releasing

The fork uses a simplified [release action](.github/workflows/release.yml)
that simply uploads pre-built x86-64 Linux binaries for each tool as a tarball.

In order to trigger the release process,
create a tag of the form `vX.Y.Z-blaxel[.R]` at the commit where you want to build the binaries,
where `X.Y.Z` is the tag of the latest upstream commit
and `[.R]` is an optional revision number (in case there are several forked version built off a single upstream version),
then push the new tag to the Blaxel fork repository,
and trigger the workflow manually:

```bash
gh workflow run release.yml --ref blaxel-fork -f tag=vX.Y.Z-blaxel
```
