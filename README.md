# ROI-NeRFs Project Page

Project page for **ROI-NeRFs: Hi-Fi Visualization of Objects of Interest within a Scene by NeRFs Composition**.

Built using the [Nerfies](https://nerfies.github.io) template.

🔗 **Live site**: `https://qanhbui.github.io/roi-nerfstudio/`

---

## 📁 Directory Structure

```
roi-nerfstudio/          (branch: gh-pages)
├── index.html           ← Main page
├── static/
│   ├── images/
│   │   ├── teaser.png        ← Main teaser image
│   │   ├── pipeline.png      ← Method pipeline figure
│   │   └── results/          ← Comparison result images
│   │       ├── montmajour_baseline.png
│   │       ├── montmajour_ours.png
│   │       ├── marine_baseline.png
│   │       └── marine_ours.png
│   └── videos/               ← (Optional) Demo videos
│       └── demo.mp4
└── README.md
```

---

## 🚀 Deployment Guide (Step-by-Step)

### Option 1: Using a `gh-pages` branch (Recommended)

This approach keeps the main code (Python) on the `roinerfs-dev` branch and the website on a separate `gh-pages` branch.

#### Step 1: Clone the repository

```bash
git clone https://github.com/qanhbui/roi-nerfstudio.git
cd roi-nerfstudio
```

#### Step 2: Create an orphan `gh-pages` branch

```bash
# Create a brand-new empty branch (no history)
git checkout --orphan gh-pages

# Remove all files from the previous branch
git rm -rf .

# Verify — the directory should now be empty
ls
```

#### Step 3: Copy the project page files

```bash
# Copy index.html here
# Copy the static/ directory here

# The directory structure should look like:
# roi-nerfstudio/
# ├── index.html
# ├── static/
# │   ├── images/
# │   │   ├── teaser.png
# │   │   ├── pipeline.png
# │   │   └── results/
# │   └── videos/
# └── README.md
```

#### Step 4: Add your images

Place your image files in `static/images/`:

- `teaser.png` — Main teaser image (displayed at the top of the page)
- `pipeline.png` — Pipeline illustration (you can reuse `ROI-NeRFs_pipeline.png` from the `roinerfs-dev` branch)

```bash
# Grab the pipeline figure from the main code branch
git show roinerfs-dev:readme_images/ROI-NeRFs_pipeline.png > static/images/pipeline.png
```

#### Step 5: Commit and push

```bash
git add .
git commit -m "Initial project page"
git push origin gh-pages
```

#### Step 6: Enable GitHub Pages

1. Go to **https://github.com/qanhbui/roi-nerfstudio** → **Settings**
2. Left sidebar → **Pages**
3. Under **Source**: select **Deploy from a branch**
4. Choose branch: **gh-pages**, folder: **/ (root)**
5. Click **Save**
6. Wait 1–2 minutes; the site will be live at: **https://qanhbui.github.io/roi-nerfstudio/**

#### Step 7: Switch back to the main code branch

```bash
git checkout roinerfs-dev
```

---

### Option 2: Using a `/docs` folder on the main branch

If you prefer to keep the project page within the same branch as your code:

```bash
git checkout roinerfs-dev

# Create the docs directory
mkdir -p docs/static/images docs/static/videos

# Copy index.html into docs/
cp path/to/index.html docs/

# Copy images
cp readme_images/ROI-NeRFs_pipeline.png docs/static/images/pipeline.png

git add docs/
git commit -m "Add project page"
git push origin roinerfs-dev
```

Then go to Settings → Pages → select branch `roinerfs-dev`, folder `/docs`.

---

## ✏️ How to Edit Content

### Changing basic information

Open `index.html` and locate the following sections:

| Content | Find in HTML |
|---|---|
| Title | `<h1 class="publication-title">` |
| Author names | `<div class="publication-authors">` |
| Paper links | `<div class="publication-links">` |
| Abstract text | `<div class="abstract-content">` |
| BibTeX entries | `<div class="bibtex-block">` |

### Adding result images

1. Place images in `static/images/results/`
2. In `index.html`, find the **Results** section and replace the placeholders:

```html
<!-- Replace this -->
<div class="placeholder-img">...</div>

<!-- With this -->
<img src="static/images/results/montmajour_baseline.png"
     alt="Montmajour Baseline" style="width:100%;">
```

### Embedding a YouTube video

Find the `<!-- VIDEO -->` section and uncomment the iframe:

```html
<iframe src="https://www.youtube.com/embed/YOUR_VIDEO_ID?rel=0&showinfo=0"
        frameborder="0" allow="autoplay; encrypted-media" allowfullscreen
        style="width:100%; aspect-ratio:16/9; border-radius:12px;">
</iframe>
```

### Adding a local video

```html
<video autoplay muted loop playsinline style="width:100%; border-radius:12px;">
  <source src="static/videos/demo.mp4" type="video/mp4">
</video>
```

---

## 🔗 Linking the Project Page from Your Repo

After deployment, add the link to your repository:

1. Go to **repo Settings** → **General** → **Website** field → paste `https://qanhbui.github.io/roi-nerfstudio/`
2. Or add it to the `README.md` on the `roinerfs-dev` branch:

```markdown
## 🌐 Project Page
**[https://qanhbui.github.io/roi-nerfstudio/](https://qanhbui.github.io/roi-nerfstudio/)**
```

---

## 🎨 Customizing the Appearance

### Changing the color scheme

Find the `:root` section at the top of the CSS in `index.html`:

```css
:root {
  --primary: #4a6fa5;      /* Main color — change here */
  --primary-dark: #2c4a7c;
  --accent: #e07a5f;        /* Accent color */
}
```

### Adding a new section

Copy the structure of an existing section:

```html
<section class="section">
  <div class="container is-max-desktop">
    <h2 class="section-title">New Section Title</h2>
    <p>Your content here...</p>
  </div>
</section>
```

---

## 📝 Acknowledgments

- Template based on [Nerfies](https://nerfies.github.io) ([CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/))
- Built on [Nerfstudio](https://github.com/nerfstudio-project/nerfstudio)
