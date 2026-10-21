
# Assignment 3: Jenkins Build Automation

## Aim
To configure Jenkins to retrieve the Student Task Manager application from GitHub and automate the application build process.

## Objectives
- Understand the basics of Jenkins build automation.
- Configure a Jenkins job connected to a GitHub repository.
- Install application dependencies using npm.
- Execute the application build process through Jenkins.
- Verify the build status and console output.

## Tools Used
- Jenkins
- Git and GitHub
- Node.js
- npm
- Visual Studio Code

## Procedure
1. Prepared the Student Task Manager application for build automation.
2. Configured the application build script using `build.js`.
3. Added the required build command to `package.json`.
4. Committed and pushed the application files to GitHub.
5. Created a Jenkins Freestyle project named `task-manager-build`.
6. Configured the GitHub repository URL and selected the `main` branch.
7. Configured the build steps to execute `npm install` and `npm run build`.
8. Executed the Jenkins job and inspected the console output.
9. Verified the build result.

## Commands Used

```bash
npm install
npm run build
git add .
git commit -m "Add application build configuration"
git push origin main
```

## Build Commands in Jenkins

```bash
npm install
npm run build
```

## Expected Outcome
Successful execution of the Student Task Manager build process through Jenkins, with the build status and console output used to verify the result.

## Screenshots
Add screenshots demonstrating:
- Jenkins Freestyle project configuration.
- Git repository and branch configuration.
- Build steps configuration.
- Successful Jenkins build.
- Jenkins console output.

## Repository
[Student Task Manager GitHub Repository](<YOUR-GITHUB-REPOSITORY-URL>)
