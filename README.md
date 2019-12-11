# OSS Standard

Maintainability guidelines of Open-Source Software development

### Basic guidelines

- Follow the [git flow guidelines ](https://nvie.com/posts/a-successful-git-branching-model/)
- Use the [git flow](https://github.com/nvie/gitflow/wiki/Installation) tool
- Developers only hit the develop branch

Development flow
1. Pull the develop branch to get the most up-to-date version of the system/application/service
2. Create a feature branch following the branch naming conventions detailed below `git flow feature start I332-short-name`
3. Push frequently based on the smaller parts of the sections, follow the push guidelines detailed below
4. Create Pull Request once the development reaches the state where the solution considered as done based on the requirements, follow the guidelines of [Pull Request](#pull-request)


### Branch naming conventions

### Push guidelines

- Never use `*` or `.` in `git add`, it helps to overview the files and avoid the pushes of unecessary files (ex.: binaries)
- Never use `-m` in `git commit`, helps to have an additional overview of the files and make it possible to format the commit message properly
- Use `git flow feature publish I12-branch-name` instead of `git push`
- Never use `git flow feature finish I12-branch-name`, it's merge the branch directly into the develop

### Pull request

### On-premise contribution
