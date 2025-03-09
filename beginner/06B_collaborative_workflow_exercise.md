# Git Essentials for Beginners - Part 06B: Collaborative Workflow Exercise

## Introduction: Pair Programming with Git

In this exercise, you and a partner will collaborate on solving a simple programming problem using a proper Git workflow. This hands-on practice will reinforce the concepts from Part 06 and help you build muscle memory for common Git collaboration patterns.

You'll experience:

- Creating and working with feature branches
- Pushing and pulling changes
- Managing merge requests
- Handling potential conflicts
- Following commit message conventions

## Setup: Preparing Your Repositories

### Option 1: Work with a Partner

1. One person creates a new repository on GitHub/GitLab
2. Add your partner as a collaborator
3. Both clone the repository to your computers

### Option 2: Simulate Collaboration Yourself

1. Create a new repository on GitHub/GitLab
2. Clone it to two different folders on your computer:

   ```bash
   # First clone
   git clone https://github.com/yourusername/leetcode-collab.git leetcode-main

   # Second clone
   git clone https://github.com/yourusername/leetcode-collab.git leetcode-partner
   ```

3. Work with the two folders as if they were on different computers

## The Problem: Length of Last Word

You'll be implementing a solution to this problem:

**Length of Last Word**

Given a string `s` consisting of words and spaces, return the length of the last word in the string.

A **word** is a maximal substring consisting of non-space characters only.

**Examples:**

```
Input: s = "Hello World"
Output: 5
Explanation: The last word is "World" with length 5.

Input: s = "   fly me   to   the moon  "
Output: 4
Explanation: The last word is "moon" with length 4.

Input: s = "luffy is still joyboy"
Output: 6
Explanation: The last word is "joyboy" with length 6.
```

## Initial Project Setup

Before starting, let's set up the project structure:

1. Create a README.md file with the problem description
2. Add language-specific implementation files

JavaScript (last-word.js):

```javascript
/**
 * @param {string} s
 * @return {number}
 */
var lengthOfLastWord = function (s) {};
```

Java (LastWord.java):

```java
class Solution {
    public int lengthOfLastWord(String s) {

    }
}
```

C# (LastWord.cs):

```csharp
public class Solution {
    public int LengthOfLastWord(string s) {

    }
}
```

Choose whichever language you prefer, or implement it in multiple languages if you want an extra challenge.

## The Collaboration Rules

1. Create a `main` → `dev` → feature branches structure
2. Take turns implementing the solution in 5-minute intervals
3. After each interval:
   - Commit your changes with a proper commit message
   - Push your feature branch
   - Create a merge request to the `dev` branch
4. Your partner then:
   - Reviews the code
   - Merges it to `dev`
   - Creates a new feature branch from the updated `dev`
   - Takes their 5-minute turn

## Step-by-Step Workflow

### Initial Setup (Both Partners)

```bash
# Clone the repository
git clone [repository-url]
cd [repository-name]

# Create the dev branch
git checkout -b dev
git push -u origin dev
```

### Person A: First Implementation

```bash
# Create your feature branch
git checkout dev
git pull origin dev
git checkout -b feature/last-word-length-01

# Make changes to the implementation file
# ... edit the code file ...

# Commit and push
git add .
git commit -m "feat: start implementation with basic structure"
git push -u origin feature/last-word-length-01

# Create merge request to dev (through web interface)
```

### Person B: Continue Implementation

```bash
# After Person A's merge request is accepted:
git checkout dev
git pull origin dev
git checkout -b feature/last-word-length-02

# Make changes to the implementation file
# ... edit the code file ...

# Commit and push
git add .
git commit -m "feat: handle edge cases with spaces"
git push -u origin feature/last-word-length-02

# Create merge request to dev (through web interface)
```

### Continuing the Cycle

Keep alternating, with each person:

1. Creating a new feature branch from updated `dev`
2. Implementing for 5 minutes
3. Committing with a descriptive message
4. Creating a merge request

## Potential Implementation Stages

Split your solution into logical steps:

1. Parse/trim the input string
2. Handle edge cases (extra spaces, empty input)
3. Find the last word
4. Calculate and return the length

Each feature branch could focus on one aspect of the solution.

## Commit Message Examples

Use conventional commit messages:

```
feat: create basic structure for finding last word
feat: implement string trimming and splitting
fix: handle edge case with trailing spaces
refactor: simplify word finding logic
docs: add code comments explaining approach
```

## Handling Conflicts

If conflicts occur naturally during the process, that's a great learning opportunity! Here's how to resolve them:

1. Pull the latest `dev` branch
2. Merge `dev` into your feature branch
3. Resolve conflicts in your editor by choosing which code to keep
4. Complete the merge by adding and committing the resolved files
5. Push your updated feature branch

Don't artificially create conflicts, but don't be afraid if they happen naturally.

## Reflection Questions

After completing the exercise, discuss with your partner:

1. How did breaking the implementation into small, collaborative steps affect the solution quality?
2. Did you encounter any merge conflicts? How did you resolve them?
3. How did the commit message convention help (or not help) in understanding the evolution of the code?
4. What would you do differently in your next collaborative Git project?
5. How did this workflow compare to your previous experiences collaborating on code?

## Final Step: Merge to Main

Once your solution is complete and working:

```bash
git checkout dev
git pull origin dev
git checkout main
git merge dev
git push origin main
```

Congratulations! You've successfully completed a collaborative coding exercise using a professional Git workflow.
