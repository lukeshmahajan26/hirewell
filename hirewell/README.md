# Hirewell – Job Board Portal

A responsive, front-end-only job board portal built with plain HTML, CSS and JavaScript. Job seekers can search and apply for jobs and track their applications, and employers can post jobs and manage applicants. Data is stored in the browser with localStorage, so there is no backend to set up.

Open `index.html` in a browser. No build step and no server needed.

## Structure
```
index.html            markup only
css/                  tokens, base, layout, components, one file per screen, responsive
js/core/              bus (events), storage (localStorage adapter), utils
js/services/          auth, job, application, stats  (data + rules, no DOM)
js/ui/                shell + one module per screen    (DOM only, calls services)
js/app.js             bootstrap
```
Services never touch the DOM and never call each other's internals except through
their public API or the event bus (`jobs:removed`, `auth:login`, `apps:changed` ...).
Everything runs in the browser. Data is kept in localStorage, so there is no backend, database or server to set up.

## Features
- Login and register with job seeker and employer roles
- Search, category, job type and location filters, plus sorting
- Structured forms to post, edit, close and delete jobs
- Application tracking: Applied, Screening, Interview, Offer, Rejected
- Overview dashboard with live counts and charts
- Salaries shown in ₹ (INR)
- Responsive layout with light and dark mode