# MPhil Proposal – Availability Scheduling Form

A personalised availability survey for **Tak Kwan Quentin Lam's** MPhil proposal meeting.  
The form is a static single-page app hosted on **GitHub Pages** and styled to look like Google Forms.

---

## Project structure

```
mphil-scheduling/
├── index.html   ← The full form (HTML + CSS + JS, self-contained)
├── .nojekyll    ← Tells GitHub Pages not to run Jekyll
└── README.md    ← This file
```

---

## Step 1 — Set up a Formspree account (free)

Formspree receives the form submissions and forwards them to your e-mail.

1. Go to **<https://formspree.io>** and create a free account (up to 50 submissions/month — more than enough here).
2. Click **"New Form"**, give it a name (e.g. *MPhil Proposal Availability*), and enter the e-mail address where you want to receive responses.
3. Copy the **form endpoint URL** — it looks like:
   ```
   https://formspree.io/f/xyzabcde
   ```
4. Open `index.html` and replace the placeholder on **line ~134**:
   ```js
   // BEFORE
   const FORMSPREE_ENDPOINT = 'https://formspree.io/f/YOUR_FORM_ID';

   // AFTER (use your real ID)
   const FORMSPREE_ENDPOINT = 'https://formspree.io/f/xyzabcde';
   ```

---

## Step 2 — Publish to GitHub Pages

### 2-a Create a GitHub repository

1. Log in to [github.com](https://github.com).
2. Click **"New repository"**.
3. Name it however you like, e.g. `mphil-scheduling` (or `<yourname>.github.io` for a root site).
4. Set it to **Public** (required for the free GitHub Pages tier).
5. Do **not** add a README — you already have one.

### 2-b Push the project

Open a terminal inside the `mphil-scheduling` folder and run:

```powershell
cd C:\Users\quent\mphil-scheduling
git init
git add .
git commit -m "Initial commit – availability form"
git branch -M main
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/mphil-scheduling.git
git push -u origin main
```

Replace `YOUR_GITHUB_USERNAME` with your actual GitHub username.

### 2-c Enable GitHub Pages

1. In your GitHub repository, go to **Settings → Pages**.
2. Under **Source**, select **Deploy from a branch**.
3. Choose branch `main`, folder `/ (root)`.
4. Click **Save**.

GitHub will give you a URL like:

```
https://YOUR_GITHUB_USERNAME.github.io/mphil-scheduling/
```

It can take 1–2 minutes for the site to go live.

---

## Step 3 — Send personalised links

Append the `?p=` query parameter to the base URL for each recipient:

| Recipient | Link to send |
|---|---|
| Prof. Urs Maurer | `https://YOUR_GITHUB_USERNAME.github.io/mphil-scheduling/?p=urs-maurer` |
| Prof. Tomohiro Inoue | `https://YOUR_GITHUB_USERNAME.github.io/mphil-scheduling/?p=tomohiro-inoue` |
| Prof. Hon-Cheong So | `https://YOUR_GITHUB_USERNAME.github.io/mphil-scheduling/?p=hon-cheong-so` |

Each link pre-fills the **Name** field with that professor's name (read-only). Opening the URL without a valid `?p=` parameter shows a warning and blocks submission.

---

## Time slots covered

The form covers **weekday (Mon–Fri) morning and afternoon slots** for the two-week window:

| Week | Days |
|---|---|
| Week 1 | June 1 (Mon) – June 5 (Fri) |
| Week 2 | June 8 (Mon) – June 12 (Fri) |

That is **20 selectable slots** in total. Professors may tick as many as they wish.

> **Note:** June 14, 2026 falls on a Sunday, not a Friday.  
> The form therefore ends on **Friday June 12**, which is the last working day of the two-week window.

---

## Receiving responses

After each professor submits the form, Formspree will:
- Send their answers to your registered e-mail in a formatted message.
- Save a copy in the **Formspree dashboard** at <https://formspree.io>.

Each response will include:
- Respondent name (pre-filled)
- All selected time slots
- Online / In-Person preference
- Submission timestamp
