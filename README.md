# HR Employee Portal + Separated Admin Console v10

## Release summary

This version separates the employee experience from the management experience:

- `index.html` is now the employee-facing guided form only.
- `admin.html` is a full management console with its own professional login screen.
- Double-clicking the `HR` logo in `index.html` redirects to `admin.html`.
- `version.json` is used by both pages for automatic refresh after deployment.
- `firestore.rules` was updated to allow authorized admins to edit/delete submissions while preserving employee write constraints.

## Admin login

Open `admin.html` directly, or double-click the HR logo from `index.html`.

Admin login includes:

- English as the default admin language.
- Arabic/English switch.
- Saved admin language preference through `localStorage`.
- Remember me option using Firebase Auth persistence.
- Strong login error messages.
- Bootstrap admin button for the configured UID when the Firestore admin document is missing.

## Admin console features

- Executive dashboard.
- Completion rate by company.
- Missing fields heatmap.
- Recent activity.
- Submissions table.
- Employee directory table.
- Missing submissions table.
- Audit center.
- Export center.
- Import center.
- View record through eye action.
- Edit submission JSON with audit logging.
- Edit employee directory JSON with loginIndex update.
- Delete submission or employee record with `DELETE` confirmation.
- Export Employees, Family Members, Assets, Missing Employees, and Audit Log.
- Import private employee seed JSON and create `employeeDirectory` + `loginIndex` automatically.

## Deployment

Upload all files to GitHub Pages:

- `index.html`
- `admin.html`
- `version.json`
- `firestore.rules` only for reference, not needed publicly but useful for deployment documentation
- `favicon.ico`
- `favicon.svg`
- `apple-touch-icon.png`

Do not upload private employee seed files to GitHub.

## Required Firebase setup

Publish the included `firestore.rules` file before using admin edit/delete features.

Authentication must have Email/Password enabled. The configured bootstrap UID is:

`PwyarKYD7iTs1sbE0rTLqHrkqdv1`

## Cache/version behavior

Both pages read `version.json?ts=Date.now()` and refresh when the deployed version changes. This reduces the need for Ctrl+F5 after updates.
