# TASK 2: Forking and Pull Request Workflow

## Step-by-Step Guide

### 1. Fork a Repository
```bash
# On GitHub.com:
# 1. Navigate to the repository you want to fork
# 2. Click the "Fork" button in the top-right corner
# 3. Select your account as the destination
# 4. Wait for GitHub to create the fork
```

### 2. Clone Your Fork
```bash
# Clone your forked repository to your local machine
git clone https://github.com/YOUR_USERNAME/REPOSITORY_NAME.git
cd REPOSITORY_NAME
```

### 3. Create a New Branch
```bash
# Create and switch to the 'update-readme' branch
git checkout -b update-readme
```

### 4. Make Changes
```bash
# Edit the README.md file
# Add one line to the README for the workshop task
echo "Workshop task completed: This line was added for the GitHub workshop assessment." >> README.md
```

### 5. Commit Your Changes
```bash
# Stage the changes
git add README.md

# Commit with a descriptive message
git commit -m "Add workshop task line to README"
```

### 6. Push to Your Fork
```bash
# Push the branch to your fork on GitHub
git push origin update-readme
```

### 7. Create a Pull Request
```bash
# On GitHub.com:
# 1. Navigate to your forked repository
# 2. Click "Compare & pull request" button that appears
# 3. Set the pull request title: "Updated README"
# 4. Set the pull request description: "Added one line for workshop task"
# 5. Review the changes
# 6. Click "Create pull request"
```

## Summary
This workflow demonstrates:
- Forking a repository to your account
- Creating a feature branch for changes
- Making and committing changes
- Pushing to your fork
- Creating a pull request with proper title and description
