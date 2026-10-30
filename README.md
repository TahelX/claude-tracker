# Claude Account Tracker

## Publish with GitHub Pages
1. Upload `index.html` and `CNAME` to the root of your `claude-tracker` repository.
2. In GitHub repository Settings → Pages, choose Deploy from a branch, `main`, `/ (root)`.
3. Set the custom domain to `claude.heykadir.in` if that DNS record is configured.

## Supabase setup
- The page uses the Supabase project URL and publishable key in `index.html`.
- The `public.claude_accounts` table must have columns `id`, `user_id`, `label`, `email`, `service`, `plan`, `workspace`, `status`, `cooldown_end`, `cooldown_hours`, `created_at`, and `notes`.
- Enable Email authentication and create a user in Supabase Authentication → Users.
- RLS must be enabled and policies must restrict every operation to rows where `user_id = auth.uid()`.
- Keep secret/service-role keys and database passwords out of frontend code.

This is a manual tracker. It does not read Claude's actual usage limits automatically. Cooldown timestamps are saved in Supabase, so the countdown continues while the page is closed.
