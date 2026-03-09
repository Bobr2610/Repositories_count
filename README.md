[![Repositories](https://raw.githubusercontent.com/Bobr2610/Repositories_count/main/counter.png?v=1773095836)](https://github.com/Bobr2610/Repositories_count)

# Repository Counter

Displays the number of public repositories owned by a GitHub user or organization.

---

## How to use

### 1. Copy files to your repository

Clone or download and add to your repository:

| File/folder                          | Description                             |
| ------------------------------------ | --------------------------------------- |
| .github/workflows/update-counter.yml | GitHub Actions workflow                 |
| theme/                               | Digit images 0.png–9.png (beaver theme) |
| counter.json                         | {"count": 0} — fallback when API fails  |

### 2. Personal Access Token

1. [GitHub → Settings → Developer settings → Personal access tokens](https://github.com/settings/tokens)
2. Create a token with **`read:user`** scope (or `repo` for full access)
3. Copy the token (it is shown only once)

### 3. Repository secret

1. Your repo → **Settings** → **Secrets and variables** → **Actions**
2. **New repository secret**
3. Name: `TRAFFIC_TOKEN`
4. Value: paste the token from step 2

### 4. Theme folder

The repository must contain a **`theme/`** folder with files `0.png` … `9.png` (digits for the counter).  
You can get them from the original repository:

- [Views_Counter_with_custom_images — theme](https://github.com/Bobr2610/Views_Counter_with_custom_images/tree/main/theme)  
  Download the `theme` folder and place it in the root of your repo.

### 5. Add the badge to README

Insert this line into your README (or keep the one that comes with the repo):

```markdown
[![Repositories](https://raw.githubusercontent.com/Bobr2610/Repositories_count/main/counter.png?v=1773095836)](https://github.com/Bobr2610/Repositories_count)
```

**Autonomous:** On the first run, the workflow automatically replaces `OWNER/REPO` and the branch with your repository — no manual editing needed. It also updates `?v=` to a timestamp on each run to avoid cache.

### 6. Running

- **Automatically:** the workflow runs every hour and on push (except for changes to `counter.png`, `theme/`, `README.md`)
- **Manually:** **Actions** → **Update Repository Counter** → **Run workflow**

---

## Configuration

1. Add the **`TRAFFIC_TOKEN`** secret — Personal Access Token with `read:user` or `repo` permission
2. The workflow is **fully autonomous**: it detects the current repository and branch, updates the badge URL automatically (works when forked), and refreshes `counter.png` every hour and on push

---

Based on [Views_Counter_with_custom_images](https://github.com/Bobr2610/Views_Counter_with_custom_images).
