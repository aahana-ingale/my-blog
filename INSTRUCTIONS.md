# 📝 Blog Publishing Guide

Welcome! You only need **two commands** to write and publish a blog post.

---

## 🚀 Step 1: Open the Codespace

1. Go to the repository on GitHub.
2. Click **Code**.
3. Open the **Codespace**.
4. Wait a few seconds.

The blog preview will open automatically in your browser.

You’re ready to start writing.

---

## ✍️ Step 2: Create a New Blog Post

In the terminal, type:

```sh
make new "Your Blog Title"
```

Example:

```sh
make new "My Trip to Japan"
```

This will:

- Create a new blog post folder
- Create an `images` folder inside the post folder
- Open the file so you can start writing

The folder structure will look like:

```sh
content/blog/your-blog-title/
├─ index.md
├─ images/
└─ cover.png  (optional)
```

---

## 🖼 Adding Metadata

Open `index.md` and make sure to:

- Change `draft: true` → `draft: false`  
  This ensures the post is published.
- Add tags under `tags:` in the metadata, e.g.:

```yaml
tags:
  - travel
  - japan
```

- Set the cover image:

```yaml
cover: cover.png
```

Place `cover.png` in the same folder as `index.md`.

---

## 🖼 Adding Images to the Post

You can add images in **two ways**:

### 1️⃣ Standard Markdown

```markdown
![Description](images/your-image.jpg)
```

### 2️⃣ Hugo Shortcode (with alignment)

```markdown
{{< figure
  src="images/photo1.png"
  align="center"
>}}
```

Both methods use files from the `images` folder inside your post directory.

---

## 👀 Preview Your Post

In the terminal, type:

```sh
make dev
```

Click on the localhost:1313 and the forwarded browser should open. Refresh the browser to see your changes.

Draft posts are visible in preview, but make sure you set `draft: false` before publishing.

---

## 🌍 Step 3: Publish Your Post

When you're ready to publish, run:

```sh
make go
```

This will:

- Stage all changes
- Commit with a message like `"Add blog for your-blog-title"`
- Push to GitHub
- Trigger deployment to Cloudflare Pages

Your post will be live in a few minutes.

---

## ✅ Quick Summary

1. Create a new post:

```sh
make new "Title"
```

1. Edit metadata:

   - Set `draft: false`
   - Add `tags`
   - Set `cover: cover.png` if you have a cover image

2. Add images using Markdown or Hugo shortcode:

   - Markdown: `![Desc](images/file.jpg)`
   - Shortcode: `{{< figure src="images/file.png" align="center" >}}`

3. Publish:

```sh
make go
```

That’s it. No Git knowledge required.
