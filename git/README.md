# Git Basics

```
{
  "course_title": "Git Mastery: From Zero to Version Control Hero",
  "course_description": "A comprehensive deep-dive into Git, version control workflows, collaboration, and advanced history management.",
  "course_difficulty": "beginner",
  "course_estimated_duration": "40 hours",
  "tags": [
    "git",
    "version-control",
    "collaboration",
    "devops"
  ],
  "settings": {
    "unlock_mode": "sequential",
    "pass_score": 80,
    "allow_retries": true
  },
  "modules": [
    {
      "title": "Module 1: Foundations of Version Control & Git",
      "description": "Understanding why version control is essential and mastering the basic Git workflow.",
      "objectives": [
        "Understand Version Control Systems (VCS)",
        "Install and configure Git",
        "Initialize a repository",
        "Track changes and commit"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "The Philosophy of Version Control",
          "duration": 10,
          "content": {
            "markdown": "# What is Version Control?\nVersion control is a system that records changes to a file or set of files over time so that you can recall specific versions later. It allows you to revert files to a previous state, revert the entire project, compare changes over time, and see who last modified something."
          }
        },
        {
          "type": "text",
          "title": "Installing and Configuring Git",
          "duration": 15,
          "content": {
            "markdown": "# Getting Started\nDownload Git from git-scm.com. Once installed, configure your identity so your commits are correctly attributed:\n```bash\ngit config --global user.name \"Your Name\"\ngit config --global user.email \"your.email@example.com\"\n```"
          }
        },
        {
          "type": "text",
          "title": "The Basic Git Workflow",
          "duration": 20,
          "content": {
            "markdown": "# Init, Add, Commit\n1. `git init`: Initialize a new Git repository in your current directory.\n2. `git status`: Check the state of your files (modified, staged, untracked).\n3. `git add <file>`: Stage changes for the next commit.\n4. `git commit -m \"message\"`: Save the staged changes to the repository history."
          }
        }
      ],
      "quizzes": [
        {
          "title": "Git Basics Quiz",
          "duration": 5,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "Which command is used to configure your global username in Git?",
                "options": [
                  "git config --global user.name",
                  "git set user.name",
                  "git init user.name",
                  "git config user.name"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What does the 'git add' command do?",
                "options": [
                  "Saves changes to the repository history",
                  "Stages changes for the next commit",
                  "Creates a new branch",
                  "Pushes changes to a remote server"
                ]
              },
              {
                "type": "short_answer",
                "question": "What command do you use to check the current state of your working directory and staging area?"
              },
              {
                "type": "voice_response",
                "question": "Explain the difference between the working directory, the staging area, and the Git repository (HEAD)."
              }
            ]
          }
        }
      ],
      "checkpoint": [
        {
          "type": "code",
          "title": "Your First Commit",
          "duration": 20,
          "content": {
            "prompt": "Initialize a new Git repository, create a file named 'README.md' with the text 'Hello Git', stage the file, and commit it with the message 'Initial commit'. Provide the sequence of Git commands used.",
            "language": "bash",
            "starter_code": "# Write your git commands here\n",
            "socratic_focus": "Focus on the correct sequence of init, add, and commit, and ensuring the file is created before staging."
          }
        }
      ]
    },
    {
      "title": "Module 2: Branching and Merging",
      "description": "Learn how to work on multiple features simultaneously and integrate them safely.",
      "objectives": [
        "Understand Git branches",
        "Create and switch branches",
        "Merge branches",
        "Resolve merge conflicts"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "Understanding Branches",
          "duration": 15,
          "content": {
            "markdown": "# What is a Branch?\nA branch in Git is simply a lightweight movable pointer to a commit. The default branch is usually called `main` or `master`. Branching allows you to diverge from the main line of development and work on features in isolation."
          }
        },
        {
          "type": "text",
          "title": "Branching and Switching",
          "duration": 15,
          "content": {
            "markdown": "# Working with Branches\nCreate a new branch: `git branch <branch-name>`\nSwitch to it: `git checkout <branch-name>`\nOr do both at once: `git checkout -b <branch-name>`"
          }
        },
        {
          "type": "text",
          "title": "Merging and Conflicts",
          "duration": 20,
          "content": {
            "markdown": "# Integrating Changes\nTo merge a branch into your current branch: `git merge <branch-name>`.\nIf both branches modified the same lines in a file, Git will pause and ask you to resolve the merge conflict manually by editing the file, staging it, and committing."
          }
        }
      ],
      "quizzes": [
        {
          "title": "Branching Quiz",
          "duration": 10,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "Which command creates a new branch and switches to it immediately?",
                "options": [
                  "git branch new-branch",
                  "git checkout new-branch",
                  "git checkout -b new-branch",
                  "git merge new-branch"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What happens when you try to merge two branches that have conflicting changes in the same file?",
                "options": [
                  "Git automatically chooses the newer changes",
                  "Git aborts the merge and deletes the branch",
                  "Git pauses the merge and marks the file with conflict markers",
                  "Git creates a new branch with the conflicting changes"
                ]
              },
              {
                "type": "short_answer",
                "question": "What command is used to integrate changes from a specific branch into your current branch?"
              }
            ]
          }
        }
      ],
      "checkpoint": [
        {
          "type": "code",
          "title": "Feature Branch Workflow",
          "duration": 30,
          "content": {
            "prompt": "Create a branch named 'feature-login', switch to it, modify 'README.md' to add a 'Login Feature' section, commit the change, switch back to 'main', and merge 'feature-login' into 'main'.",
            "language": "bash",
            "starter_code": "# Write your git commands here\n",
            "socratic_focus": "Ensure the user correctly switches branches before committing and merges the correct branch into main."
          }
        }
      ]
    },
    {
      "title": "Module 3: Remote Repositories & Collaboration",
      "description": "Connect your local Git repository to remote servers like GitHub to collaborate with others.",
      "objectives": [
        "Understand remote repositories",
        "Clone, push, and pull",
        "Manage remotes",
        "Understand Forks and Pull Requests"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "Working with Remotes",
          "duration": 15,
          "content": {
            "markdown": "# The Distributed Workflow\nGit is a distributed VCS. A remote is a common repository on a server (like GitHub). Use `git remote -v` to see your remotes. The default name for a remote is usually `origin`."
          }
        },
        {
          "type": "text",
          "title": "Cloning, Pushing, and Pulling",
          "duration": 20,
          "content": {
            "markdown": "# Syncing Code\n- `git clone <url>`: Download a remote repository to your local machine.\n- `git push origin <branch>`: Upload your local branch commits to the remote.\n- `git pull`: Fetch changes from the remote and automatically merge them into your current branch."
          }
        },
        {
          "type": "text",
          "title": "Forks and Pull Requests",
          "duration": 15,
          "content": {
            "markdown": "# Collaborating on GitHub\nA fork is your personal server-side copy of someone else's project. A Pull Request (PR) lets you tell project maintainers about the changes you pushed to your fork, proposing that they merge your changes into their main repository."
          }
        }
      ],
      "quizzes": [
        {
          "title": "Remotes Quiz",
          "duration": 10,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "What does the 'git clone' command do?",
                "options": [
                  "Creates a new branch",
                  "Copies a remote repository to your local machine",
                  "Deletes a remote repository",
                  "Merges two remote repositories"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "Which command uploads your local branch commits to the remote repository?",
                "options": [
                  "git pull",
                  "git fetch",
                  "git push",
                  "git merge"
                ]
              },
              {
                "type": "short_answer",
                "question": "What is the term for a personal server-side copy of another user's repository?"
              }
            ]
          }
        }
      ],
      "checkpoint": [
        {
          "type": "code",
          "title": "Pushing to a Remote",
          "duration": 25,
          "content": {
            "prompt": "Assume you have a local repo with a remote named 'origin'. Create a new branch 'feature-x', commit a change, and push this new branch to the remote 'origin' so it tracks the remote branch. Provide the commands.",
            "language": "bash",
            "starter_code": "# Write your git commands here\n",
            "socratic_focus": "Focus on the syntax of pushing a new branch to a remote, e.g., git push -u origin feature-x."
          }
        }
      ]
    },
    {
      "title": "Module 4: Advanced Git Techniques",
      "description": "Master powerful Git tools to save work, rewrite history, and automate tasks.",
      "objectives": [
        "Use git stash",
        "Understand rebase vs merge",
        "Tagging releases",
        "Introduction to Git hooks"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "Stashing Your Work",
          "duration": 15,
          "content": {
            "markdown": "# Temporarily Shelving Changes\nIf you need to switch branches but your working directory is dirty and you aren't ready to commit, use `git stash`. This saves your uncommitted work. Bring them back with `git stash pop`."
          }
        },
        {
          "type": "text",
          "title": "Rebasing",
          "duration": 20,
          "content": {
            "markdown": "# Rebasing vs Merging\nWhile `merge` ties two branches together with a merge commit, `rebase` moves the entire feature branch to begin on the tip of the main branch, creating a perfectly linear history without merge commits."
          }
        },
        {
          "type": "text",
          "title": "Tagging and Hooks",
          "duration": 15,
          "content": {
            "markdown": "# Marking Points in History\nUse `git tag v1.0.0` to mark a specific commit as a release point.\nGit Hooks are scripts that run automatically on events like commit or push, allowing you to enforce code quality or automate deployments."
          }
        }
      ],
      "quizzes": [
        {
          "title": "Advanced Git Quiz",
          "duration": 10,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "What is the primary purpose of 'git stash'?",
                "options": [
                  "To permanently delete uncommitted changes",
                  "To temporarily save uncommitted changes so you can work on something else",
                  "To push changes to a remote server",
                  "To create a new branch"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "How does 'git rebase' differ from 'git merge'?",
                "options": [
                  "Rebase creates a new merge commit, while merge does not.",
                  "Rebase rewrites project history by creating new commits for each commit in the original branch.",
                  "Rebase is used for remote repos, merge is for local repos.",
                  "There is no difference."
                ]
              },
              {
                "type": "short_answer",
                "question": "What command is used to apply the stashed changes and remove them from the stash list?"
              }
            ]
          }
        }
      ],
      "checkpoint": [
        {
          "type": "code",
          "title": "Stash and Tag",
          "duration": 20,
          "content": {
            "prompt": "You have uncommitted changes in 'app.js'. You need to switch branches immediately. Stash your changes, switch to 'main', tag the current commit as 'v1.0', switch back to your original branch, and apply the stash.",
            "language": "bash",
            "starter_code": "# Write your git commands here\n",
            "socratic_focus": "Ensure the correct sequence of stash, checkout, tag, checkout, and stash pop."
          }
        }
      ]
    },
    {
      "title": "Module 5: Fixing Mistakes & Rewriting History",
      "description": "Learn how to recover from errors, undo changes, and safely rewrite Git history.",
      "objectives": [
        "Amend commits",
        "Revert vs Reset",
        "Use the Reflog",
        "Recover lost commits"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "Amending Commits",
          "duration": 10,
          "content": {
            "markdown": "# Fixing the Last Commit\nForgot to add a file or made a typo in the commit message? Use `git commit --amend` to replace the last commit with a new one containing your staged changes and/or corrected message."
          }
        },
        {
          "type": "text",
          "title": "Reverting and Resetting",
          "duration": 20,
          "content": {
            "markdown": "# Undoing Things\n- `git revert <commit>`: Creates a *new* commit that undoes the changes of a previous commit. Safe for public branches.\n- `git reset <commit>`: Moves the branch pointer backward, erasing commits from history. Dangerous for shared branches."
          }
        },
        {
          "type": "text",
          "title": "The Magic of Reflog",
          "duration": 15,
          "content": {
            "markdown": "# Recovering Lost Work\nThe reflog records every time the tip of a branch is updated. If you accidentally delete a branch or hard reset, you can find the lost commit hashes in `git reflog` and restore them using `git reset --hard <hash>`."
          }
        }
      ],
      "quizzes": [
        {
          "title": "Fixing Mistakes Quiz",
          "duration": 10,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "Which command should you use to undo a commit on a shared, public branch without rewriting history?",
                "options": [
                  "git reset --hard",
                  "git revert",
                  "git commit --amend",
                  "git checkout"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What does 'git reflog' help you do?",
                "options": [
                  "View the remote repository logs",
                  "Find hashes of lost commits to restore them",
                  "View the log of all branches in the repository",
                  "Automatically fix merge conflicts"
                ]
              },
              {
                "type": "short_answer",
                "question": "What flag is used with 'git commit' to modify the most recent commit message or add forgotten files?"
              }
            ]
          }
        }
      ],
      "checkpoint": [
        {
          "type": "code",
          "title": "Recovering a Lost Commit",
          "duration": 30,
          "content": {
            "prompt": "You just accidentally ran 'git reset --hard HEAD~1' and lost your last commit. How do you find the hash of the lost commit using the reflog and restore your branch to that state?",
            "language": "bash",
            "starter_code": "# Write your git commands here\n",
            "socratic_focus": "Focus on using git reflog to find the hash and git reset --hard <hash> to restore it."
          }
        }
      ]
    }
  ],
  "final_project": {
    "id": "final-oss-contribution",
    "title": "The Open Source Contribution Simulator",
    "description": "Simulate a real-world open source contribution. Fork a provided repository, clone it locally, create a feature branch, implement a new feature (e.g., adding a new function to a calculator or a new CSS style), push to your fork, and submit a Pull Request to the original repository."
  }
}
```