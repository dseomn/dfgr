# DotFiles Git Repo (dfgr)

dfgr is a simple wrapper around git for when you basically want [plain git
dotfiles](https://www.atlassian.com/git/tutorials/dotfiles), but you also want a
separate command to operate on your dotfiles repo, with command completion.

Another way of thinking about it is that it's like [yadm](https://yadm.io/) with
almost all the features removed. If you copy your dotfiles manager's code into
your dotfiles repo (which dfgr encourages), the much smaller amount of code will
hopefully minimize how often that code needs to be updated. Additionally, it
should be much easier to review this code if you don't want to trust some
stranger on the internet. That said, if you want the extra features, yadm is
great too.

## Installation

1.  If needed, add `~/.local/bin` to your `$PATH`.
1.  Copy `dfgr` to `~/.local/bin/dfgr`, or link it from there.
1.  If you want bash completion, copy `bash-completion/completions/dfgr` to
    `~/.local/share/bash-completion/completions/dfgr`, or link it from there.

## Creating or cloning a repo

```sh
mkdir -p ~/.local/share/dfgr
git --git-dir ~/.local/share/dfgr/dotfiles.git --work-tree ~ init
```

Then, if you are cloning an existing repo:

```sh
git --git-dir ~/.local/share/dfgr/dotfiles.git remote add -f origin <URL>
git --git-dir ~/.local/share/dfgr/dotfiles.git switch main
```

If the `git-switch` command gives the error below, resolve the conflicts between
the local files and the ones in the dotfiles repo, and run the command again.

```
error: The following untracked working tree files would be overwritten by checkout
```
