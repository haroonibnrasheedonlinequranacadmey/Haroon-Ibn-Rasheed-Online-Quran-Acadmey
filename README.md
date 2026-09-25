# Haroon Ibn Rasheed Online Quran Academy

Single static website with separate HTML pages for Admin, Teacher and Student portals.

## Supabase connection
The frontend is connected to the academy Supabase project using the public **publishable key**. Row Level Security (RLS) must remain enabled.

- Project URL: configured in `assets/supabase-config.js`
- Publishable key: configured in `assets/supabase-config.js`
- **Never** put a Supabase secret/service_role key in this repository.

## Login
The login page now uses Supabase Auth instead of the old localStorage demo accounts. The user's role is read from `public.profiles` and must match the selected Account Type.

## Current database
The supplied SQL setup creates profiles, students, teachers, courses, materials, enrollments, schedules, group classes, leave applications, teacher salaries, attendance and notifications, with RLS policies.

## Important next backend step
A browser-only static site cannot safely create Auth users for other people with the Supabase Admin API. Teacher/student account creation should use a secure server-side Edge Function (or another trusted backend) using the secret key. The secret key must never be placed in HTML, JavaScript, GitHub, or the browser.

## GitHub Pages
Upload the project folder to the same GitHub repository. The site remains one website; each HTML file is simply another page under the same GitHub Pages domain.
