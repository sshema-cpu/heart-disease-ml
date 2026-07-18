# 🚀 How to Publish Your Project to GitHub — Step by Step

Two paths below. **Path A (website upload)** needs zero command line and takes ~10 minutes. **Path B (git commands)** is the "real developer" way — worth doing since Git is on your resume.

---

## Path A: Upload Through the GitHub Website (easiest)

### Step 1 — Create the repository
1. Go to [github.com](https://github.com) and sign in (or create an account — use a professional username, ideally `samshema` or similar, since it appears in all your URLs).
2. Click the **+** in the top right → **New repository**.
3. Repository name: `heart-disease-ml`
4. Description: `Comparing Logistic Regression, Decision Trees & Neural Networks on 1,025 patient records — ML final project`
5. Set to **Public** (recruiters must be able to see it).
6. Do **NOT** check "Add a README" (you already have one).
7. Click **Create repository**.

### Step 2 — Upload the files
1. Unzip `heart-disease-ml.zip` (the file I gave you) on your computer.
2. On your new empty repo page, click **"uploading an existing file"**.
3. Drag the **entire contents** of the unzipped folder in (README.md, requirements.txt, LICENSE, .gitignore, and the data/, notebooks/, report/, docs/ folders).
   - GitHub's web uploader preserves folders if you drag the folders themselves in.
4. Commit message: `Initial commit — heart disease ML project`
5. Click **Commit changes**.

### Step 3 — Add your portfolio page (this fixes your resume link!)
1. On your Mac, find `SamShemaPortfolio.html` on your Desktop.
2. **Rename it to exactly:** `index.html`
3. In your GitHub repo, click into the `docs/` folder → **Add file → Upload files** → drag `index.html` in → Commit.
4. Delete the placeholder: click `README_PLACEHOLDER.txt` → trash icon → Commit.

### Step 4 — Turn on GitHub Pages
1. In the repo, go to **Settings → Pages** (left sidebar).
2. Under "Build and deployment": Source = **Deploy from a branch**.
3. Branch = **main**, Folder = **/docs** → **Save**.
4. Wait 1–2 minutes, refresh — GitHub shows your live URL:
   `https://YOUR-USERNAME.github.io/heart-disease-ml/`
5. **Test it in an incognito window.** That URL is what goes on your resume as "Portfolio."

### Step 5 — Final polish (5 minutes, big payoff)
1. Open README.md in the repo → pencil icon → replace every `YOUR-USERNAME` with your real GitHub username and fix the LinkedIn link → Commit.
2. Repo home page → gear icon next to "About" (right side):
   - Description: `ML comparison: can simple models beat neural networks at predicting heart disease?`
   - Website: paste your GitHub Pages URL
   - Topics: `machine-learning`, `scikit-learn`, `healthcare`, `python`, `data-science`, `classification`
3. Profile → **Pin** this repository so it's the first thing visitors see.

---

## Path B: Command Line (the developer way)

```bash
# One-time setup (if you haven't)
git config --global user.name "Sam Shema"
git config --global user.email "s.shema@tcu.edu"

# From inside the unzipped heart-disease-ml folder:
cd heart-disease-ml
git init
git add .
git commit -m "Initial commit — heart disease ML project"

# Create the repo on github.com first (Step 1 above), then:
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/heart-disease-ml.git
git push -u origin main
```

Then do Steps 3–5 from Path A (add index.html, enable Pages, polish).

---

## ✅ After Publishing: Update Your Resume

Replace the broken `file:///Users/samshema/Desktop/...` link with:

- **Portfolio:** `https://YOUR-USERNAME.github.io/heart-disease-ml/`
- **GitHub:** `https://github.com/YOUR-USERNAME` (add this to your resume header too)

And on the Heart Disease project line of your resume, the "Portfolio link" placeholder can now point to the live page or straight to the repo.

---

## 🎯 Optional Next Level (when you have an hour)

- **Make it your profile README:** create a repo named exactly `YOUR-USERNAME` with a README.md — it displays on your GitHub profile page. Great place for a short bio + pinned projects.
- **A personal site for everything:** create a repo named `YOUR-USERNAME.github.io` — whatever index.html you put there becomes `https://YOUR-USERNAME.github.io`, a cleaner root URL for your whole portfolio (heart disease project + the Grammy, YouTube, and A/B testing work).
- **Add your other projects as repos** — even Excel projects can live on GitHub with a good README and screenshots. Six pinned repos with clear READMEs reads as a serious portfolio.
