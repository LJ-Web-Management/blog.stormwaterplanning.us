# Publishing a new blog post

To publish a new post, add a file to this `uploads/` folder and push it to `main` (or upload it directly on GitHub: **Add file → Upload files**, selecting this folder).

Supported formats:

- **`.docx`** — a Word document. The first heading or paragraph becomes the post title; the rest becomes the post body.
- **`.txt`** — a plain text file, one paragraph per line.
- **`.zip`** — a zip containing one `.docx`/`.txt` plus (optionally) one image file (`.jpg`, `.jpeg`, `.png`, `.webp`, `.gif`) to use as the post's featured image.

Once the file lands in `uploads/`, a GitHub Actions workflow (`.github/workflows/convert-docx.yml`) automatically:

1. Converts the document to a styled HTML post under `posts/`.
2. Adds an entry to `posts.json` so it shows up on the blog homepage.
3. Moves the original file into `uploads/processed/` so it isn't converted again.
4. Commits and pushes the result straight to `main`, which redeploys the live site via GitHub Pages.

No local setup is required — everything runs in GitHub Actions.
