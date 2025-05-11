

```markdown
# 🔐 GitHooksProj

GitHooksProj is a practical DevOps project for managing and automating Git workflows using custom Git hooks. The project includes implementations of common hooks such as `pre-commit`, `prepare-commit-msg`, `pre-push`, and `post-merge`. These hooks enforce coding standards, improve collaboration, and prevent common Git issues across your development team.

---

## 📦 Features

- **Pre-commit Hook**: Blocks commits if files fail formatting or basic checks.
- **Prepare-commit-msg Hook**: Automatically adds branch names or ticket IDs to commit messages.
- **Pre-push Hook**: Prevents pushes if tests fail or linting errors are found.
- **Post-merge Hook**: Displays a notification or message after a successful merge.
- **Shell Scripts**: Simple and modular Bash scripts to support each hook logic.

---

## 📁 Directory Structure

```

GitHooksProj/
│
├── hooks/                  # Custom Git hooks
│   ├── pre-commit
│   ├── prepare-commit-msg
│   ├── pre-push
│   └── post-merge
│
├── scripts/                # Supporting Bash scripts
│   ├── check\_format.sh
│   ├── generate\_commit\_msg.sh
│   └── post\_merge\_notice.sh
│
├── .gitignore
└── README.md

````

---

## ⚙️ Installation & Setup

1. **Clone the repository**:

   ```bash
   git clone https://github.com/Fadi7AY/GitHooksProj.git
   cd GitHooksProj
````

2. **Install the hooks**:

   Copy the custom hooks into your local Git repository’s `.git/hooks` directory:

   ```bash
   cp hooks/* .git/hooks/
   chmod +x .git/hooks/*
   ```

3. **Make the scripts executable**:

   ```bash
   chmod +x scripts/*.sh
   ```

4. **Test the setup**:

   Try making a commit or push to observe the hooks in action.

---

## 🔍 Hook Details

### ✅ `pre-commit`

Runs before a commit is finalized. Common tasks:

* Formatting check (via `check_format.sh`)
* Rejects commit if issues are found

### 📝 `prepare-commit-msg`

Appends branch name or task ID to the beginning of a commit message.

* Example: `feat/login Add authentication logic`

### 🚫 `pre-push`

Blocks `git push` if:

* Code doesn't pass tests or linting
* Branch policy violations exist

### 📬 `post-merge`

After a merge, runs a message script to:

* Notify the user
* Display changes or tips

---

## 🧪 Example Workflow

```bash
# Make changes to the code
nano main.py

# Add and commit
git add main.py
git commit -m "Fix bug in logic"  # Hooks will run here

# Push changes
git push origin main  # Hooks will run here too
```

---

## 🧰 Requirements

* Git 2.x or later
* Bash shell
* Optional tools: formatters like `black`, `eslint`, or testing frameworks (if used in your scripts)

---

## 🤝 Contributing

Pull requests are welcome! If you’d like to add a new hook or improve an existing one:

1. Fork the repository
2. Create a new branch
3. Make your changes
4. Submit a pull request

---



