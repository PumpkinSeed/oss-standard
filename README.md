# OSS Standard

- Maintainability guidelines of Open-Source Software development
- **Guidelines aplicable for newly started software projects**
- *Any pieces of advice for the improvement of the guideline is warmly accepted.*

### Issues

- The first step should always be the issue/ticket
- If there isn't an issue template try to provide as many additional details as possible, like main issue, how to replicate, version(s) of software(s) used when the issue occured
- After the discussion and having the possible solution clarified go to the implementation following the [basic guidelines](#basic-guidelines)

### Basic guidelines

- Follow [trunk based development](https://trunkbaseddevelopment.com/)

Development flow
1. Pull the **master** branch to get the most up-to-date version of the system/application/service
2. Create a feature branch following the [branch naming conventions](#branch-naming-concentions), `git branch I332-short-name`
3. Push frequently based on the smaller parts of the sections, follow the [push guidelines](#push-guidelines)
4. Create Pull Request once the development reaches a state where the solution is considered to be done based on the requirements, follow the guidelines of [pull request](#pull-request)
5. Accept the reviews and do the change requests

Maintainer flow
1. Accept pull request on master
2. Based on the size of the team responsible for the codebase add half of the team as reviewer
3. Setup additional content for the pull request, in case of [Github](#github-pr-additionals) 
4. - If half of the reviewers (so 1/4 of the team) approve the changes 
   - and all of the change requests get done 
   - and the newly added code has at least 80% of code coverage 
   - and the automated test system or CI tool runs successfully then merge it following the [merge guidelines](#merge-guidelines)
5. When the develop reaches the goals of the next version, release a new version based on the [release-guidelines](#release-guidelines)

Third-party developer flow
1. Fork the original repository
2. Clone it and the remote origin points to the forked version
3. Set the remote upstream to the original repository
4. Frequently do pulls on upstream's master and merge it into the origin's working branch to keep the development up-to-date
5. Do the steps of the Development flow
6. Create pull request between forks against the **master** branch

### Branch naming conventions

- First letter must be `I` if issue, or `T` if board ticket, strongly platform restricted
- After the first letter, add the number of the ticket, ex.: `432`
- After that add the short name of the ticket with dashes in [kebab-case](https://trends.google.com/trends/explore?date=all&q=kebab-case,spinal-case,lisp-case,dash-case,caterpillar-case), ex.: `short-name`
- ex.: `I432-short-name` or `T432-payment-bug-fix`


### Push guidelines

- Never use `*` or `.` in `git add`, it helps to overview the files and avoid the pushes of unecessary files (ex.: binaries)
- Never use `-m` in `git commit`, it helps to have an additional overview of the files and makes it possible to format the commit message properly
- Use `git push --set-upstream origin I12-branch-name` at the first time
- Never push changes on the master

### Pull request

- Add well-meaning title so that the maintainer can quickly recognize the purpose of the pull request.
- Write detailed description in the body, what main issue this PR solves and how is it testable to prove the validity of the solution.
- Create pull request against **master**.

### Merge guidelines

- Use `Squash` to keep the commit line clean from the thousands of commits

### Release guidelines

- In special cases let's handle it in an automated way or go with the following steps by hand
- Use [Semver 2](https://semver.org/) or language-specific best practices
- Create annotated tag with `git tag -a v1.2.3`
- Push the new changes `git push --tags`

### Github PR additionals

- `Assignes`, yourself or an other team member who should deal with the PR
- `Labels`, determine the kind of the PR and provide more information about
- `Projects`, determine the project where the PR belongs to
- `Milestones`, determine the version number where the PR will be released
