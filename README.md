# ⚙️ GitHub Actions Demo – `action-repo`

This repository demonstrates how GitHub Actions can be used to automate tasks when a **Pull Request (PR)** is created, updated, or reopened.

---

## 📦 Project Structure

action-repo/
├── .github/
│ └── workflows/
│ └── pr-check.yml # GitHub Actions workflow file
├── sample.js # Sample file for testing
└── README.md # Project documentation

yaml
Copy
Edit

---

## 🚀 Features

- Automatically triggers a workflow when a **PR is opened, updated, or reopened**
- Logs PR title, author, and branch in GitHub Actions logs
- Simple example to showcase GitHub CI/CD basics

---

## 🔧 Workflow File

> `.github/workflows/pr-check.yml`

```yaml
name: PR Checker

on:
  pull_request:
    types: [opened, synchronize, reopened]

jobs:
  check-pr:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Run basic check
        run: echo "✅ Pull Request received! Running checks..."

      - name: Show PR metadata
        run: |
          echo "Title: ${{ github.event.pull_request.title }}"
          echo "Author: ${{ github.actor }}"
          echo "Branch: ${{ github.head_ref }}"
✅ How It Works
A pull request is created, updated, or reopened

GitHub triggers the workflow defined in pr-check.yml

The workflow:

Checks out the code

Logs a message

Prints metadata about the PR

📂 Sample Output
In the GitHub Actions logs, you'll see something like:

vbnet
Copy
Edit
✅ Pull Request received! Running checks...
Title: Fix UI bug on login page
Author: harichopper
Branch: fix-login-ui
📚 How to Test It
Fork or clone this repo

Push a new branch and create a pull request

Go to the Actions tab and see your workflow run

View logs to check PR metadata

🧠 Why Use GitHub Actions?
GitHub Actions helps you:

Automate testing and deployments

Enforce code quality checks

Reduce manual workflows during collaboration

📅 Created On
July 9, 2025
by @harichopper

yaml
Copy
Edit

---

Would you like me to generate and upload this `README.md` file directly to your `action-repo` project folder, or give you the Git commands to commit and push it now?
