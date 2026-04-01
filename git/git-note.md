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
git clone git@github.com:username/repo.git ~/projects/github/repo
