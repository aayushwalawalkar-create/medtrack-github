# MedTrack

A front-end prototype for a paperless patient case-taking workflow.

MedTrack helps clinicians move from patient input to a structured, reviewable case record while keeping red-flag alerts, prescriptions, and the patient timeline in one place.

## Included prototype pages and flows

### Animated opening page (`index.html`)

- Animated MedTrack logo splash screen
- “because health matters” brand tagline
- Animated orbit graphics and loading transition
- Automatically opens the Patient/Doctor login page after the intro
- Manual “Continue to login” option

### Optional creative welcome page (`welcome.html`)

- Full animated product welcome page
- Medical case summary graphic
- Floating profile, preparation-time, and consent cards
- Patient/Doctor story section
- Sponsored partner placement

### Product details page (`landing.html`)

- Patient and doctor value propositions
- Structured case-taking USP
- Patient-to-consultation workflow
- AI-assisted case preparation explanation
- Doctor subscription business model
- Privacy and stigma-sensitive case-taking message
- Responsive layout with patient/doctor view toggle

### Patient portal (`patient.html`)

- My overview dashboard with profile completeness and quick actions
- Editable personal profile with name, age, date of birth, sex, blood group, and emergency contact
- Medical history sections for allergies, conditions, surgeries, and current medications
- Add and remove records through interactive forms and modals
- Consultation history with doctor, specialty, summary, and care tags
- Prescription and report upload form with image previews, document dates, doctor name, and notes
- Appointment search and booking flow with doctor, date, time, and reason for visit
- Medicine reminders with medicine name, dose, alarm time, frequency, start/end dates, and notes
- Reminder on/off switches and remove actions
- Reminder summary showing active alarms, next dose, and today’s dose count
- Patient-controlled doctor access with grant, deny, and revoke actions
- Access request, granted, denied, and restricted status views
- Doctor dashboard consent-status notice showing that records require patient approval
- Privacy and consent messaging
- Multilingual input selector for English, Hindi, Marathi, Gujarati, Bengali, Tamil, Telugu, and Kannada
- Browser voice-input controls for symptoms, allergies, medical history, surgeries, medications, and lifestyle notes
- Automatic translation-preview state using the clinic’s default language; patients do not need to choose the doctor’s output language
- Demo data saved in browser `localStorage`, so changes remain visible during local use

Voice capture uses the browser Speech Recognition API when supported. Full medical translation into any language should be connected to a secure, clinically reviewed translation service before production use; the prototype preserves the original patient wording and clearly presents the conversion as a preview.

The patient portal is a front-end prototype. Data is stored only in the current browser and is not yet sent to a secure backend.

### Interactive clinician demo (`app.html`)

- Clinician overview dashboard
- Today's patient queue
- Allergy and red-flag review alerts
- Adaptive new-case intake flow
- AI case summary preview
- Patient directory
- Patient timeline across visits
- Prescription safety view
- Responsive layout for smaller screens

Open `index.html` first to see the animated logo intro; it then opens the login screen automatically. The previous creative welcome page is preserved as `welcome.html`, and the product details page is preserved as `landing.html`.

The page communicates that AI organizes and summarizes information for review; it does not diagnose or replace the clinician.

## Pricing model

- Patients — Free
- Doctors — First month free, then ₹100 per month
- Clinics — ₹100 per month

This is the current hackathon pricing assumption and can later be refined with plan limits, taxes, payment processing, and clinic-size tiers.

## Paid promotion placements

The prototype includes clearly labeled sponsored placements across the homepage, login page, patient portal, and doctor dashboard for potential partners such as:

- Pharmacy and medicine-delivery apps
- Diagnostic laboratories
- Medical device companies
- Clinical and prescription-management tools

The patient portal’s sponsored **Explore** buttons open interactive catalog tabs with demo medicine or diagnostics listings and prices. These placements are mock UI only. Production ads should use transparent sponsorship labels, privacy-safe targeting, medical advertising review, and clear separation from clinical recommendations.

## Demo login flow

After the animated intro, `login.html` presents separate **Patient** and **Doctor** login choices with ID and password fields.

For this prototype, enter any non-empty login ID and password. The demo redirects to:

- Patient login → `patient.html`
- Doctor login → `app.html`

This is intentionally a visual demo only. It does not authenticate users or protect real data.

## Included files

- `index.html` — animated logo intro that opens the login page
- `login.html` — Patient/Doctor credential page
- `welcome.html` — optional full creative welcome page
- `landing.html` — detailed product page with product story, pricing, and workflow
- `patient.html` — interactive patient portal
- `app.html` — interactive clinician dashboard prototype
- `README.md` — project documentation
- `.gitignore` — standard local-file exclusions
- `LICENSE` — MIT license

## Run locally

No build step or dependencies are required.

1. Download or clone the repository.
2. Open `index.html` in a browser.

For a local server, run:

```bash
python -m http.server 8000
```

Then open <http://localhost:8000>.

## Deploy with GitHub Pages

1. Create a new GitHub repository, for example `medtrack`.
2. Upload `index.html` and this `README.md`.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select the `main` branch and `/ (root)` folder.
6. Save. GitHub will provide the public Pages URL.

## Current scope

This is a front-end demonstration using sample patient data. It does not yet connect to a database, authentication provider, clinical AI model, prescription database, or electronic health record.

Before using real patient information, add appropriate authentication, encryption, access controls, audit logging, consent handling, privacy controls, and clinical safety review.

## Suggested next implementation steps

1. Add a backend API and database for patients, visits, allergies, medications, and audit events.
2. Add clinician and patient authentication with role-based access.
3. Replace the summary demo with a reviewed AI extraction service.
4. Add a real medication interaction database and clinical alert workflow.
5. Add automated tests for red-flag detection and case approval.
