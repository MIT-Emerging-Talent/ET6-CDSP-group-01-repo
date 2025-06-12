# Contributing to our project

Welcome to our collaborative data science project! This guide will help you
contribute effectively to our repository
while maintaining consistency.

## Getting Started

### Core Tools

This project uses:

- Python 3.8+
- Jupyter Notebook (interactive development environment)
- VS Code (code editor)
- Git (for version control)

### Repository Setup

- Each **milestone** has it's own folder add your work to it's relative milestone
 folder.
- The **notes/meeting_minutes/** folder contains our team's meeting minutes.
- Add any helpful info or suggestions to the `notes/` folder
- **Don't** make changes directly to the main branch. All changes
should be made using *pull requests* from branches.
- Create a branch for each task:

  ```bash
  git checkout -b task-name
  ```

## Workflow

### 1. Pull the latest changes from `main`

```bash
git checkout main
git pull origin main
```

### 2. Create a new branch

```bash
git checkout -b branch-name
```

### 3. Make your changes and commit

```bash
git add .
git commit -m "short message"
```

### 4. Push your branch

```bash
git push origin branch-name
```

### 5. Wait for review from a team member

- Your commit should pass all *CI checks* and don't have any conflicts with the
 main branch
- Use descriptive, short commit messages

## Code Quality

- Follow the **PEP8** style guide
- Code must pass both **ruff** and **pylint**
- Use **clear, descriptive variable names**
- Create **functions** for reusable logic
- Add **comments** where helpful, especially for non-obvious logic.
- Include **docstrings** for all functions and classes to explain what they do.
  
**Thank you for collaboration in our project and don't hesitate to contact to any
 team member for help or asking questions.** 🤝
