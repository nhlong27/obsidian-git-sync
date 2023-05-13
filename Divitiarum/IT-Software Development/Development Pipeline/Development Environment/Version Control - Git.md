[#git]

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
	```