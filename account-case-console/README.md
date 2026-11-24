# Account & Case Console

A static browser-based admin console for the Supabase demo project.

## Features
- List and search Accounts and Cases
- Add and update Accounts
- Create cases and append Genesys interaction IDs to an existing matching active case
- Update case status, priority, description, subject and account/transaction association
- Refresh tables and see summary counts

## Configuration
Open the page and enter:
- Project URL: https://uegnxuaystagioadgwzv.supabase.co
- Your Supabase publishable/anon key (never use the service_role key in browser code)

The Cases UI calls:
https://uegnxuaystagioadgwzv.supabase.co/functions/v1/dynamic-function

The Accounts UI uses the Supabase REST API against public."Accounts".

## Supabase requirements
- The Accounts table needs anon grants and suitable SELECT, INSERT and UPDATE RLS policies for the demo.
- The Case Edge Function must support get_all, add and update, and its RLS policies must allow required operations.
- If calls are intended without an Authorization header, ensure the Edge Function is deployed with JWT verification disabled.

## GitHub Pages
The page is stored at `account-case-console/index.html` in the `zIdeas` repository. To publish it:
1. Open repository Settings → Pages.
2. Under Build and deployment choose Deploy from a branch.
3. Select `main` and `/(root)`, then Save.
4. Wait for GitHub Pages deployment to finish.

Expected page URL:
https://krishnulal.github.io/zIdeas/account-case-console/

This is a public static page. A publishable key is designed for browser use, but it does not make unrestricted data access safe. Do not use this UI with real customer records until authentication and row-level authorization are implemented. Never expose a service_role key.
