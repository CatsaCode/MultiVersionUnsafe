MultiVersionUnsafe

* Commit
* Commit
* Commit

New version is released

* Create version branch
* Bump commit
* Commit
* Commit
* Commit
* Switch to version branch
* Source merge
* 	`git merge main --no-commit --no-ff` (Merge but stop before commit and don't allow fast forward)
* 	`git restore --source HEAD -- buildFiles.\*`
* 	Commit merge (Maybe with message of "source merge" rather than "merge")

Compiler option for version is needed

* Switch to main branch
* Add BUILD_FOR_MAIN
* Commit
* Switch to version branch
* Source merge from main branch
* Add BUILD_FOR_VERSION
* Commit

Need to update from version branch

* Switch to version branch
* Commit
* Commit
* Commit
* Switch to main branch
* Source merge from version branch