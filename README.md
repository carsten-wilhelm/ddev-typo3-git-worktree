[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/ddev/ddev-addon-template/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/ddev/ddev-addon-template/actions/workflows/tests.yml?query=branch%3Amain)
[![last commit](https://img.shields.io/github/last-commit/ddev/ddev-addon-template)](https://github.com/ddev/ddev-addon-template/commits)
[![release](https://img.shields.io/github/v/release/ddev/ddev-addon-template)](https://github.com/ddev/ddev-addon-template/releases/latest)

# DDEV Add-on for Git worktrees with TYPO3

## Overview

This add-on adds commands to work with Git worktrees for TYPO3.

To use the scripts, you need to have worktree support for your project, e.g.

```
# 1. Clone the repo into a hidden .bare folder
git clone --bare git@github.com:user/repo.git .bare

# 2. Tell the root folder where the Git history is hidden
echo "gitdir: ./.bare" > .git

# 3. Fix the fetch configuration to see all remote branches
git config remote.origin.fetch "+refs/heads/*:refs/remotes/origin/*"

# 4. Create your first worktree (the main branch)
git worktree add main
```

To create a new worktree, run the command

```
ddev generate-worktree-config [folder]
```

It will create a new worktree folder named in your project and create necessary
DDEV and TYPO3 config enhancements. The worktree will have a separate DDEV
config with separate DDEV domains, so you can run all worktrees in a project
in parallel (e.g. when maintaining different versions of TYPO3 during an upgrade).

## Installation

```bash
ddev add-on get macaw/ddev-typo3-git-worktree
ddev restart
```

## Usage

| Command | Description |
| ------- | ----------- |
| `ddev generate-worktree-config` | Create new git worktree or remove an existing oe |

The other two commands should not be used standalone, since they will create files for
either DDEV or TYPO3 sites.

## Credits

**Contributed and maintained by Macaw**
