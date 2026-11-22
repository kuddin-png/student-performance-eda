# Publish this project to GitHub

The project folder is already organized as a GitHub-ready repository.

1. Extract `student-performance-eda.zip`.
2. Create an empty repository on GitHub (for example, `student-performance-eda`). Do not initialize it with a README, license, or `.gitignore`.
3. Open a terminal in the extracted project folder and run:

```bash
git init
git add .
git commit -m "Add executed student performance EDA"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/student-performance-eda.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username. The remote repository must exist before the `git push` command.

A remote GitHub repository was not created automatically in this session because the connected GitHub actions do not expose a create-repository operation. The archive includes the notebook, executed outputs, datasets, PDF, README, and requirements needed to publish it.
