# Git Essentials for Beginners - Part 4B: Basic Merging Exercise

## Introduction: Making Merging Meaningful

Before we start, take a moment to think about:

- How do you handle different perspectives in your daily life?
- When facing conflicting ideas, do you choose one, the other, or try to combine them?
- How might version control reflect how we manage differing viewpoints?

These questions mirror what we'll explore with Git merging!

## Choose Your Adventure

For these exercises, you'll create content on a topic of your interest. Choose one of these simple topics or create your own:

- Your favorite programming languages (pros and cons)
- Remote work vs. office work preferences
- Individual contributor vs. team player approach
- Morning person vs. night owl
- Text editors/IDEs preferences
- Best learning resources for programming

Feel free to be creative! The content matters less than the Git operations, but meaningful content makes practice more engaging.

## Setting Up Your Practice Repository

1. Create a new Git repository
2. Create a README.md with a basic introduction to your chosen topic
3. Make an initial commit
4. Add more content to the README.md and make a second commit

Create these branches for our exercises:

```bash
git branch main1
git branch main2
git branch main3
git branch main-backup
```

## Exercise 1: Fast-Forward Merge

**Goal:** Create a simple branch that advances ahead of main1, then merge it back using a fast-forward merge.

**Checklist:**

- Start with this structure:
  ```
  A---B  (main1)
  ```
- Create a feature1 branch and add commits
- End with this structure after merging:
  ```
  A---B---C  (main1, feature1)
  ```

**Exercise:**

1. Switch to main1
2. Create a feature1 branch
3. On feature1, add a file that elaborates on one aspect of your chosen topic
4. Merge feature1 back into main1
5. Verify you have a fast-forward merge

## Exercise 2: Creating a Merge Commit

**Goal:** Experience a situation where Git must create a merge commit due to divergent branches.

**Checklist:**

- Start with main2
- Create and modify a feature2 branch
- Make different changes on main2
- End with this structure after merging:
  ```
        C---D  (feature2)
       /     \
  A---B---F---G  (main2)
  ```

**Exercise:**

1. Switch to main2
2. Create a feature2 branch
3. On feature2, create two commits that add content about one perspective on your topic
4. Switch back to main2 and create a commit with a different perspective
5. Merge feature2 into main2
6. Verify you have a merge commit (not fast-forward)

## Exercise 3: Resolving Conflicts

**Goal:** Practice resolving conflicts when two branches modify the same content differently.

**Checklist:**

- Start with main3
- Create two feature branches that modify the same file
- First merge should be clean
- Second merge creates a conflict
- End with this structure:
  ```
        H  (feature3A)
       /  \
  A---B----J---K  (main3)
       \     /
        I---  (feature3B)
  ```

**Exercise:**

1. Switch to main3
2. Create feature3A and feature3B branches
3. On each branch, create a file with the same name but different content:
   - Both files should address your chosen topic
   - Include sections with the same headings but different content
4. Merge feature3A into main3
5. Try to merge feature3B into main3
6. Resolve the conflict by thoughtfully combining both perspectives
7. Complete the merge

## Exercise 4: Using Branches for Exploration

**Goal:** Experience how branches provide safety for exploring ideas.

**Checklist:**

- Use main-backup as your safe branch
- Create experimental branches to explore different ideas
- End with a structure that shows your exploration

**Exercise:**

1. Switch to main-backup
2. Create an "experimental" branch
3. On this branch, try a completely different approach to your topic
4. If you like it, merge it back
5. If not, create another experimental branch from main-backup

## Challenge: Create a Content Repository

Now that you understand the basics, create a repository on a topic you're passionate about, using branches to:

1. Develop different sections in parallel
2. Explore alternative approaches
3. Practice merging and resolving conflicts

Document your branching strategy in the README and make your repository something you might actually want to share!

## Visualization Checkpoint

After each exercise, visualize your branch structure:

```bash
git log --all --graph --oneline
```

Compare it to the target structure in the checklist to confirm you're on track.
