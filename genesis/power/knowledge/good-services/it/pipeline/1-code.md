- VCS
	- object database (key-value): commit (ID, previous, author, committer, message, tree ~directory(, ID, blob file IDs))
	- patterns
		- branching --> complexity, rapid development vs stability
			- git flow: main, develop - feature, release (tag), hotfix
			- trunk-based
		- repo --> flexibility vs consistency
			- mono-repo: yarn workspaces, lerna, turborepo
			- micro-repo 
	- commands
		- create and push existing project to github  https://kbroman.org/github_tutorial/pages/init.html
			- multiple commands one line: &&
			- Markdown https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax
			- Git Graph
		- git tag
			-  ``` git log --pretty=oneline
				git tag -a <version>
				git log --oneline --decorate <tag>
				git tag <tag name> <tag name>^^{} (window shell escape ^ so doubled) -f -a
				git push -f --tags```
			- https://stackoverflow.com/questions/1028649/how-do-you-rename-a-git-tag
			- https://stackoverflow.com/questions/7813194/how-do-i-edit-an-existing-tag-message-in-git
			- https://stackoverflow.com/questions/3790669/git-is-a-tag-unique-per-commit
		- git merge
			- https://www.atlassian.com/git/tutorials/using-branches/git-merge
		- git branch
			- ```git checkout -b <new> <base>
				git branch <new> <base>
			- rename https://stackoverflow.com/questions/6591213/how-do-i-rename-a-local-git-branch
			- 
		- ![[Pasted image 20230528074737.png]]
		- remove past files from commit history 
			- https://daily-dev-tips.com/posts/removing-a-env-file-from-git-history/
		- squash commits
			- https://stackoverflow.com/questions/5189560/how-do-i-squash-my-last-n-commits-together
		- head
			- git diff head, git checkout head-2 file, git checkout hash 
		- stash
			- git stash, git stash list, git stash apply/pop/drop, git stash show file -p
	- release
		- versioning
			- https://git-scm.com/book/en/v2/Git-Basics-Tagging
			- https://www.gitkraken.com/gitkon/semantic-versioning-git-tags
			- Commits vs Tags vs Releases (or Pre-releases) with Git
			- Pre-release versions: Alpha vs Beta
			- SemVer
				- ![[Pasted image 20230504133611.png]]
				- ![[Pasted image 20230504133633.png]]
			- CalVer
				- External factors (e.g. marketing)
			- (Web) Apps: depends SemVer or CalVer https://frontside.com/blog/2022-02-09-semver-or-calver-by-project-type/
- IDE
	- @builtin extensions (Git, GitHub) 
	- git gist & profile exporting 
	 ![[Pasted image 20230522081255.png]]
- Package manager

