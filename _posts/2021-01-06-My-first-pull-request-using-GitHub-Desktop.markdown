## Installing GitHub Desktop to manage my commits

1. Sign up for GitHub in [GitHub webpage](https://github.com/join).

		Username: 
		Email Address:
		Password:

2. Download GitHub Desktop [from the web](https://desktop.github.com/).

4. Install GitHub Desktop using the downloaded executable.

5. Log in at GitHub Desktop using your username and password.

## Contribute to an existing repository

### Download a repository on GitHub.com to our machine

6. Go to the repository webpage in GitHub. (e.g., [openTEPES repository](https://github.com/IIT-EnergySystemModels/openTEPES))

7. Click on the green button called "Code", after that click on "Open with GitHub Desktop" option.

8. Select the path in your computer where you can store the repository, and click on "clone" green button.

### Create a new branch to store any new changes

9. On the interface of GitHub Desktop.

		--> Go to the menu
		--> Click on "Branch"
		--> Select "New branch..."

10. Insert a name for the new branch, and create branch. (e.g., new-branch)

11. Switch to that branch by clicking on the sub-menu "Current branch" that is located at the center of the three sub-menus which are below to the main the menu.

12. On the central part of the interface of GitHub Desktop, select the blue button "Publish branch". (It created the created branch in ours computer, in the version web of the repository)

12. Make changes in the files of the repository using a text editor.

### Push changes to github

This process helps us synchronize the changes that we made on our computer with the branch's version web. 

13. On the interface of GitHub Desktop.

		--> In the left-bottom side of the interface:
			- locate the blue button "Commit to ...".
		--> Insert a name for the changes, in the "summary (required)" textbox.
		--> Click on "Commit to ..." button.
		--> In the central part of the interface:
			- locate the blue button "Push ...", and Click on it.

14. Try to insert appropiated names to the commits, and make a push for a set of similar commits.


### Pull request to github

This process inserts our most advanced changes made in the created branch to the master branch.

15. After, we finish to make the changes and corresponding push to the created branch

16. On the central part of the interface of GitHub Desktop.

		--> Select "Create Pull Request," it will lead to the respository in the web.
		--> Insert a name for the Pull-request
		--> Click on green button "Create Pull Request".
		--> Select reviewers on the left side of the webpage (section reviewers).
		--> The owners of the respository will make the merge.
		--> In case that you are the owner, you can make the merge by yourselft.
		--> Deleted the merged branch both in the web version and GitHub Desktop.

### Update our version of the repository by pulling changes from github

This process will update the version of the respository that you have in your computer with new ones located in the web.

17. On the interface of GitHub Desktop.

		--> Click on the sub-menu "Fecth origin".
			- It is located at the right side of the three sub-menus which are below to the main menu.
		--> In the central part of the interface:
			- Locate the blue button "Pull origin", and Click on it.

18. Sometimes we have to make the rebase of the repository as follows:
		
		--> Click on the menu "Branch".
		--> Select the option "Rebase Current Branch..."
		