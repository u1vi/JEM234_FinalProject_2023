# Git Prune - Prune Unreachable Objects

## Description

The `git prune` command is used to remove files and objects that are no longer reachable from the current branch. It is a useful tool to clean up your working directory and make it more lightweight after finishing a project. This command helps keep your Git repository tidy and efficient.


## Usage

```bash
git prune [-n] [-v] [--progress] [--expire <time>] [--] [<head>...]
```

- `-n, --dry-run`: Report what would be removed without actually removing anything.
- `-v, --verbose`: Report all removed objects.
- `--progress`: Show progress.
- `--expire <time>`: Expire loose objects older than `<time>`.
- `--`: Indicates the end of options; following arguments are not treated as options.

- `<head>...`: Keep objects reachable from the specified `<head> ` references in addition to those reachable from any of the repository's references.

## Examples

To prune objects not used by your repository or by another repository that borrows from yours via its `.git/objects/info/alternates`:

```bash
$ git prune $(cd ../another && git rev-parse --all)
```