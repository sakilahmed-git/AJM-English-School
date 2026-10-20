# AJM English School — School Website & Administration Workspace

> A full-stack school website designed to bring public information, academic resources, and day-to-day administrative tools into one application.

🌐 **Website:** [ajmenglishschool.in](https://ajmenglishschool.in)  
🧪 **Deployment note:** The domain has previously shown a browser security warning. Verify current availability and clear any warning before treating it as a trusted live demo.

## Overview

AJM English School combines a public-facing school website with an authenticated administration workspace. The public experience helps families find school information, academics, exam schedules, results, toppers, fees, and gallery content. The admin workspace supports the staff workflows behind student records and academic publishing.

## Key features

### Public website
- School landing page with campus imagery, animated hero, quick-access cards, school values, and contact information.
- Dedicated pages for academics, exam dates, results, toppers, fees, and gallery.
- Public result lookup by class and roll number.
- Printable marksheet view with class, roll number, and date-of-birth verification.

### Admin workspace
- Student directory for Classes 1–10.
- Create, edit, and delete student records.
- Manage admission details, date of birth, remarks, subject marks, unit-test totals, and ranks.
- Automatically recalculate totals across six subjects for each unit test.
- Preview and print student marksheets.
- Edit class-wise exam schedules and fee data using CSV workflows.
- Publish toppers, manage gallery uploads, and download data backups.

## Why this project stands out

- **End-to-end product thinking:** connects a public information experience with practical administrative workflows.
- **Data-driven functionality:** student records, marks, totals, rankings, exam schedules, and result lookup.
- **Privacy-aware design:** the documented public results endpoint uses an allow-list and avoids returning sensitive fields such as date of birth and admission number.
- **Useful school operations:** printable marksheets, bulk data editing, gallery management, and backup downloads.
- **Security considerations:** signed HTTP-only admin sessions and upload validation are documented.

## Technology

- Next.js 15
- React 19
- TypeScript
- Node.js-compatible hosting
- File-backed data workflows in the current implementation

## Live and development status

| Area | Status |
|---|---|
| Application | Implemented Next.js project |
| Local development | Supported |
| Public domain | Exists; current availability and browser security status need verification |
| Production readiness | Requires security hardening and deployment verification |

Before using this with real student data, add rate limiting to login and marksheet verification, review CSRF protections, protect backups, and consider transactional database storage for concurrent administrators. CSV fee management is not payment processing.

## Run locally

```powershell
npm install
Copy-Item .env.example .env.local
```

Set a strong private admin password and a random `ADMIN_SESSION_SECRET` of at least 32 characters in `.env.local`, then run:

```powershell
npm run dev
```

Open [http://localhost:3000](http://localhost:3000). Admin sign-in is at `/admin/login`.

**Never commit credentials, production environment files, student-data backups, or private student information to Git.**
