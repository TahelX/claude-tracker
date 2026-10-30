# Claude Account Tracker

Static, browser-based account tracker designed for GitHub Pages.

## Deploy to GitHub Pages

1. Create a new public GitHub repository, for example `claude-tracker`.
2. Upload `index.html`, `CNAME`, and `README.md` to the repository root.
3. In the repository, open **Settings → Pages**.
4. Set the source to **Deploy from a branch**, choose `main` and `/ (root)`, then save.
5. In Hostinger DNS for `heykadir.in`, add this record:

   - Type: `CNAME`
   - Name/Host: `claude`
   - Target/Points to: `tahelx.github.io`
   - TTL: default

6. Wait for DNS to propagate, then return to **Settings → Pages** and verify the custom domain is `claude.heykadir.in`.
7. Enable **Enforce HTTPS** once GitHub makes it available.

## Important data note

The tracker stores account records in the browser's local storage. It does not sync between devices or browsers. Export a JSON backup regularly. Do not store account passwords in this tracker.
