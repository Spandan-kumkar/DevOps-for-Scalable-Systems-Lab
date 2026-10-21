
# Assignment 2: Git Branching and Collaboration

## Commands Executed

### 1. Push Changes and Check Branches

```bash
git push
git branch
git switch main
```

### 2. Clone the Shared Repository

```bash
git clone <GitHub-repository-URL>
cd devops-task-manager
```

### 3. Synchronize Main Branch

```bash
git switch main
git pull origin main
```

### 4. Create a Feature Branch

```bash
git switch -c feature-add-task
```

### 5. Check Repository Status

```bash
git status
```

### 6. Stage and Commit Feature Changes

```bash
git add .
git commit -m "Add task creation feature"
```

### 7. Push the Feature Branch

```bash
git push -u origin feature-add-task
```

### 8. Synchronize After Pull Request Merge

After merging the Pull Request on GitHub, execute:

```bash
git switch main
git pull origin main
```

## Outcome

The commands demonstrate Git branching, repository synchronization, staging, committing, and pushing feature changes. Pull Request creation, code review, approval, and merging are performed through the GitHub website.
