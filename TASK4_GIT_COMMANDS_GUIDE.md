# TASK 4: Git Commands and Merge Conflict Resolution

## Part 1: Essential Git Commands

### git status
Shows the working tree status - which files are modified, staged, or untracked.

```bash
git status
```

**Example Output:**
```
On branch main
Changes not staged for commit:
  modified:   README.md

Untracked files:
  newfile.txt
```

### git log
Shows the commit history.

```bash
# Basic log
git log

# One line per commit
git log --oneline

# With graph
git log --oneline --graph --all
```

**Example Output:**
```
a02eb0a Add intro.txt with personal information
ebbb49e Initial plan
1e88c79 Initial commit
```

### git branch
Lists, creates, or deletes branches.

```bash
# List all branches
git branch

# Create a new branch
git branch branch-name

# Delete a branch
git branch -d branch-name

# List all branches including remote
git branch -a
```

## Part 2: Creating and Resolving Merge Conflicts

### Step 1: Create Two Branches
```bash
# Create and switch to branch-a
git checkout -b branch-a

# Make a change to README.md
echo "This is version A" > conflict-line.txt

# Commit the change
git add conflict-line.txt
git commit -m "Add conflict-line.txt with version A"
```

### Step 2: Create Second Branch from Main
```bash
# Go back to main
git checkout main

# Create and switch to branch-b
git checkout -b branch-b

# Make a different change to the same file
echo "This is version B" > conflict-line.txt

# Commit the change
git add conflict-line.txt
git commit -m "Add conflict-line.txt with version B"
```

### Step 3: Merge First Branch
```bash
# Go back to main
git checkout main

# Merge branch-a (this will succeed)
git merge branch-a -m "Merge branch-a into main"
```

### Step 4: Create the Conflict
```bash
# Try to merge branch-b (this will create a conflict)
git merge branch-b
```

**Expected Output:**
```
Auto-merging conflict-line.txt
CONFLICT (add/add): Merge conflict in conflict-line.txt
Automatic merge failed; fix conflicts and then commit the result.
```

### Step 5: View the Conflict
```bash
# Check status
git status

# View the conflicted file
cat conflict-line.txt
```

**The file will contain conflict markers:**
```
<<<<<<< HEAD
This is version A
=======
This is version B
>>>>>>> branch-b
```

### Step 6: Resolve the Conflict
Edit the file to resolve the conflict. Remove the conflict markers and choose the desired content:

```bash
# Option 1: Keep both versions
echo "This is version A and B combined" > conflict-line.txt

# Option 2: Keep version A
echo "This is version A" > conflict-line.txt

# Option 3: Keep version B  
echo "This is version B" > conflict-line.txt

# Option 4: Create a new version
echo "This is the merged version" > conflict-line.txt
```

### Step 7: Complete the Merge
```bash
# Stage the resolved file
git add conflict-line.txt

# Complete the merge
git commit -m "Resolve merge conflict between branch-a and branch-b"

# Verify the merge
git log --oneline --graph --all
```

### Step 8: Clean Up Branches (Optional)
```bash
# Delete the feature branches after merging
git branch -d branch-a
git branch -d branch-b
```

## Summary
This exercise demonstrates:
- Using essential git commands (status, log, branch)
- Creating multiple branches
- Making conflicting changes
- Recognizing merge conflicts
- Resolving conflicts manually
- Completing a merge after resolution

## Key Takeaways
1. **git status** - Always check status before and after operations
2. **git log** - Review commit history to understand changes
3. **git branch** - Manage branches effectively
4. **Conflicts** - Occur when same lines are modified differently in different branches
5. **Resolution** - Requires manual editing and explicit commit
