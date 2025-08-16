# MultiVersionUnsafe

This method of maintaining multiple game versions easily allows commits in both the latest main branch and any other version branch. When syncing changes from one to another, a "source merge" is used where the merge is cut short just before the commit, all files that are related to building for the specific game version are unstaged and restored, then the merge continues as normal. This guideline must be stuck with and it makes the graph log a little confusing, but it has the easier implementation and usage.

- Commit
- Commit
- Commit

New version is released

- Create version branch
- Bump commit
- Commit
- Commit
- Commit
- Switch to version branch
- Source merge
- 	`git merge main --no-commit --no-ff` (Merge but stop before commit and don't allow fast forward)
- 	`git restore --source HEAD -- buildFiles.\*`
- 	Commit merge (Maybe with message of "source merge" rather than "merge")

Compiler option for version is needed

- Switch to main branch
- Add BUILD_FOR_MAIN
- Commit
- Switch to version branch
- Source merge from main branch
- Add BUILD_FOR_VERSION
- Commit

Need to update from version branch

- Switch to version branch
- Commit
- Commit
- Commit
- Switch to main branch
- Source merge from version branch

Need to update from version branch without leaving duplicate commits

- Duplicate commits are avoided by default

Need to make the same update to build files in each version branch

- Cherry-pick the commits to each branch manually because source merge completely ignores those files and a regular merge command will explode your repository

Need to make a specific update to build files on main version branch

- Done by default