Cane Next+ Admin Email Authorization Fix

1. Supabase > SQL Editor
   Run admin_email_authorization.sql

2. Confirm user_profiles contains:
   email = wipadas@mitrphol.com
   role = admin
   status = active

3. Upload index.html and config.js to GitHub Pages.

4. Logout, then login again.

5. Open Data Management and Import.

This version checks the signed-in Supabase email against user_profiles.email.
It no longer depends on auth_uid matching.
