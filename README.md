# City Library — Static GitHub Pages Demo

This is a **static demo** of the City Library sample project. It is a single `index.html`
file using only HTML, CSS and plain JavaScript, with the browser's local storage standing
in for a real database. This is what makes it possible to host on **GitHub Pages**, which
cannot run PHP or connect to MySQL.

**This is a demo of the layout and flow only.** It does not satisfy the assignment's
mandatory requirements (real server-side PHP, a MySQL database, hashed passwords in a real
users table). The graded submission must be the full PHP + MySQL version, deployed on
InfinityFree (or similar) — see the main `library_system` project for that version.

## How to put this live on GitHub Pages

1. Create a new **public** repository on GitHub (e.g. `city-library-demo`).
2. Upload `index.html` (and this `README.md`) to the repository — either drag-and-drop on
   the GitHub website ("Add file" → "Upload files") or with `git push`.
3. In the repository, go to **Settings → Pages**.
4. Under "Build and deployment" → "Source", choose **Deploy from a branch**.
5. Under "Branch", choose `main` (or `master`) and folder `/ (root)`, then **Save**.
6. Wait 1–2 minutes, then refresh the Pages settings page — it will show your live link,
   something like:
   `https://yourusername.github.io/city-library-demo/`
7. Open that link. You should see the home page, not a 404. Try Register → Login → Books →
   Borrow → Dashboard → Return to confirm it works end-to-end.

## Why the PHP version 404'd on GitHub

GitHub Pages only serves static files. When it receives a request for `index.php`, it has
no PHP engine to run, so it either serves the raw source code as text or returns a 404,
depending on the file. Register, login and the database connection in the real project only
work on a server that executes PHP — GitHub Pages is not that kind of server. That's why the
assignment separates "push to GitHub" (for code + history) from "deploy to a PHP host"
(for the live working link).

## Notes
- Data is stored per-browser (`localStorage`/`sessionStorage`), so it won't be shared between
  visitors and resets if you clear your browser data.
- Passwords are stored as plain text in local storage in this demo only, because there is no
  server to hash them. The real PHP version uses `password_hash()`/`password_verify()` and
  never stores a plain password — do not present this demo's password handling as the real
  mechanism in the assignment report.
