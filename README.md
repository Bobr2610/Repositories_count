[![Repositories](https://raw.githubusercontent.com/Bobr2610/Repositories_count/main/counter.png?v=0)](https://github.com/Bobr2610/Repositories_count)

# Repository Counter

Displays the number of public repositories owned by a GitHub user or organization.

---

## How to use

### 1. Fork and setup on GitHub

1. Create a **new repository** on GitHub (or use an existing one).
2. Push the contents of this folder to the repository (to the `main` branch).
3. In **README.md**, replace `OWNER` and `REPO` with your username and repository name in the badge link (at the top of the file).  
   Example: if your repo is `https://github.com/YourName/my-project`, the line should be:
   ```markdown
   [![Repositories](https://raw.githubusercontent.com/YourName/my-project/main/counter.png?v=0)](https://github.com/YourName/my-project)
   ```

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

### 5. Run

- **Scheduled:** the workflow runs every hour and on push (except when only `counter.png`, `theme/`, or `README.md` are changed).
- **Manual:** **Actions** → **Update Repository Counter** → **Run workflow**.

After the first successful run, the README will be updated with the correct image link including `?v=...` — you don't need to change it manually.

---

Based on [Views_Counter_with_custom_images](https://github.com/Bobr2610/Views_Counter_with_custom_images).
