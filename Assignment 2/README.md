# Assignment 2: Git Branching and Collaboration

## Aim
To implement Git branching strategies using feature branches, pull requests, code review, and merging to simulate collaborative software development in a distributed team.

## Objectives
- Create and manage feature branches.
- Collaborate using a shared GitHub repository.
- Push feature branch changes to GitHub.
- Create and review Pull Requests.
- Approve and merge Pull Requests into the `main` branch.
- Synchronize the local repository with the latest changes.

## Tools Used
- Git
- GitHub
- Visual Studio Code

## Procedure
1. Opened the existing Student Task Manager GitHub repository.
2. Added a collaborator to the repository.
3. Cloned the shared repository on the collaborator's system.
4. Switched to the `main` branch and pulled the latest changes.
5. Created a feature branch named `feature-add-task`.
6. Implemented changes on the feature branch.
7. Staged, committed, and pushed the feature changes to GitHub.
8. Created a Pull Request for the implemented feature.
9. Reviewed the changes and approved the Pull Request.
10. Merged the Pull Request into `main`.
11. Pulled the latest changes to synchronize the local repository.

## Git Commands

```bash
git clone <GitHub-repository-URL>
cd <repository-folder>
git switch main
git pull origin main
git switch -c feature-add-task
git status
git add .
git commit -m "Add task creation feature"
git push -u origin feature-add-task
```

After the Pull Request is merged:

```bash
git switch main
git pull origin main
git log --oneline --graph --all
```

## Expected Outcome
Successful demonstration of collaborative development using Git branches, Pull Requests, code review, merging, and synchronization with GitHub.

## Screenshots
Screenshots demonstrating repository collaboration, feature branch creation, commits, Pull Request creation, code review, merging, and the updated commit history are included in the `screenshots/` folder.

