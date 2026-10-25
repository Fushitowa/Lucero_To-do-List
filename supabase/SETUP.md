# Supabase setup

1. Create a Supabase project.
2. In **Authentication → Sign In / Providers**, enable **Allow anonymous sign-ins**. The app uses a persisted anonymous Supabase user so every task remains private to that browser profile without exposing a service-role key.
3. Open **SQL Editor**, paste and run `migrations/20261025000000_create_tasks.sql`.
4. Copy the project URL and publishable key from the project’s **Connect** dialog into a new root `.env` file, using `.env.example` as the template.
5. Restart the Vite development server. On first connection, existing tasks in this browser are copied into Supabase; existing local storage remains as a fallback.

Anonymous accounts are tied to the browser’s stored session. Clearing site data or switching browsers creates a new account and does not restore the prior account’s tasks. Add a permanent sign-in method if cross-device access is needed.
