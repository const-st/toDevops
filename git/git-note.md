Create multiple SSH keys in advance, one for each Git account

/.ssh/config
# correct
Host github.com
    HostName github.com
    User git              # ←  git, не мой username
    IdentityFile ~/.ssh/id_ed25519_github

# incorrect it won't work like that
Host github.com
    HostName github.com
    User your-username    # ← не над
    IdentityFile ~/.ssh/id_ed25519_github

git config --global core.editor nano
git config --global init.defaultBranch main

mkdir -p ~/projects/github
mkdir -p ~/projects/gitlab
~/.gitconfig-github
[user]
    name = Your GitHub Username
    email = github-email@example.com
~/.gitconfig-gitlab 
	-//-

~/.gitconfig >>
[includeIf "gitdir:~/projects/github/"]
    path = ~/.gitconfig-github
[includeIf "gitdir:~/projects/gitlab/"]
    path = ~/.gitconfig-gitlab

and clone example
#### git clone git@github.com:username/repo.git ~/projects/github/repo

git config --list --local
git config --global --list

git commit -m
git commit -m "" --date="your format manual input" --author="name"
git commit -am ""

git add -A && git commit -m "Major update" --date="2026-03-31"

git commit --amend --date="2026-03-31 09:00:00" --no-edit - replace last commit

git log --pretty=fuller

git log origin/main..HEAD
git log HEAD..origin/main
git fetch origin

git checkout - b
git swithc -c

git push -u origin feature-branch 

git branch -d namebranch
git push origin --delete nameBranch

git log --oneline --graph --all -10 /// looks merge

git checkout -b feature

git commit -m "commit 1"
git commit -m "commit 2"

git checkout main
git pull origin main        # забрать чужие изменения
git checkout feature
git rebase main              # переложить свои коммиты поверх

(fast-forward)
git checkout main
git merge feature
git push origin main
