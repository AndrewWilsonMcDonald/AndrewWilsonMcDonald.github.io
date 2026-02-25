# How to Edit Your Website (No Coding Required)

## What Changed and Why

Your old site was ONE big file (`index.html`) where your content and design were mixed together. Now your site has **separate files for separate jobs**:

| File | What it does | How often you'll edit it |
|------|-------------|------------------------|
| `index.md` | Your page content (bio, descriptions) | Whenever you update your bio |
| `_data/clips.yml` | Your list of writing clips | Every time you publish something new |
| `_layouts/default.html` | The design/styling | Rarely, only if you want a new look |
| `_config.yml` | Site settings (your name, URL) | Almost never |

**The magic:** GitHub Pages has Jekyll built in. When you push these files to your repo, GitHub automatically combines your content (`index.md`) with your template (`_layouts/default.html`) and generates the final HTML page. You never have to touch HTML again.

---

## The #1 Thing You'll Do: Add a New Clip

This is the task you'll do most often. Here's exactly how:

### Step 1: Go to Your Repository
1. Open your browser and go to: `https://github.com/AndrewWilsonMcDonald/AndrewWilsonMcDonald.github.io`
2. Make sure you're signed in to GitHub

### Step 2: Open the Clips File
1. Click on the `_data` folder
2. Click on `clips.yml`
3. Click the **pencil icon** (✏️) in the top-right of the file to edit it

### Step 3: Add Your New Clip
Scroll to the **top** of the list (right after the instructions section) and add a new entry. Copy this exact pattern:

```
- title: "Your Headline Here"
  url: "https://the-link-to-your-story.com"
  desc: "Short description"
```

**Real example** — say you just published a new WFUV piece:

```
- title: "NYC Budget Crisis Deepens Under Mamdani"
  url: "https://wfuv.org/content/nyc-budget-crisis"
  desc: "Investigation into municipal spending shortfalls"
```

#### Rules to follow:
- The **dash and space** (`- `) goes before `title` — this marks a new clip
- `title`, `url`, and `desc` each need **exactly 2 spaces** before them (not a tab!)
- Put all values in **quotes** `" "`
- `desc` is optional — just delete that whole line if you don't need a description
- Add new clips at the TOP of the list so your newest work appears first

### Step 4: Save (Commit) Your Changes
1. Scroll down to the green **"Commit changes"** button
2. In the commit message box, type something like: `Add new WFUV clip`
3. Make sure **"Commit directly to the main branch"** is selected
4. Click **"Commit changes"**

### Step 5: Wait ~1-2 Minutes
GitHub Pages rebuilds your site automatically. After a minute or two, visit your site to see the new clip live.

---

## How to Edit Your Bio or Page Content

### Step 1: Open `index.md` in Your Repository
1. Go to your repo on GitHub
2. Click on `index.md`
3. Click the pencil icon (✏️) to edit

### Step 2: Edit the Content
The file is written in **Markdown**, which is basically plain text with a few simple formatting tricks:

| What you want | What you type |
|--------------|---------------|
| **Bold text** | `**Bold text**` |
| *Italic text* | `*Italic text*` |
| A link | `[Link text](https://url.com)` |
| A heading | `## Heading` |
| A new paragraph | Just leave a blank line between paragraphs |

So if you want to change your bio paragraph, just find it in the file and type your new text. No HTML tags needed.

**Example:** To change your intro, find this line:
```
I'm a journalist and student at Fordham University...
```
And just replace it with whatever you want. Plain English.

### Step 3: Commit Your Changes
Same as before — scroll down, write a short message like `Update bio`, and click **"Commit changes"**.

---

## How to Update Your Contact Links

Your contact links are in `index.md` and look like this:

```
[andrewwilsonmcdonald@gmail.com](mailto:andrewwilsonmcdonald@gmail.com) |
[LinkedIn](https://linkedin.com/in/andrew-mcdonald-7b720228b) |
```

To change a link, just replace the URL inside the parentheses. To add a new one, follow the same `[Display Text](URL) |` pattern.

---

## How to Replace Your Headshot

1. Name your new photo `photo.jpg` (same name as the current one)
2. Go to your repository on GitHub
3. Click **"Add file"** → **"Upload files"**
4. Drag in your new `photo.jpg`
5. GitHub will ask if you want to replace the existing file — say yes
6. Commit the change

---

## File Structure Cheat Sheet

```
YourRepo/
├── _config.yml          ← Site settings (name, URL)
├── _data/
│   └── clips.yml        ← ⭐ YOUR CLIPS LIST (edit this most often)
├── _layouts/
│   └── default.html     ← Design template (don't touch unless restyling)
├── index.md             ← ⭐ YOUR PAGE CONTENT (bio, descriptions)
└── photo.jpg            ← Your headshot
```

---

## Setting This Up (One-Time Migration)

Since you already have a GitHub Pages repo, here's how to switch over:

### Step 1: Back Up Your Current Site
1. Go to your repo: `https://github.com/AndrewWilsonMcDonald/AndrewWilsonMcDonald.github.io`
2. Download your current `index.html` somewhere safe (click it, then click the download button), just in case

### Step 2: Upload the New Files
1. On your repo page, click **"Add file"** → **"Upload files"**
2. Drag in ALL of these files/folders:
   - `_config.yml`
   - `_data/` folder (with `clips.yml` inside)
   - `_layouts/` folder (with `default.html` inside)
   - `index.md`
3. Commit the upload

### Step 3: Delete the Old `index.html`
1. Click on `index.html` in your repo
2. Click the **trash can icon** (🗑️) in the top-right
3. Commit the deletion
4. **Important:** Jekyll will now use `index.md` instead. Your site URL stays the same.

### Step 4: Verify
Wait 1-2 minutes, then visit `https://andrewwilsonmcdonald.github.io`. It should look exactly the same as before — but now it's way easier to edit.

---

## Troubleshooting

**Site looks broken after an edit?**
- Go to your repo → click **"Actions"** tab → check if the latest build has a red ❌
- If so, click on it to see the error. Usually it's a spacing issue in `clips.yml`
- Most common fix: make sure you used 2 spaces (not tabs) before `title`, `url`, and `desc`

**New clip not showing up?**
- Wait 2 minutes — GitHub Pages can be slow
- Hard refresh your browser: `Ctrl+Shift+R` (Windows) or `Cmd+Shift+R` (Mac)
- Check that your clip entry has the right format (dash, spaces, quotes)

**Site returns a 404?**
- Make sure you deleted `index.html` (Jekyll and raw HTML can conflict)
- Make sure `index.md` has the three dashes at the very top:
  ```
  ---
  layout: default
  ---
  ```
