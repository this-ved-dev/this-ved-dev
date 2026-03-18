# Complete Setup Guide for this-ved-dev

Follow these steps in order to get your GitHub profile README working.

---

## Step 1: Create Your Profile Repository

1. Go to [github.com/new](https://github.com/new)
2. Set **Repository name** to exactly: `this-ved-dev` (must match your username)
3. Set visibility to **Public**
4. **Do NOT** add a README, .gitignore, or license (we'll push existing code)
5. Click **Create repository**

---

## Step 2: Push Your Code

If you're working from the Andrew6rant folder on your computer:

```bash
cd "C:\Users\Vedant Misra\Desktop\MY FILES\PROGRAMMING\Andrew6rant"

# Add your new repo as remote (replace with your actual repo URL if different)
git remote add origin https://github.com/this-ved-dev/this-ved-dev.git

# Or if origin already exists, change it:
# git remote set-url origin https://github.com/this-ved-dev/this-ved-dev.git

# Push everything
git branch -M main
git push -u origin main
```

If you're starting fresh, you can also:
- **Fork** the Andrew6rant repo, then rename the fork to `this-ved-dev`
- Or **upload** the files manually via the GitHub website

---

## Step 3: Create a Personal Access Token (for ACCESS_TOKEN secret)

1. Go to [GitHub → Settings → Developer settings → Personal access tokens](https://github.com/settings/tokens)
2. Click **"Fine-grained tokens"** (not Classic)
3. Click **"Generate new token"**
4. Fill in:
   - **Token name:** `profile-readme-stats` (or any name)
   - **Expiration:** 90 days or No expiration
   - **Repository access:** "Only select repositories" → choose `this-ved-dev`
5. Under **Permissions**, set:
   - **Account permissions:** `read:Followers`, `read:Starring`, `read:Watching`
   - **Repository permissions:** `read:Contents`, `read:Metadata`
6. Click **"Generate token"**
7. **Copy the token** (you won't see it again!)

---

## Step 4: Add Secrets to Your Repository

1. Go to your repo: `https://github.com/this-ved-dev/this-ved-dev`
2. Click **Settings** (top menu)
3. In the left sidebar, click **Secrets and variables → Actions**
4. Click **"New repository secret"**
5. Add these two secrets:

| Name | Value |
|------|-------|
| `ACCESS_TOKEN` | Paste the token you created in Step 3 |
| `USER_NAME` | `this-ved-dev` |

---

## Step 5: Set Your Birthday (for "Uptime" age)

1. Open `today.py` in your repo
2. Find this line near the top:
   ```python
   BIRTHDAY = datetime.datetime(2000, 1, 1)  # year, month, day
   ```
3. Change it to your birth date, e.g.:
   ```python
   BIRTHDAY = datetime.datetime(2005, 3, 15)  # March 15, 2005
   ```
4. Commit and push the change

---

## Step 6: Run the Workflow

1. Go to **Actions** tab in your repo
2. Click **"README build"** in the left sidebar
3. Click **"Run workflow"** (dropdown) → **"Run workflow"** (button)
4. Wait for the green checkmark (~1–2 minutes)

The workflow will:
- Fetch your GitHub stats (repos, stars, commits, followers, lines of code)
- Update the SVG files
- Push the changes back to your repo

---

## Step 7: View Your Profile

Go to: **https://github.com/this-ved-dev**

Your profile README should now show your ASCII art and stats. It updates:
- Every time you push to `main`
- Automatically every day at 4:00 AM UTC

---

## Customize Your Info (Optional)

Edit `light_mode.svg` and `dark_mode.svg` to change:
- **vedant@misra** → `this-ved-dev@github` or similar
- **OS, Host, Kernel** → Your OS, company/school, role
- **IDE** → VSCode, Cursor, etc.
- **Languages** → Your programming languages
- **Hobbies** → Your interests
- **Email, LinkedIn, Twitter** → Your contact info

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| Workflow fails with "403" or "Unauthorized" | Check that `ACCESS_TOKEN` has the correct permissions |
| "USER_NAME not found" | Add the `USER_NAME` secret with value `this-ved-dev` |
| Profile shows old/wrong data | Run the workflow manually from the Actions tab |
| Nothing shows on profile | Make sure the repo is named exactly `this-ved-dev` |
