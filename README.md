# Git
FIU STARS Tutorial Wiki on Git and Git Development processes

Your local repository consists of three "trees" maintained by git. the first one is your Working Directory which holds the actual files. the second one is the Index which acts as a staging area and finally the HEAD which points to the last commit you've made.
![workflow](http://rogerdudler.github.io/git-guide/img/trees.png)

## Basics
  * Create a new repository
    * `mkdir project && cd project`
    * `git init`
  * Clone an existing repository
    * `git clone https://github.io/USERNAME/REPO.git`
  * View difference in files
   * `git diff`
  * Add to Staging
    * `git add <filename>` or `git add * ` for everything in directory
    * To add files interactively `git add -i`
  * Commit to HEAD
    * `git commit -m "Commit Message"`
  * Pushing changes to remote server
    * `git push origin master`
    * If you didn't clone a repository to need to add your remote repositoty like so:
      * `git remote add origin <server>`
  * Creating a separate branch
   * `git branch <new-branch>`
   * `git checkout <new-branch>`
   * A simpler way `git checkout -b <new-branch>`


## Development Process - GitFlow
The Gitflow Workflow still uses a central repository as the communication hub for all developers. And, as in the other workflows, developers work locally and push branches to the central repo. The only difference is the branch structure of the project.

### Branching
![Branching](https://www.atlassian.com/git/images/tutorials/collaborating/using-branches/hero.svg)
Branches serve as an abstraction for the edit/stage/commit process, they are used to develop features isolated from each other. The staging/development branch is the "default" branch when you create a repository. 
Use other branches for development and merge them back to the staging/development branch upon completion.
![branching](http://rogerdudler.github.io/git-guide/img/branches.png)
  * Create a branch from staging
    * `$ git checkout -b <feature-branch> origin/staging`
    * `$ git push origin <feature-branch>`
  * Build and push feature code to respective `<feature-branch>`

### Updating & Merging
 * To update your local repository with the latest from the server
  * `git pull`
 * To update a specific branch
  * `git checkout <branch>` 
  * `git pull origin <branch>`

### Submiting Updates
 * Push updated and completed branch to remote repo
  * `git pull origin master`
  * `git push origin <feature-branch>`
 * Create PR `pull-request`
   * Go to Git Repositiory Page
   * Click `Create Pull Request` button
   * Confiuration: Into `staging` branch from `<feature-branch>` branch
     ![pull-request](https://guides.github.com/activities/hello-world/create-pr.png) 

![gitflow](https://www.atlassian.com/git/images/tutorials/collaborating/comparing-workflows/gitflow-workflow/01.svg)
![maintenance](https://www.atlassian.com/git/images/tutorials/collaborating/comparing-workflows/gitflow-workflow/05.svg)


## Resources
* [Learn Git Interactively](https://try.github.io/levels/1/challenges/1)
