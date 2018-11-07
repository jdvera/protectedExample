# Creating the Repo with a protected Master branch
1. [Create the branch **with a README**](https://raw.githubusercontent.com/jdvera/protectedExample/master/1.PNG)
2. [Click Settings on the top row](https://raw.githubusercontent.com/jdvera/protectedExample/master/2.PNG)
3. [Click Branches on the sidebar](https://raw.githubusercontent.com/jdvera/protectedExample/master/3.PNG)
4. [Click "Add rule" on the right](https://raw.githubusercontent.com/jdvera/protectedExample/master/4.PNG)
5. [Type "master" into the Apply Rule To section, check "Require pull request reviews before merging" & "Include administrators", and click Create](https://raw.githubusercontent.com/jdvera/protectedExample/master/5.PNG)


### After Creating and Cloning, make your own branch
For this example, I'll be using a branch called "feature/homepage".  Remember we start off in master after cloning
1. `git checkout -b feature/homepage`
    * checkout says we want to move to a different branch, -b says the branch we named doesn't exist yet, so git needs to create it first


### After working for a while and want to push to GitHub
1. commit your current work (git add / git commit)
    * if you have uncommited work, git usually won't let you do anything until you've saved it or gotten rid of it (e.g. git stash)

2. `git pull`
    * pull all the recent changes your teammates may have made while you were working

3. `git merge master`
    * merging anything new from master -> features/homepage.
    * *This step may cause conflicts*  That's okay.  Make sure to read the message after the merge to see if there are any conflicts, and **resolve all of them before continuing**.
    * Also good to double-check your site at this point and make sure it still works correctly

4. `git add -A`
5. `git commit -m "type whatever here"`
6. `git push origin features/homepage`
    * If master is protected, then you will **NOT** be able to push from your master branch to GitHub's master.  Only push up the branch you have been working on
    * You may get an error message saying something about that branch having "no upstream branch", followed by a command that looks like `git push --set-upstream origin features/homepage`.  Simply copy/paste that command and run it.

You should now be able to go to GitHub, refresh the page, and see that a new branch exists with your work in it


### Go to GitHub to actualy merge changes to master
1. Click on [Pull Requests](https://raw.githubusercontent.com/jdvera/protectedExample/master/6.PNG) on the top row
2. Click [New Pull Request](https://raw.githubusercontent.com/jdvera/protectedExample/master/7.PNG)
3. On the second dropdown, choose the branch you've been working on.  [You should then see green "Able to merge" text.](https://raw.githubusercontent.com/jdvera/protectedExample/master/8.PNG)
    * If you do not see "Able to merge", then you likely did not resolve all the conflicts when running `git merge master`.  Either go back to your computer and make sure you resolved everything, or resolve the conflicts in GitHub (maybe grab a TA at this point)
4. Click [Create Pull Request](https://raw.githubusercontent.com/jdvera/protectedExample/master/9.PNG)

At this point, the new Request is posted, and another teammate will need to review it


### The other teammate reviewing the Pull Requests
1. After clicking the Pull Request tab, you should see the request in the list.  [Click on the name of the request](https://raw.githubusercontent.com/jdvera/protectedExample/master/10.PNG)
2. On the right-side, next to Reviewers, [click the gear button and select your username](https://raw.githubusercontent.com/jdvera/protectedExample/master/11.PNG)
3. After a seccond or two, you should see a update appear near the top.  [Click Add Your Review](https://raw.githubusercontent.com/jdvera/protectedExample/master/12.PNG)
4. You *should* be looking through your teammate's code to make sure everything looks/works correctly.
    * When you're ready to comment, [click Review Changes -> check Approve if everything's okay **OR** Request Changes if something's wrong (with a comment) -> click Submit Review](https://raw.githubusercontent.com/jdvera/protectedExample/master/13.PNG)
5. Assuming everything was okay, click [Merge Pull Request](https://raw.githubusercontent.com/jdvera/protectedExample/master/14a.PNG)
6. [Click Confirm Merge.](https://raw.githubusercontent.com/jdvera/protectedExample/master/14b.PNG)  If you'd like, you can add a custom commit message first
7. *Optional* If you are finished with that feature/bug/etc., [you may delete the branch off GitHub.](https://raw.githubusercontent.com/jdvera/protectedExample/master/14c.PNG)  This doesn't immediately delete them off your local computers, so you can still do stuff there.
8. Everyone else on the team can run `git pull origin master` to get the updated code