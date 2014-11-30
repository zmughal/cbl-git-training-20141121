## Links

- Download Git from [here](http://git-scm.com/downloads).
- Online tutorial: [Try Git](http://try.github.com/)
- Game: [ Learn Git branching ](http://pcottle.github.io/learnGitBranching/)
- Cheat sheet: [Git cheat sheet](http://www.git-tower.com/blog/git-cheat-sheet/)
- Video: [Git for 4 year olds and up](https://www.youtube.com/watch?v=1ffBJ4sVUb4)
- Article: [Git for Computer Scientists](http://eagain.net/articles/git-for-computer-scientists/)
- Slides: [Git Concepts Simplified](http://gitolite.com/gcs.html)
- Book: [Pro Git](http://git-scm.com/book/en/v2)

## Configuration

Make a file called .gitconfig in your home directory and put in your name and e-mail like this:

```config
[user]
	name = Your Name
	email = your.email@example.com
```


## Tips

- `git gui` : show all the branches
- `git add -i`: interactive mode is used for patching (adding part of a file)
- `.gitignore` file: used to indicate files that will be ignored when showing
  modifications. You can use this to not commit data / output.
- when using branches and you have multiple people, you can prefix your name to
  the branch name to let others know who is working on what
- Commit often on your own branch even if your code isn't working completely.
  It lets you see all the steps in your thought process so if you need to go
  back, you can. 

## Git config and aliases

You can use aliases to make typing the commands shorter. Here are some example
aliases and settings. You can use them by putting them in your `.gitconfig`:

```config
[push]
	default = matching

[color]
	ui = auto
[color "branch"]
	current = yellow reverse
	local = yellow
	remote = green
[color "diff"]
	meta = yellow bold
	frag = magenta bold
	old = red bold
	new = green bold
[color "status"]
	added = yellow
	changed = green
	untracked = cyan
[color "grep"]
	match = green

[diff]
	renames = true
[diff "odf"]
	command = odt2txt
[diff "jpg"]
	command = exiftool

[alias]
	st = status -sb
	ci = commit
	br = branch
	co = checkout
	df = diff
	lg = log -p
	lgw = log -p --color-words
	wdiff = diff --color-words
	wshow = show --color-words
	cl = clean -dfx
	cc = cherry-pick
	ff = merge --ff-only
	fx = commit -a --amend -C HEAD
	ix = diff --cached
	hist =  log --all --graph --pretty='[%C(cyan)%h%Creset]%C(bold cyan)%d%Creset %s'
	shist = log       --graph --pretty='[%C(cyan)%h%Creset]%C(bold cyan)%d%Creset %s'
	pu = !"git fetch origin -v; git fetch upstream -v; git merge upstream/master"
	clog = log --date=short --pretty=format:\"%Cred%ad %Cblue%h %Cgreen%an %Creset%s%C(yellow)%d\"
	slog = log --date=short --pretty=format:\"%C(124)%ad %C(24)%h %C(34)%an %C(252)%s%C(178)%d\"
	llog = log --date=short --format=\"%C(94)--------------------------------------------------------------------------------%n%C(24)%h %C(124)%ad %C(34)%an %C(22)<%ae>%C(130)%d%n%C(178) %s%n%n%B(1)\"
	l = log --graph --pretty=format:'%C(yellow)%h%Creset%C(blue)%d%Creset %C(white bold)%s%Creset %C(white dim)(by %an %ar)%Creset'
	ll = !git l --all
	lb = log --graph --simplify-by-decoration --pretty=format:'%d' --all
	ca = commit --amend --reuse-message=HEAD
	softreset = reset --soft HEAD^
	softresetuselastcommit = commit -c ORIG_HEAD

	# for git >= 1.7.2
	headless = checkout --orphan

	# http://stackoverflow.com/questions/957928/is-there-a-way-to-get-the-git-root-directory-in-one-command
	top = rev-parse --show-toplevel
	exec = "!exec "
	wip = commit -a -m WIP
	git = !git

[merge]
	tool = vimdiff
[core]
	excludesfile = ~/.gitignore_global

[pager]
        log = diff-highlight | $PAGER
        show = diff-highlight | $PAGER
        diff = diff-highlight | $PAGER
```
