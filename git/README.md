# Git Basics

{
  "course_title": "Git: From Confused to Confident",
  "course_description": "A comprehensive, hands-on journey through Git — the world's most widely used version control system. You'll go from understanding what version control even is, all the way to mastering branching strategies, merge conflicts, rebasing, hooks, and collaborating on real-world team workflows using GitHub.",
  "course_difficulty": "beginner",
  "course_estimated_duration": "50 hours",
  "tags": [
    "git",
    "version-control",
    "github",
    "devops",
    "collaboration",
    "workflow"
  ],
  "settings": {
    "unlock_mode": "sequential",
    "pass_score": 80,
    "allow_retries": true
  },
  "modules": [
    {
      "title": "Module 1: What is Version Control?",
      "description": "Before touching Git, we need to understand why it exists and what problem it solves.",
      "objectives": [
        "Understand what version control is and why it matters",
        "Distinguish between centralized and distributed VCS",
        "Appreciate the history and philosophy of Git"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "The Problem Git Solves",
          "duration": 10,
          "content": {
            "markdown": "# The Problem Git Solves\n\nImagine you're writing an essay. You save it as `essay.docx`. Then you edit it and save `essay_v2.docx`. Then `essay_final.docx`. Then `essay_final_REAL.docx`.\n\nNow multiply that chaos across a team of 10 developers, all editing the same codebase at the same time.\n\nVersion control systems (VCS) exist to solve this exact problem. They track every change made to a set of files over time, so you can:\n\n- See who changed what and when\n- Revert to any previous state\n- Work on new features without breaking existing code\n- Collaborate without stepping on each other's toes\n\nGit is the most widely used VCS in the world today. It powers GitHub, GitLab, Bitbucket, and is used by virtually every software company on the planet."
          }
        },
        {
          "type": "text",
          "title": "Centralized vs Distributed VCS",
          "duration": 10,
          "content": {
            "markdown": "# Centralized vs Distributed Version Control\n\n## Centralized VCS (CVCS)\nIn a centralized system like SVN (Subversion), there is **one central server** that holds all the versions of the files. Developers check out files from this central place and commit changes back to it.\n\n**Problem**: If the server goes down, nobody can work. If it's lost, history is gone.\n\n## Distributed VCS (DVCS)\nIn a distributed system like Git, **every developer has a full copy of the entire history** on their machine. There's no single point of failure.\n\nYou can:\n- Commit changes offline\n- See the full project history without internet access\n- Push and pull changes between multiple remotes\n\nThis is why Git is so powerful — it's decentralized by design."
          }
        },
        {
          "type": "text",
          "title": "A Brief History of Git",
          "duration": 10,
          "content": {
            "markdown": "# A Brief History of Git\n\nGit was created in **2005** by **Linus Torvalds** — the same person who created the Linux kernel.\n\nThe Linux kernel project had been using a proprietary distributed VCS called BitKeeper. When the free license for BitKeeper was revoked, Linus decided to write his own system. In just a few weeks, Git was born.\n\n## Git's Design Goals\n\nLinus designed Git with these principles:\n\n1. **Speed** — committing, branching, and merging should be near-instant\n2. **Simplicity** — simple design\n3. **Strong support for non-linear development** — thousands of parallel branches\n4. **Fully distributed** — no central authority required\n5. **Integrity** — every file and commit is checksummed with SHA-1\n\nToday, Git is maintained as open-source software and is used by millions of developers worldwide."
          }
        }
      ],
      "quizzes": [
        {
          "title": "Version Control Fundamentals Quiz",
          "duration": 5,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "Who created Git?",
                "options": [
                  "Linus Torvalds",
                  "Dennis Ritchie",
                  "Guido van Rossum",
                  "Brendan Eich"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What is the key advantage of a distributed VCS over a centralized one?",
                "options": [
                  "It is faster to set up",
                  "Every developer has the full history locally",
                  "It requires less disk space",
                  "It only allows one person to commit at a time"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "In what year was Git created?",
                "options": [
                  "1999",
                  "2001",
                  "2005",
                  "2010"
                ]
              },
              {
                "type": "short_answer",
                "question": "Name one popular platform that hosts Git repositories."
              },
              {
                "type": "voice_response",
                "question": "In your own words, explain what problem version control solves for software teams."
              }
            ]
          }
        }
      ],
      "checkpoint": []
    },
    {
      "title": "Module 2: Installing Git & Your First Repository",
      "description": "Get Git installed, configure it with your identity, and create your very first repository.",
      "objectives": [
        "Install Git on your operating system",
        "Configure your global identity",
        "Understand what a repository is",
        "Initialize a local Git repository"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "Installing Git",
          "duration": 10,
          "content": {
            "markdown": "# Installing Git\n\n## Windows\nDownload the installer from [git-scm.com](https://git-scm.com). During installation, use the recommended defaults. This also installs **Git Bash**, a terminal emulator you'll use to run Git commands.\n\n## macOS\nRun this in your Terminal:\n```bash\nbrew install git\n```\nIf you don't have Homebrew, install it first from [brew.sh](https://brew.sh).\n\nAlternatively, installing Xcode Command Line Tools also installs Git:\n```bash\nxcode-select --install\n```\n\n## Linux (Ubuntu/Debian)\n```bash\nsudo apt update && sudo apt install git\n```\n\n## Verify the Installation\n```bash\ngit --version\n```\nYou should see output like: `git version 2.43.0`"
          }
        },
        {
          "type": "text",
          "title": "Configuring Your Identity",
          "duration": 10,
          "content": {
            "markdown": "# Configuring Your Git Identity\n\nBefore you make any commits, you need to tell Git who you are. This information is attached to every commit you make.\n\n## Setting Your Name and Email\n```bash\ngit config --global user.name \"Your Name\"\ngit config --global user.email \"you@example.com\"\n```\n\nThe `--global` flag applies this to all repositories on your machine. You can override it per-project by running the command without `--global` inside a repository.\n\n## Setting a Default Editor\nGit sometimes opens a text editor (for commit messages, etc.). Set it to something familiar:\n```bash\n# VS Code\ngit config --global core.editor \"code --wait\"\n\n# Nano (simple terminal editor)\ngit config --global core.editor nano\n```\n\n## Viewing Your Config\n```bash\ngit config --list\n```"
          }
        },
        {
          "type": "text",
          "title": "What is a Repository?",
          "duration": 10,
          "content": {
            "markdown": "# What is a Git Repository?\n\nA **repository** (or **repo**) is a directory that Git is tracking. It contains:\n\n- Your project files\n- A hidden `.git/` folder that stores the entire history and metadata\n\n## The `.git/` Folder\nWhen you initialize a Git repo, a `.git/` folder is created. You should **never manually edit** this folder. Inside it, Git stores:\n\n- All your commits and their history\n- Branch pointers\n- Configuration for this specific repo\n- The staging index\n\n## Two Ways to Get a Repo\n1. **Initialize a new one** from an existing folder: `git init`\n2. **Clone an existing one** from a remote: `git clone <url>`\n\nWe'll cover cloning in a later module."
          }
        }
      ],
      "quizzes": [
        {
          "title": "Setup & Repository Quiz",
          "duration": 5,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "Which command verifies that Git is correctly installed?",
                "options": [
                  "git check",
                  "git --version",
                  "git status",
                  "git verify"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What does the --global flag do in git config?",
                "options": [
                  "Applies the setting to the internet",
                  "Applies the setting to all repositories on your machine",
                  "Applies the setting to a remote server",
                  "Applies the setting to the current commit only"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "Where does Git store all its internal data for a repository?",
                "options": [
                  ".gitconfig/",
                  ".git/",
                  "git/",
                  ".version/"
                ]
              },
              {
                "type": "short_answer",
                "question": "What command initializes a new Git repository in the current directory?"
              },
              {
                "type": "voice_response",
                "question": "Explain in your own words what a Git repository is and what it contains."
              }
            ]
          }
        }
      ],
      "checkpoint": [
        {
          "type": "code",
          "title": "Initialize Your First Repo",
          "duration": 15,
          "content": {
            "prompt": "Using the terminal, write the sequence of commands to: (1) create a new directory called 'my-first-repo', (2) navigate into it, and (3) initialize it as a Git repository. Then verify it was created by listing hidden files.",
            "language": "bash",
            "starter_code": "# Write your commands here\n",
            "socratic_focus": "Ask the student what they see after running git init and what the .git folder might contain."
          }
        }
      ]
    },
    {
      "title": "Module 3: The Three Stages & Your First Commit",
      "description": "Understand Git's fundamental workflow: working directory, staging area, and the repository.",
      "objectives": [
        "Understand the three stages of Git",
        "Use git add to stage changes",
        "Use git commit to save a snapshot",
        "Use git status and git log"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "Git's Three Stages",
          "duration": 15,
          "content": {
            "markdown": "# Git's Three Stages\n\nThis is the single most important concept to understand in Git. Every file in a Git repository is in one of three states:\n\n## 1. Working Directory (Modified)\nThis is where you edit files normally. Changes here are **not yet tracked** by Git — they're just changes on your filesystem.\n\n## 2. Staging Area (Staged / Index)\nThe staging area is like a **loading dock**. You selectively choose which changes you want to include in your next commit and `add` them here. This lets you craft precise, meaningful commits rather than committing everything at once.\n\n## 3. Repository (Committed)\nOnce you commit, the staged changes become a permanent **snapshot** in your Git history. This is stored in the `.git/` directory.\n\n## The Workflow\n```\nEdit files → Stage changes → Commit snapshot\n(Working Dir)  (git add)      (git commit)\n```\n\nThink of it like taking a photo:\n- Working directory = arranging subjects for the photo\n- Staging area = choosing exactly who/what is in the frame\n- Commit = pressing the shutter — a permanent snapshot is saved"
          }
        },
        {
          "type": "text",
          "title": "Checking Status and Staging Files",
          "duration": 15,
          "content": {
            "markdown": "# Checking Status and Staging Files\n\n## git status\nYour most-used command. Always shows you what's happening:\n```bash\ngit status\n```\nOutput tells you:\n- Which branch you're on\n- Files that are staged (green)\n- Files that are modified but not staged (red)\n- Untracked files (not in Git yet)\n\n## git add — Staging Changes\nStage a specific file:\n```bash\ngit add filename.txt\n```\n\nStage all changes in the current directory:\n```bash\ngit add .\n```\n\nStage specific parts of a file interactively (advanced):\n```bash\ngit add -p filename.txt\n```\n\n## Unstaging a File\nIf you accidentally staged something:\n```bash\ngit restore --staged filename.txt\n```"
          }
        },
        {
          "type": "text",
          "title": "Making Your First Commit",
          "duration": 15,
          "content": {
            "markdown": "# Making Your First Commit\n\n## git commit\nOnce you have files staged, commit them:\n```bash\ngit commit -m \"Your commit message here\"\n```\n\nThe `-m` flag lets you write the message inline. Without it, Git opens your configured editor.\n\n## Writing Good Commit Messages\nA good commit message:\n- Is written in the **imperative mood**: 'Add feature' not 'Added feature'\n- Is concise but descriptive\n- Explains **what** changed and **why**, not how\n\n**Good**: `Fix login redirect loop for expired sessions`\n**Bad**: `stuff` or `fixed bug`\n\n## Viewing History with git log\n```bash\ngit log\n```\nShows all commits with their SHA hash, author, date, and message.\n\nUseful variations:\n```bash\ngit log --oneline          # Compact one-line format\ngit log --oneline --graph  # ASCII branch graph\ngit log --author=\"Bright\"  # Filter by author\n```"
          }
        }
      ],
      "quizzes": [
        {
          "title": "Staging & Commits Quiz",
          "duration": 10,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "What does the staging area allow you to do?",
                "options": [
                  "Permanently delete files from the repository",
                  "Selectively choose which changes to include in the next commit",
                  "Push changes to a remote server",
                  "View the full commit history"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "Which command shows you the current state of your working directory and staging area?",
                "options": [
                  "git log",
                  "git history",
                  "git status",
                  "git show"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What is a Git commit?",
                "options": [
                  "A temporary save that can be undone easily",
                  "A permanent snapshot of your staged changes stored in history",
                  "A file sent to a remote server",
                  "A branch of the repository"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "How do you stage all changes in the current directory?",
                "options": [
                  "git commit .",
                  "git push .",
                  "git add .",
                  "git stage --all"
                ]
              },
              {
                "type": "short_answer",
                "question": "Write the command to make a commit with the message 'Initial project setup'."
              },
              {
                "type": "voice_response",
                "question": "Describe Git's three stages in your own words and give an analogy that helps you remember them."
              }
            ]
          }
        }
      ],
      "checkpoint": [
        {
          "type": "code",
          "title": "Your First Real Commit",
          "duration": 20,
          "content": {
            "prompt": "Inside a Git repository, write the sequence of bash commands to: (1) create a file called README.md with the text '# My Project', (2) check the current status, (3) stage the file, (4) commit it with the message 'Add project README', and (5) view the commit log.",
            "language": "bash",
            "starter_code": "# Step-by-step: create, stage, and commit a file\n",
            "socratic_focus": "Ask the student what git status showed before and after staging, and what information git log displays."
          }
        }
      ]
    },
    {
      "title": "Module 4: Branching — Git's Superpower",
      "description": "Branching is what makes Git extraordinary. Learn to create, switch, and manage branches.",
      "objectives": [
        "Understand what a branch is conceptually",
        "Create and switch branches",
        "Merge branches together",
        "Delete branches after merging"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "What is a Branch?",
          "duration": 15,
          "content": {
            "markdown": "# What is a Branch?\n\nA branch in Git is simply a **lightweight, movable pointer to a commit**.\n\nWhen you make commits, the branch pointer automatically moves forward to point to your latest commit. The default branch is called `main` (or `master` in older repos).\n\n## Why Branch?\nBranches let you:\n- Work on a new feature without touching production code\n- Fix a bug in isolation\n- Experiment freely and throw it away if it doesn't work\n- Have multiple team members working in parallel without conflicts\n\n## The HEAD Pointer\n`HEAD` is a special pointer that tells Git: **\"this is where I am right now\"**. It usually points to the current branch, which points to the latest commit.\n\n```\nmain: A → B → C  ← HEAD\n```\n\nWhen you create a new branch:\n```\nmain:    A → B → C\nfeature:         C  ← HEAD (same starting point)\n```\n\nNow commits on `feature` diverge from `main`."
          }
        },
        {
          "type": "text",
          "title": "Creating and Switching Branches",
          "duration": 15,
          "content": {
            "markdown": "# Creating and Switching Branches\n\n## Creating a Branch\n```bash\ngit branch feature-login\n```\nThis creates the branch but does NOT switch to it.\n\n## Switching to a Branch\n```bash\ngit switch feature-login\n```\nor the older syntax:\n```bash\ngit checkout feature-login\n```\n\n## Create and Switch in One Command\n```bash\ngit switch -c feature-login\n# or\ngit checkout -b feature-login\n```\n\n## Listing Branches\n```bash\ngit branch          # Local branches\ngit branch -a       # All branches (including remote)\ngit branch -v       # With last commit info\n```\n\n## The Active Branch\nThe branch with an asterisk `*` next to it (or highlighted) is your current branch.\n\n**Tip**: Always know which branch you're on before making commits. `git status` always shows the current branch at the top."
          }
        },
        {
          "type": "text",
          "title": "Merging Branches",
          "duration": 15,
          "content": {
            "markdown": "# Merging Branches\n\nOnce your feature is done, you merge it back into `main`.\n\n## How to Merge\nFirst, switch to the branch you want to merge **into**:\n```bash\ngit switch main\n```\nThen merge:\n```bash\ngit merge feature-login\n```\n\n## Types of Merges\n\n### Fast-Forward Merge\nIf `main` hasn't changed since you branched off, Git simply moves the `main` pointer forward. No merge commit is created.\n```\nBefore:  main → C,  feature → C → D → E\nAfter:   main → E (fast-forwarded)\n```\n\n### Three-Way Merge\nIf `main` has new commits since you branched, Git creates a new **merge commit** that has two parents.\n```\nmain:    A → B → C → F (merge commit)\nfeature:         ↑→ D → E ↗\n```\n\n## Deleting a Merged Branch\nAfter merging, the branch is no longer needed:\n```bash\ngit branch -d feature-login\n```\nUse `-D` (capital D) to force-delete an unmerged branch."
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
                "question": "What is a Git branch technically?",
                "options": [
                  "A copy of the entire repository",
                  "A lightweight movable pointer to a commit",
                  "A folder inside the .git directory",
                  "A remote version of the repository"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "Which command creates a new branch AND switches to it in one step?",
                "options": [
                  "git branch -new feature",
                  "git switch feature",
                  "git switch -c feature",
                  "git create feature"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What is a fast-forward merge?",
                "options": [
                  "A merge that happens instantly without checking for conflicts",
                  "A merge where Git moves the branch pointer forward because the base branch has no new commits",
                  "A merge that skips the staging area",
                  "A merge that deletes the source branch automatically"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What does HEAD point to?",
                "options": [
                  "The remote origin branch",
                  "Always the main branch",
                  "Your current position in the repository",
                  "The first commit ever made"
                ]
              },
              {
                "type": "short_answer",
                "question": "What command would you run to delete a branch called 'old-feature' after it has been merged?"
              },
              {
                "type": "voice_response",
                "question": "Explain why branching is useful in a team environment. What would happen if everyone committed directly to main?"
              }
            ]
          }
        }
      ],
      "checkpoint": [
        {
          "type": "code",
          "title": "Branch, Commit, and Merge",
          "duration": 25,
          "content": {
            "prompt": "Write a sequence of bash commands that: (1) creates and switches to a new branch called 'add-about-page', (2) creates a file called about.html with some content, (3) stages and commits it with a meaningful message, (4) switches back to main, (5) merges 'add-about-page' into main, and (6) deletes the 'add-about-page' branch.",
            "language": "bash",
            "starter_code": "# Branch → develop → merge → clean up\n",
            "socratic_focus": "Ask the student what type of merge occurred (fast-forward or three-way) and how they can tell."
          }
        }
      ]
    },
    {
      "title": "Module 5: Merge Conflicts — Don't Panic",
      "description": "Merge conflicts are a normal part of collaboration. Learn to read them, resolve them, and move on.",
      "objectives": [
        "Understand what causes a merge conflict",
        "Read and interpret conflict markers",
        "Manually resolve conflicts",
        "Use tools to help with conflict resolution"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "What Causes a Merge Conflict?",
          "duration": 10,
          "content": {
            "markdown": "# What Causes a Merge Conflict?\n\nA merge conflict happens when two branches have **changed the same part of the same file** and Git cannot automatically decide which version to keep.\n\n## Scenario\n1. You and a teammate both branch off `main`\n2. You both edit line 5 of `index.html`\n3. Your teammate merges their branch first\n4. When you try to merge yours, Git says: **CONFLICT**\n\nGit is not broken — it's doing its job. It's telling you: \"I found two different changes to the same place. You need to decide which one to keep.\"\n\n## What Does NOT Cause a Conflict\n- Changes to different files\n- Changes to different parts of the same file\n- One branch adds a file, the other doesn't touch it\n\nGit handles all of those automatically."
          }
        },
        {
          "type": "text",
          "title": "Reading Conflict Markers",
          "duration": 15,
          "content": {
            "markdown": "# Reading Conflict Markers\n\nWhen a conflict occurs, Git edits the conflicted file and inserts special markers:\n\n```\n<<<<<<< HEAD\nThis is the content from YOUR current branch\n=======\nThis is the content from the branch being MERGED IN\n>>>>>>> feature-branch\n```\n\n## Breaking It Down\n- `<<<<<<< HEAD` — start of YOUR changes (the branch you're on)\n- `=======` — the dividing line between the two versions\n- `>>>>>>> feature-branch` — end of THEIR changes (the branch you're merging)\n\n## Your Job\nYou must:\n1. Open the conflicted file in your editor\n2. Decide what the final content should be (keep yours, keep theirs, or combine both)\n3. **Delete ALL the conflict markers** (`<<<<`, `====`, `>>>>`)\n4. Save the file\n5. `git add` the resolved file\n6. `git commit` to complete the merge"
          }
        },
        {
          "type": "text",
          "title": "Resolving Conflicts and Using Tools",
          "duration": 15,
          "content": {
            "markdown": "# Resolving Conflicts\n\n## Step-by-Step Resolution\n```bash\n# 1. After a failed merge, check which files conflict\ngit status\n\n# 2. Open each conflicted file and resolve manually\n# (edit in your editor, remove all conflict markers)\n\n# 3. Stage the resolved files\ngit add resolved-file.html\n\n# 4. Complete the merge\ngit commit\n# (Git auto-generates the merge commit message)\n```\n\n## Aborting a Merge\nIf you're overwhelmed and want to start over:\n```bash\ngit merge --abort\n```\nThis cancels the merge and returns your branch to the state before the merge began.\n\n## Using a Visual Merge Tool\nMost editors have built-in merge conflict resolution:\n- **VS Code**: Click 'Accept Current', 'Accept Incoming', or 'Accept Both Changes' directly in the editor\n- **Command line tool**: `git mergetool`\n\n## Best Practice\nSmall, frequent merges create smaller conflicts. The longer you wait to merge, the worse the conflicts tend to be."
          }
        }
      ],
      "quizzes": [
        {
          "title": "Merge Conflicts Quiz",
          "duration": 10,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "What triggers a merge conflict in Git?",
                "options": [
                  "Two branches modifying different files",
                  "Two branches modifying the same lines in the same file",
                  "Forgetting to run git add before committing",
                  "Having too many branches"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "In a conflict marker, what does the content between <<<<<<< HEAD and ======= represent?",
                "options": [
                  "The version from the remote server",
                  "The original file before any edits",
                  "The changes from YOUR current branch",
                  "The changes from the branch being merged in"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "After manually resolving a conflict in a file, what is the next step?",
                "options": [
                  "git merge --continue",
                  "git add the resolved file, then git commit",
                  "git push the changes immediately",
                  "git reset and start over"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "Which command cancels an in-progress merge and returns to the pre-merge state?",
                "options": [
                  "git merge --stop",
                  "git merge --cancel",
                  "git merge --abort",
                  "git reset --merge"
                ]
              },
              {
                "type": "short_answer",
                "question": "What must you remove from a conflicted file before staging it as resolved?"
              },
              {
                "type": "voice_response",
                "question": "Walk through the steps you would take when you encounter a merge conflict, from the moment Git reports it to the completed merge."
              }
            ]
          }
        }
      ],
      "checkpoint": [
        {
          "type": "code",
          "title": "Simulate and Resolve a Conflict",
          "duration": 30,
          "content": {
            "prompt": "Set up a merge conflict scenario: (1) Create a file 'bio.txt' on main with one line of text and commit it. (2) Create branch 'version-a', change the first line, and commit. (3) Switch back to main, change the same first line to something different, and commit. (4) Merge 'version-a' into main. Show what the conflict markers look like, then write the resolved version of the file and the commands to complete the merge.",
            "language": "bash",
            "starter_code": "# Set up conflict scenario\n# Then resolve it step by step\n",
            "socratic_focus": "Ask the student: how did you decide which version to keep? What would you do if you needed content from BOTH versions?"
          }
        }
      ]
    },
    {
      "title": "Module 6: Working with Remotes & GitHub",
      "description": "Connect your local Git repository to the world using remote repositories on GitHub.",
      "objectives": [
        "Understand what a remote is",
        "Clone a repository from GitHub",
        "Push and pull changes",
        "Understand fetch vs pull"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "What is a Remote?",
          "duration": 10,
          "content": {
            "markdown": "# What is a Remote Repository?\n\nA **remote** is a version of your repository hosted on the internet (or a network). It allows:\n- Team members to share code\n- Backup of your project\n- Continuous integration and deployment pipelines\n\n## Common Remote Hosts\n- **GitHub** (most popular, owned by Microsoft)\n- **GitLab** (self-hostable, strong CI/CD)\n- **Bitbucket** (popular in enterprise)\n\n## The 'origin' Convention\nBy convention, the primary remote is named `origin`. When you clone a repository, Git automatically names the source remote `origin`.\n\n## Viewing Remotes\n```bash\ngit remote -v\n```\nShows all remotes and their URLs:\n```\norigin  https://github.com/username/repo.git (fetch)\norigin  https://github.com/username/repo.git (push)\n```\n\n## Adding a Remote Manually\n```bash\ngit remote add origin https://github.com/username/repo.git\n```"
          }
        },
        {
          "type": "text",
          "title": "Cloning, Pushing and Pulling",
          "duration": 20,
          "content": {
            "markdown": "# Cloning, Pushing, and Pulling\n\n## Cloning a Repository\nGet a full copy of a remote repository:\n```bash\ngit clone https://github.com/username/repo.git\n```\nThis creates a new folder, downloads the entire history, and sets up `origin` automatically.\n\n## Pushing — Sending Your Changes Up\n```bash\ngit push origin main\n```\nThis pushes your local `main` branch to the remote `origin`.\n\nFirst-time push for a new branch:\n```bash\ngit push -u origin feature-branch\n```\nThe `-u` flag sets the upstream, so future pushes can just be `git push`.\n\n## Pulling — Getting Remote Changes Down\n```bash\ngit pull origin main\n```\n`git pull` is actually a combination of two operations:\n1. `git fetch` — downloads new commits from the remote\n2. `git merge` — merges them into your current branch\n\n## Fetch vs Pull\n- `git fetch` — downloads changes but does NOT merge them. Safe, lets you inspect before merging.\n- `git pull` — downloads AND merges immediately.\n\nPro tip: `git fetch` first, review with `git log origin/main`, then merge manually for full control."
          }
        },
        {
          "type": "text",
          "title": "GitHub: Issues, PRs and Forks",
          "duration": 15,
          "content": {
            "markdown": "# GitHub: Beyond Just Storage\n\nGitHub adds a collaboration layer on top of Git.\n\n## Pull Requests (PRs)\nA **Pull Request** is a GitHub feature (not a Git feature) that lets you:\n1. Push your feature branch to GitHub\n2. Open a PR to request merging it into `main`\n3. Team members review, comment, request changes\n4. Once approved, it gets merged\n\nThis is the standard team workflow at virtually every software company.\n\n## Issues\nGitHub Issues are used to track:\n- Bugs\n- Feature requests\n- Tasks\n\nYou can reference issues in commit messages: `Fix login bug (closes #42)` — this automatically closes issue #42 when merged.\n\n## Forks\nA **fork** is a personal copy of someone else's repository on GitHub. Common in open-source:\n1. Fork the repo to your GitHub account\n2. Clone your fork locally\n3. Make changes and push to YOUR fork\n4. Open a PR from your fork to the original repo\n\n## Keeping Your Fork Updated\n```bash\ngit remote add upstream https://github.com/original/repo.git\ngit fetch upstream\ngit merge upstream/main\n```"
          }
        }
      ],
      "quizzes": [
        {
          "title": "Remotes & GitHub Quiz",
          "duration": 10,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "By convention, what is the default remote name when you clone a repository?",
                "options": [
                  "main",
                  "upstream",
                  "origin",
                  "remote"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What is the difference between git fetch and git pull?",
                "options": [
                  "fetch is faster than pull",
                  "fetch downloads changes but doesn't merge; pull downloads AND merges",
                  "fetch only works on GitHub; pull works on any remote",
                  "There is no difference"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What is a Pull Request on GitHub?",
                "options": [
                  "A Git command to pull changes from a remote",
                  "A GitHub feature for proposing and reviewing changes before merging",
                  "A request to delete a branch",
                  "A way to download a repository"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What does git push -u origin feature-branch do?",
                "options": [
                  "Pushes main to origin",
                  "Pushes the branch and sets origin as the upstream tracking branch",
                  "Updates the remote URL",
                  "Fetches the latest changes from origin"
                ]
              },
              {
                "type": "short_answer",
                "question": "What is a fork on GitHub and how is it different from cloning?"
              },
              {
                "type": "voice_response",
                "question": "Describe the full Pull Request workflow — from creating a feature branch locally to having it merged into main on GitHub."
              }
            ]
          }
        }
      ],
      "checkpoint": [
        {
          "type": "code",
          "title": "Push a Branch to GitHub",
          "duration": 20,
          "content": {
            "prompt": "Write the complete sequence of commands to: (1) connect a local repository to a GitHub remote at https://github.com/yourname/demo-project.git, (2) create and switch to a branch called 'update-readme', (3) make a change and commit it, (4) push the branch to GitHub with upstream tracking, and (5) view the list of remotes.",
            "language": "bash",
            "starter_code": "# Connect, branch, commit, and push\n",
            "socratic_focus": "Ask the student what they would need to do on GitHub after pushing the branch if they wanted a teammate to review the changes."
          }
        }
      ]
    },
    {
      "title": "Module 7: Undoing Things in Git",
      "description": "Git's superpower is that almost nothing is permanent. Learn how to undo, revert, reset, and recover.",
      "objectives": [
        "Discard working directory changes",
        "Unstage files",
        "Amend the last commit",
        "Use git revert to undo public commits safely",
        "Understand git reset and its modes"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "Discarding and Unstaging Changes",
          "duration": 10,
          "content": {
            "markdown": "# Discarding and Unstaging Changes\n\n## Discard Changes in Working Directory\nThrew changes that you don't want to keep?\n```bash\ngit restore filename.txt\n```\nThis reverts the file to the last committed version. **Warning: this is irreversible — the changes are gone.**\n\nDiscard ALL working directory changes:\n```bash\ngit restore .\n```\n\n## Unstage a File\nYou staged a file but realized it shouldn't be in this commit:\n```bash\ngit restore --staged filename.txt\n```\nThe file goes back to the working directory (changes are still there, just unstaged).\n\n## Undo a git add (older syntax)\n```bash\ngit reset HEAD filename.txt\n```\nSame effect as `git restore --staged` — the file is unstaged but changes remain."
          }
        },
        {
          "type": "text",
          "title": "Amending Commits and git revert",
          "duration": 15,
          "content": {
            "markdown": "# Amending and Reverting Commits\n\n## Amending the Last Commit\nMade a typo in your commit message? Forgot to include a file?\n```bash\ngit commit --amend\n```\nThis lets you:\n- Edit the commit message\n- Add more staged files to the last commit\n\n**Important**: Only amend commits that have NOT been pushed to a shared remote. Amending rewrites history, which causes problems for teammates.\n\n## git revert — The Safe Undo\n`git revert` creates a **new commit** that undoes the changes of a previous commit. It doesn't rewrite history — it adds to it.\n\n```bash\ngit revert abc1234   # Use the commit hash\n```\nThis is the **safe** way to undo public commits because history is preserved.\n\n```\nBefore: A → B → C\nAfter:  A → B → C → D (D reverses the changes in C)\n```"
          }
        },
        {
          "type": "text",
          "title": "git reset — The Powerful (and Dangerous) Undo",
          "duration": 20,
          "content": {
            "markdown": "# git reset — Moving the Branch Pointer\n\n`git reset` moves the current branch pointer to a different commit. It has three modes:\n\n## --soft: Keep Changes Staged\n```bash\ngit reset --soft HEAD~1\n```\n- Moves back one commit\n- Changes from that commit go back to the **staging area**\n- Use case: undo a commit but keep the changes ready to re-commit\n\n## --mixed (default): Keep Changes Unstaged\n```bash\ngit reset HEAD~1\n# or\ngit reset --mixed HEAD~1\n```\n- Moves back one commit\n- Changes go back to the **working directory** (unstaged)\n- Use case: undo a commit and unstage the changes\n\n## --hard: Discard Everything\n```bash\ngit reset --hard HEAD~1\n```\n- Moves back one commit\n- All changes from that commit are **permanently discarded**\n- **Dangerous** — cannot easily recover these changes\n\n## HEAD~N Notation\n- `HEAD~1` = one commit before current\n- `HEAD~3` = three commits before current\n- Or use the commit hash: `git reset abc1234`\n\n**Rule**: Never use `git reset` on commits that have been pushed to a shared remote. Use `git revert` instead."
          }
        }
      ],
      "quizzes": [
        {
          "title": "Undoing Changes Quiz",
          "duration": 10,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "Which command safely undoes a public commit by creating a new commit that reverses the changes?",
                "options": [
                  "git reset --hard",
                  "git undo",
                  "git revert",
                  "git restore"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What does git reset --soft HEAD~1 do?",
                "options": [
                  "Deletes the last commit and discards all changes",
                  "Moves back one commit and keeps changes in the staging area",
                  "Moves back one commit and keeps changes in the working directory",
                  "Reverts the repository to the first commit"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "You staged a file by mistake. Which command removes it from the staging area while keeping the changes?",
                "options": [
                  "git restore filename.txt",
                  "git restore --staged filename.txt",
                  "git reset --hard filename.txt",
                  "git drop filename.txt"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "Why is git reset --hard dangerous when used on pushed commits?",
                "options": [
                  "It can corrupt the .git folder",
                  "It deletes the remote repository",
                  "It rewrites history, causing conflicts for teammates who have the old commits",
                  "It can only be run by administrators"
                ]
              },
              {
                "type": "short_answer",
                "question": "What command would you use to fix a typo in your most recent commit message before pushing?"
              },
              {
                "type": "voice_response",
                "question": "A teammate pushed a buggy commit to main. Should you use git reset or git revert to fix it? Why?"
              }
            ]
          }
        }
      ],
      "checkpoint": [
        {
          "type": "code",
          "title": "Undo Scenarios",
          "duration": 20,
          "content": {
            "prompt": "For each scenario, write the correct Git command: (1) You want to discard unsaved changes to 'app.js' in your working directory. (2) You staged 'test.js' but don't want it in this commit. (3) You want to undo the last commit but keep the changes staged. (4) A commit hash abc123 was pushed to main and introduced a bug — undo it safely. (5) Amend your last commit to add a forgotten file 'config.js'.",
            "language": "bash",
            "starter_code": "# Scenario 1:\n\n# Scenario 2:\n\n# Scenario 3:\n\n# Scenario 4:\n\n# Scenario 5:\ngit add config.js\n",
            "socratic_focus": "Ask the student: for scenario 4, why can't we use git reset instead of git revert?"
          }
        }
      ]
    },
    {
      "title": "Module 8: Rebasing — Rewriting History Cleanly",
      "description": "Rebase is an alternative to merge that produces a cleaner, linear project history.",
      "objectives": [
        "Understand the difference between merge and rebase",
        "Perform a basic rebase",
        "Use interactive rebase to clean up commits",
        "Know when to rebase and when not to"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "Merge vs Rebase",
          "duration": 15,
          "content": {
            "markdown": "# Merge vs Rebase\n\nBoth merge and rebase integrate changes from one branch into another. They differ in *how* they do it.\n\n## Merge\n```\nmain:    A → B → C → F (merge commit)\nfeature:         ↑→ D → E ↗\n```\nMerge preserves the full history exactly as it happened. A merge commit is created showing when the branches joined.\n\n**Pros**: True historical record, non-destructive\n**Cons**: Messy, non-linear history with many branches\n\n## Rebase\n```\nBefore:\nmain:    A → B → C\nfeature:         D → E\n\nAfter rebase:\nmain:    A → B → C\nfeature:             C → D' → E'\n```\nRebase **replays** your commits on top of the target branch. The result is a clean, linear history.\n\n**Pros**: Clean linear history, easier to read\n**Cons**: Rewrites commit hashes (D becomes D'), dangerous on shared branches\n\n**The Golden Rule**: Never rebase branches that others are working on."
          }
        },
        {
          "type": "text",
          "title": "Performing a Rebase",
          "duration": 15,
          "content": {
            "markdown": "# Performing a Rebase\n\n## Basic Rebase\nBring your feature branch up to date with main:\n```bash\n# On your feature branch\ngit switch feature-login\ngit rebase main\n```\nThis replays your feature commits on top of the latest main.\n\n## Rebase Conflicts\nJust like merging, rebasing can hit conflicts. Git pauses and asks you to resolve each one:\n```bash\n# Resolve conflicts in files, then:\ngit add resolved-file.txt\ngit rebase --continue\n\n# Or abort the rebase entirely:\ngit rebase --abort\n```\n\n## After Rebasing, Merge into Main\nNow that feature is based on the latest main, merging is a clean fast-forward:\n```bash\ngit switch main\ngit merge feature-login  # Fast-forward, no merge commit\n```\n\n## Force Pushing After Rebase\nIf you've already pushed your branch and then rebase it, you must force push:\n```bash\ngit push --force-with-lease origin feature-login\n```\n`--force-with-lease` is safer than `--force` — it fails if someone else has pushed to the branch since your last fetch."
          }
        },
        {
          "type": "text",
          "title": "Interactive Rebase — Polishing Your Commits",
          "duration": 20,
          "content": {
            "markdown": "# Interactive Rebase\n\nInteractive rebase lets you **rewrite, squash, reorder, or delete** commits before sharing them.\n\n## Starting an Interactive Rebase\nClean up the last 3 commits:\n```bash\ngit rebase -i HEAD~3\n```\n\nGit opens your editor with a list:\n```\npick a1b2c3 Add login form HTML\npick d4e5f6 Fix typo in login form\npick g7h8i9 Add login form validation\n```\n\n## Available Commands\n- `pick` — keep the commit as-is\n- `reword` — keep the commit, but edit the message\n- `edit` — pause to amend this commit\n- `squash` (or `s`) — combine this commit into the previous one\n- `fixup` (or `f`) — like squash but discard this commit's message\n- `drop` — delete this commit entirely\n\n## Example: Squash 3 commits into 1\n```\npick a1b2c3 Add login form HTML\nsquash d4e5f6 Fix typo in login form\nsquash g7h8i9 Add login form validation\n```\nGit merges them into one commit and lets you write a unified message.\n\nResult: one clean commit like `Add complete login form with validation` instead of 3 messy intermediate ones."
          }
        }
      ],
      "quizzes": [
        {
          "title": "Rebasing Quiz",
          "duration": 10,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "What does git rebase main do when run on a feature branch?",
                "options": [
                  "Merges main into the feature branch and creates a merge commit",
                  "Replays feature branch commits on top of the latest main branch",
                  "Deletes the feature branch and recreates it from main",
                  "Pushes the feature branch to the main remote"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What is the Golden Rule of rebasing?",
                "options": [
                  "Always rebase before every commit",
                  "Never rebase the main branch",
                  "Never rebase branches that other people are working on",
                  "Always use --force when pushing after a rebase"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "In an interactive rebase, what does 'squash' do?",
                "options": [
                  "Deletes the commit entirely",
                  "Combines the commit with the previous one",
                  "Edits the commit message",
                  "Pauses the rebase for manual changes"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "Why is --force-with-lease preferred over --force when pushing after a rebase?",
                "options": [
                  "It is faster",
                  "It fails safely if someone else pushed to the branch since your last fetch",
                  "It automatically resolves conflicts",
                  "It creates a backup before force pushing"
                ]
              },
              {
                "type": "short_answer",
                "question": "What command starts an interactive rebase for the last 4 commits?"
              },
              {
                "type": "voice_response",
                "question": "When would you choose to rebase instead of merge, and when would you definitely NOT use rebase?"
              }
            ]
          }
        }
      ],
      "checkpoint": [
        {
          "type": "code",
          "title": "Squash and Rebase",
          "duration": 25,
          "content": {
            "prompt": "You have a feature branch with 4 commits: 'Add header HTML', 'Fix header typo', 'Add header CSS', 'Adjust header padding'. Using interactive rebase, write the rebase command and then show what the editor configuration would look like to squash all 4 into a single clean commit called 'Add styled header component'.",
            "language": "bash",
            "starter_code": "# 1. Start interactive rebase\n\n# 2. Show the editor configuration (as a comment)\n# pick ...\n# squash ...\n# ...\n\n# 3. After completing the rebase, push the cleaned branch\n",
            "socratic_focus": "Ask the student: after squashing, will the commit hashes change? What does that mean if you've already pushed this branch?"
          }
        }
      ]
    },
    {
      "title": "Module 9: Git Stash, Tags, and Useful Tricks",
      "description": "Learn the productivity tools that experienced Git users rely on every day.",
      "objectives": [
        "Use git stash to save work-in-progress",
        "Create and use tags for releases",
        "Use git cherry-pick to apply specific commits",
        "Search history with git log and git bisect"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "git stash — Save Your Work Without Committing",
          "duration": 15,
          "content": {
            "markdown": "# git stash\n\nYou're mid-feature when an urgent bug report comes in. You can't commit unfinished work, but you also can't switch branches with uncommitted changes safely.\n\nEnter `git stash`.\n\n## Stashing Changes\n```bash\ngit stash\n# or with a descriptive name:\ngit stash push -m \"WIP: login form validation\"\n```\nThis saves your uncommitted changes to a stash stack and cleans your working directory.\n\n## Viewing Stashes\n```bash\ngit stash list\n# Output:\n# stash@{0}: WIP: login form validation\n# stash@{1}: On main: fix header colors\n```\n\n## Applying Stashes\n```bash\ngit stash pop          # Apply most recent stash and remove it from stack\ngit stash apply        # Apply most recent stash but KEEP it in the stack\ngit stash apply stash@{2}  # Apply a specific stash\n```\n\n## Dropping Stashes\n```bash\ngit stash drop stash@{0}   # Delete a specific stash\ngit stash clear            # Delete ALL stashes\n```"
          }
        },
        {
          "type": "text",
          "title": "git tag — Marking Releases",
          "duration": 10,
          "content": {
            "markdown": "# git tag — Marking Important Points\n\nTags are **fixed pointers** to a specific commit. Unlike branches, tags don't move when you make new commits. They're used to mark release versions.\n\n## Lightweight Tag\n```bash\ngit tag v1.0\n```\nSimply a named pointer. No extra metadata.\n\n## Annotated Tag (Recommended for Releases)\n```bash\ngit tag -a v1.0 -m \"Version 1.0 — first stable release\"\n```\nStores tagger name, email, date, and message.\n\n## Listing Tags\n```bash\ngit tag\ngit tag -l \"v1.*\"  # Filter with pattern\n```\n\n## Pushing Tags to Remote\nTags are NOT pushed by default:\n```bash\ngit push origin v1.0       # Push a specific tag\ngit push origin --tags     # Push all tags\n```\n\n## Checking Out a Tag\n```bash\ngit checkout v1.0\n```\nNote: This puts you in 'detached HEAD' state — you're not on a branch."
          }
        },
        {
          "type": "text",
          "title": "Cherry-pick, Bisect, and Power Log",
          "duration": 15,
          "content": {
            "markdown": "# git cherry-pick, bisect, and Power Log\n\n## git cherry-pick — Apply a Specific Commit\nApply a single commit from another branch onto your current branch:\n```bash\ngit cherry-pick abc1234\n```\nUse case: A bug fix was committed to a feature branch, but you need it on main urgently without merging the entire feature.\n\n## git bisect — Binary Search for Bugs\nYou know a bug was introduced somewhere in the last 200 commits. Bisect helps you find exactly which one:\n```bash\ngit bisect start\ngit bisect bad             # Current commit is broken\ngit bisect good v2.0       # v2.0 tag was working fine\n```\nGit checks out the middle commit. You test it:\n```bash\ngit bisect good   # or git bisect bad\n```\nGit narrows it down with each step. After ~8 steps it pinpoints the exact breaking commit.\n\n## Power git log\n```bash\n# See all commits that touched a specific file\ngit log --follow -- src/auth.js\n\n# Search commit messages\ngit log --grep=\"login\"\n\n# See changes introduced by each commit\ngit log -p\n\n# Visual branch graph\ngit log --all --oneline --graph --decorate\n```"
          }
        }
      ],
      "quizzes": [
        {
          "title": "Git Productivity Quiz",
          "duration": 10,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "What does git stash pop do?",
                "options": [
                  "Deletes all stashes",
                  "Applies the most recent stash and removes it from the stash stack",
                  "Creates a new stash from the current working directory",
                  "Applies the oldest stash"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What is the difference between a lightweight tag and an annotated tag?",
                "options": [
                  "Lightweight tags are faster to create; annotated tags store metadata like author and message",
                  "Annotated tags cannot be pushed to remotes",
                  "Lightweight tags are only for branches, not commits",
                  "There is no functional difference"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What does git cherry-pick abc1234 do?",
                "options": [
                  "Reverts the commit abc1234",
                  "Creates a branch at commit abc1234",
                  "Applies the changes from commit abc1234 to the current branch",
                  "Moves HEAD to commit abc1234"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What is git bisect used for?",
                "options": [
                  "Splitting a repository into two separate repos",
                  "Binary searching through commits to find which one introduced a bug",
                  "Dividing a large commit into smaller ones",
                  "Comparing two branches side by side"
                ]
              },
              {
                "type": "short_answer",
                "question": "You have three stashes. Write the command to apply the second-oldest stash (index 1) without removing it from the stack."
              },
              {
                "type": "voice_response",
                "question": "Describe a real-world scenario where you'd use git stash, and walk through the complete workflow."
              }
            ]
          }
        }
      ],
      "checkpoint": []
    },
    {
      "title": "Module 10: Git Workflows for Teams",
      "description": "Real teams follow structured workflows. Learn the industry-standard approaches used in professional software development.",
      "objectives": [
        "Understand Git Flow",
        "Understand GitHub Flow",
        "Know how to structure a professional PR workflow",
        "Understand trunk-based development"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "Git Flow",
          "duration": 15,
          "content": {
            "markdown": "# Git Flow\n\nGit Flow is a branching model created by Vincent Driessen. It's suited for projects with scheduled releases.\n\n## Core Branches\n- `main` — production-ready code only\n- `develop` — integration branch; all features merge here\n\n## Supporting Branches\n- `feature/*` — new features, branch off `develop`\n- `release/*` — preparing a release, branch off `develop`\n- `hotfix/*` — urgent production fixes, branch off `main`\n\n## Workflow\n```\n1. feature/login branches off develop\n2. Feature is developed and merged back into develop\n3. When ready to release, release/1.2 branches off develop\n4. QA testing happens on release branch\n5. release/1.2 merges into both main AND develop\n6. main is tagged as v1.2\n```\n\n## When to Use Git Flow\n- Projects with regular versioned releases (e.g., quarterly)\n- Larger teams with dedicated QA stages\n- Libraries and packages that support multiple versions simultaneously\n\n**Not ideal for**: Continuous deployment / SaaS products that ship multiple times per day."
          }
        },
        {
          "type": "text",
          "title": "GitHub Flow and Trunk-Based Development",
          "duration": 15,
          "content": {
            "markdown": "# GitHub Flow & Trunk-Based Development\n\n## GitHub Flow\nSimpler than Git Flow. Ideal for continuous deployment.\n\n**Rules**:\n1. Anything in `main` is deployable\n2. Create descriptive feature branches off main\n3. Push to the remote branch frequently\n4. Open a Pull Request to start discussion\n5. Merge only after review and CI passes\n6. Deploy immediately after merging to main\n\n```\nmain → feature/add-dark-mode → PR → review → merge → deploy\n```\n\n**Used by**: GitHub itself, most SaaS startups\n\n## Trunk-Based Development\nEveryone commits to `main` (the trunk) frequently — at least once a day.\n\n- Short-lived feature branches (1-2 days max)\n- Heavy use of feature flags to hide incomplete features in production\n- Requires strong automated testing (CI/CD)\n\n**Used by**: Google, Facebook, large high-velocity teams\n\n**The core idea**: Small changes merged often → fewer conflicts, faster feedback, lower risk per deployment.\n\n## Choosing a Workflow\n| Workflow | Best For |\n|---|---|\n| Git Flow | Versioned releases, larger teams |\n| GitHub Flow | SaaS, continuous deployment |\n| Trunk-Based | High velocity, strong CI/CD |\n"
          }
        },
        {
          "type": "text",
          "title": "Code Review & PR Best Practices",
          "duration": 10,
          "content": {
            "markdown": "# Code Review & PR Best Practices\n\n## Writing a Good PR\nA good Pull Request:\n- Has a clear title: what does it do?\n- Includes a description: why is this change needed?\n- References the related issue: `Closes #42`\n- Is small and focused — one feature/fix per PR\n- Passes all CI checks before requesting review\n\n## Reviewing Code Effectively\n- Be kind and constructive — review the code, not the person\n- Ask questions rather than demanding changes: 'What do you think about...?'\n- Distinguish between blocking issues and suggestions\n- Approve when it's good enough, not when it's perfect\n\n## PR Checklist\n```\n✅ Does the code do what the title says?\n✅ Are there tests for the new behavior?\n✅ Does it follow the project's style/conventions?\n✅ Is there anything that could break existing functionality?\n✅ Is the PR a reasonable size to review?\n```\n\n## Keeping PRs Small\nThe smaller a PR, the faster the review, the fewer conflicts, and the easier the rollback if something goes wrong. Aim for PRs that can be reviewed in under 30 minutes."
          }
        }
      ],
      "quizzes": [
        {
          "title": "Git Workflows Quiz",
          "duration": 10,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "In Git Flow, where do feature branches branch off from?",
                "options": [
                  "main",
                  "develop",
                  "release",
                  "hotfix"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What is the core rule of GitHub Flow?",
                "options": [
                  "Never commit directly to any branch",
                  "Anything in main must always be deployable",
                  "All features go through a develop branch before main",
                  "Tags must be created for every commit"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What is a feature flag in trunk-based development?",
                "options": [
                  "A Git tag marking a feature release",
                  "A branch naming convention",
                  "A code mechanism to enable or disable incomplete features in production",
                  "A CI/CD pipeline configuration"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "Which workflow is best suited for a team doing continuous deployment multiple times per day?",
                "options": [
                  "Git Flow",
                  "Waterfall branching",
                  "GitHub Flow or Trunk-Based Development",
                  "SVN-style centralized workflow"
                ]
              },
              {
                "type": "short_answer",
                "question": "Name two things a good Pull Request description should include."
              },
              {
                "type": "voice_response",
                "question": "Your team is building a SaaS product that deploys to production multiple times a day. Which Git workflow would you recommend and why?"
              }
            ]
          }
        }
      ],
      "checkpoint": []
    },
    {
      "title": "Module 11: Git Hooks and Automation",
      "description": "Git hooks let you automate actions at key points in the Git workflow — linting, testing, formatting, and more.",
      "objectives": [
        "Understand what Git hooks are",
        "Write a pre-commit hook to run linting",
        "Use commit-msg hook to enforce message format",
        "Understand client-side vs server-side hooks"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "What are Git Hooks?",
          "duration": 10,
          "content": {
            "markdown": "# Git Hooks\n\nGit hooks are **scripts that Git executes automatically** before or after certain events like committing, merging, and pushing.\n\nThey live in the `.git/hooks/` directory of your repository.\n\n## Types of Hooks\n\n### Client-Side Hooks (run on your machine)\n- `pre-commit` — runs before a commit is created; can abort the commit by exiting with non-zero\n- `prepare-commit-msg` — modify the default commit message\n- `commit-msg` — validate the commit message format\n- `post-commit` — runs after a commit; good for notifications\n- `pre-push` — runs before pushing; good for running tests\n\n### Server-Side Hooks (run on the remote)\n- `pre-receive` — can reject pushes\n- `post-receive` — trigger deployments, notifications\n\n## Enabling a Hook\nHook files in `.git/hooks/` must be:\n1. Named exactly (e.g., `pre-commit` — no extension)\n2. Executable: `chmod +x .git/hooks/pre-commit`\n\n**Note**: `.git/` is not tracked by Git, so hooks aren't shared via `git clone`. Use tools like Husky (Node.js) to share hooks through the repository."
          }
        },
        {
          "type": "text",
          "title": "Writing Hooks: pre-commit and commit-msg",
          "duration": 20,
          "content": {
            "markdown": "# Writing Git Hooks\n\n## pre-commit: Run Linting Before Committing\nCreate `.git/hooks/pre-commit`:\n```bash\n#!/bin/bash\necho \"Running linter...\"\nnpx eslint . --ext .js\nif [ $? -ne 0 ]; then\n  echo \"Linting failed! Fix errors before committing.\"\n  exit 1\nfi\necho \"Linting passed.\"\n```\nMake it executable:\n```bash\nchmod +x .git/hooks/pre-commit\n```\nNow every `git commit` runs ESLint first. If linting fails, the commit is aborted.\n\n## commit-msg: Enforce Commit Message Format\nCreate `.git/hooks/commit-msg`:\n```bash\n#!/bin/bash\nMSG=$(cat \"$1\")\nPATTERN=\"^(feat|fix|docs|style|refactor|test|chore): .{10,}\"\n\nif ! echo \"$MSG\" | grep -qE \"$PATTERN\"; then\n  echo \"ERROR: Commit message must follow Conventional Commits format:\"\n  echo \"  feat: add user login\"\n  echo \"  fix: resolve null pointer on logout\"\n  exit 1\nfi\n```\nThis enforces Conventional Commits style messages.\n\n## Husky — Shareable Hooks for Node.js Projects\n```bash\nnpm install --save-dev husky\nnpx husky init\n```\nHusky stores hooks in `.husky/` which IS tracked by Git, making hooks shared across the team."
          }
        }
      ],
      "quizzes": [
        {
          "title": "Git Hooks Quiz",
          "duration": 5,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "Where do Git hooks live?",
                "options": [
                  "In a hooks/ folder at the root of the project",
                  "In the .git/hooks/ directory",
                  "In the .gitignore file",
                  "On the remote server only"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "How does a pre-commit hook abort a commit?",
                "options": [
                  "By printing an error message",
                  "By calling git commit --abort",
                  "By exiting with a non-zero exit code",
                  "By deleting the staged files"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "Why are hooks in .git/hooks/ not shared when teammates clone the repository?",
                "options": [
                  "Because hooks require admin permissions",
                  "Because .git/ is not tracked by Git",
                  "Because hooks only work on the original machine",
                  "Because cloning skips binary files"
                ]
              },
              {
                "type": "short_answer",
                "question": "What tool is commonly used in Node.js projects to share Git hooks across a team?"
              },
              {
                "type": "voice_response",
                "question": "Describe two things you would automate with Git hooks in a professional project and why."
              }
            ]
          }
        }
      ],
      "checkpoint": [
        {
          "type": "code",
          "title": "Write a pre-commit Hook",
          "duration": 20,
          "content": {
            "prompt": "Write a bash pre-commit hook script that: (1) checks if any staged .js files contain the word 'console.log', (2) if any are found, prints a warning listing the files and exits with code 1 to abort the commit, (3) if none are found, prints 'All clear!' and allows the commit to proceed.",
            "language": "bash",
            "starter_code": "#!/bin/bash\n# pre-commit hook: reject commits with console.log in JS files\n\n",
            "socratic_focus": "Ask the student: what if a developer genuinely needs a console.log in production? How might you make this check bypassable?"
          }
        }
      ]
    },
    {
      "title": "Module 12: .gitignore, Submodules, and Advanced Config",
      "description": "Master the configuration and management tools that keep your repository clean and maintainable.",
      "objectives": [
        "Write effective .gitignore files",
        "Understand and use Git submodules",
        "Configure useful Git aliases",
        "Use git reflog for disaster recovery"
      ],
      "lessons": [
        {
          "type": "text",
          "title": "Mastering .gitignore",
          "duration": 15,
          "content": {
            "markdown": "# Mastering .gitignore\n\nThe `.gitignore` file tells Git which files and directories to ignore — i.e., never track.\n\n## Why It Matters\nYou should never commit:\n- `node_modules/` — huge, regenerated from package.json\n- `.env` — contains secrets and API keys\n- Build outputs — `dist/`, `build/`, `.cache/`\n- IDE configs — `.vscode/`, `.idea/`\n- OS files — `.DS_Store` (macOS), `Thumbs.db` (Windows)\n\n## .gitignore Syntax\n```\n# Ignore a specific file\n.env\n\n# Ignore a directory\nnode_modules/\n\n# Ignore all .log files\n*.log\n\n# Ignore all .txt files in any 'temp' directory\ntemp/**/*.txt\n\n# Negate a rule (include even if a parent rule excludes it)\n!important.log\n```\n\n## Global .gitignore\nSet a global ignore file for machine-wide patterns:\n```bash\ngit config --global core.excludesFile ~/.gitignore_global\n```\n\n## gitignore.io\nVisit [gitignore.io](https://gitignore.io) or use:\n```bash\ncurl -sL https://www.toptal.com/developers/gitignore/api/node,macos,vscode\n```\nto generate a .gitignore for your specific stack."
          }
        },
        {
          "type": "text",
          "title": "Git Aliases and Reflog",
          "duration": 15,
          "content": {
            "markdown": "# Git Aliases and Reflog\n\n## Git Aliases — Shortcuts for Common Commands\nAdd aliases to your global config:\n```bash\ngit config --global alias.co checkout\ngit config --global alias.br branch\ngit config --global alias.st status\ngit config --global alias.lg \"log --oneline --graph --all --decorate\"\n```\n\nNow instead of `git checkout`, you type `git co`. Instead of the long log command, just `git lg`.\n\nYou can also put shell commands in aliases:\n```bash\ngit config --global alias.undo \"reset --soft HEAD~1\"\n```\nNow `git undo` undoes the last commit (softly).\n\n## git reflog — Your Safety Net\nReflog records where HEAD has been — even commits that no longer appear in `git log`.\n\n```bash\ngit reflog\n# Output:\n# abc1234 HEAD@{0}: commit: Add login feature\n# def5678 HEAD@{1}: reset: moving to HEAD~1\n# ghi9012 HEAD@{2}: commit: Add registration form\n```\n\nIf you accidentally `git reset --hard` and lose commits, reflog can find them:\n```bash\ngit reflog               # Find the lost commit hash\ngit checkout abc1234     # Or restore it\ngit reset --hard abc1234 # Or reset back to it\n```\n\n**Reflog is local only** — it's not pushed to remotes. Commits in reflog expire after 90 days by default."
          }
        }
      ],
      "quizzes": [
        {
          "title": "Config & Cleanup Quiz",
          "duration": 5,
          "content": {
            "questions": [
              {
                "type": "multiple_choice",
                "question": "Which of these should you always add to .gitignore?",
                "options": [
                  "README.md",
                  "src/index.js",
                  ".env",
                  "package.json"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "What does git reflog track?",
                "options": [
                  "All pushes made to the remote",
                  "Every position HEAD has been at, including reset and checkout operations",
                  "Only the last 10 commits",
                  "Branch creation and deletion events only"
                ]
              },
              {
                "type": "multiple_choice",
                "question": "How do you create a Git alias named 'st' for 'git status'?",
                "options": [
                  "git alias st = status",
                  "git config alias.st status",
                  "git config --global alias.st status",
                  "git shortcut --add st status"
                ]
              },
              {
                "type": "short_answer",
                "question": "You accidentally hard-reset and lost 3 commits. What command would you run first to try to recover them?"
              },
              {
                "type": "voice_response",
                "question": "Why is it important to add .env files to .gitignore? What could go wrong if you committed a .env file?"
              }
            ]
          }
        }
      ],
      "checkpoint": [
        {
          "type": "code",
          "title": "Write a .gitignore for a Node.js project",
          "duration": 15,
          "content": {
            "prompt": "Write a comprehensive .gitignore file for a Node.js web application project. It should ignore: node_modules, environment files, build outputs (dist/, build/), log files, macOS system files (.DS_Store), VS Code settings, and any files ending in .local. Add a comment section header for each category.",
            "language": "bash",
            "starter_code": "# .gitignore for Node.js Web Application\n\n",
            "socratic_focus": "Ask the student: what would happen to a file that's already been committed if you add it to .gitignore later? How would you fix that?"
          }
        }
      ]
    }
  ],
  "final_project": {
    "id": "final-git-team-sim",
    "title": "The Team Collaboration Simulation",
    "description": "Simulate a complete professional Git workflow from scratch. You will: (1) Create a new repository and connect it to a remote on GitHub. (2) Implement a Git Flow branching strategy with main and develop branches. (3) Build a simple multi-page HTML website across three separate feature branches, each with multiple commits. (4) Open Pull Requests for each feature branch, write a PR description, and simulate a code review by addressing a requested change. (5) Resolve at least one intentional merge conflict. (6) Tag the final merged result as v1.0 with an annotated tag. (7) Write a pre-commit hook that rejects commits with TODO comments left in the code. (8) Document the entire workflow in a WORKFLOW.md file that your teammates could follow to replicate the process. This project tests every major concept from the course in a realistic, end-to-end scenario."
  }
}
```