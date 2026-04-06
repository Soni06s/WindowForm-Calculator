# 📤 How to Upload This Project to GitHub

Follow these steps to push the Windows Form Calculator project to your own GitHub repository.

---

## Step 1 — Create a GitHub Repository

1. Go to https://github.com and sign in (or create a free account).
2. Click the **`+`** button (top-right) → **New repository**.
3. Fill in:
   - **Repository name:** `WindowsFormCalculator`
   - **Description:** `A modern Windows Forms Calculator built with C# (.NET 4.8)`
   - **Visibility:** Public ✅ (or Private)
   - **Do NOT** initialise with README / .gitignore / licence (we already have them).
4. Click **Create repository**.
5. Copy the repository URL shown, e.g.:
   ```
   https://github.com/<your-username>/WindowsFormCalculator.git
   ```

---

## Step 2 — Install Git (if not already installed)

Download from https://git-scm.com/download/win and install with default options.

Verify:
```bash
git --version
```

---

## Step 3 — Initialise & Push

Open **Command Prompt** or **Git Bash** inside the `WindowsFormCalculator` folder:

```bash
# Navigate to the project folder
cd path\to\WindowsFormCalculator

# Initialise a new Git repository
git init

# Stage ALL files
git add .

# Create the first commit
git commit -m "Initial commit: Windows Form Calculator"

# Rename branch to 'main' (GitHub default)
git branch -M main

# Link to your GitHub repository  (replace <your-username>)
git remote add origin https://github.com/<your-username>/WindowsFormCalculator.git

# Push to GitHub
git push -u origin main
```

---

## Step 4 — Verify on GitHub

1. Open your browser and go to:
   ```
   https://github.com/<your-username>/WindowsFormCalculator
   ```
2. You should see all files, including the `README.md` rendered on the homepage.

---

## Step 5 — GitHub Actions (Automatic Build)

The `.github/workflows/build.yml` file is already included.  
Every time you push to `main`, GitHub will automatically:
- Restore packages
- Build the project in Release mode
- Upload `WindowsFormCalculator.exe` as a downloadable artifact

Check the build status under the **Actions** tab of your repository.

---

## Useful Git Commands for Future Updates

```bash
# Check what changed
git status

# Stage all changes
git add .

# Commit with a message
git commit -m "Your message here"

# Push to GitHub
git push
```

---

## Troubleshooting

| Problem | Fix |
|---|---|
| `git` not recognised | Re-install Git and restart CMD |
| Authentication failed | Use a **Personal Access Token** instead of password — create at https://github.com/settings/tokens |
| Push rejected | Run `git pull origin main --rebase` first, then push again |
