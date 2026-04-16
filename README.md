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
