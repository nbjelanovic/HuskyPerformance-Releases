# Changelog

All notable public-facing changes to Husky Performance are recorded here.

Husky Performance is still pre-release software. Entries under **Unreleased** describe work completed for a future preview but not yet included in the current public download. A change moves into a numbered release only after its package has been built and validated.

## [Unreleased]

### Improved

- Confirmed Husky Performance's business-only product direction. Future Preview builds always use Professional business capabilities, and the customer-facing desktop no longer reads the retired Personal development override. Guided Setup always uses Business / Shop identity and Professional Open Shop access, and Customers always presents business customer/shop and work-order workflows. Historical Personal-mode data readers remain only for migration and regression safety and are not an offered product path.
- Restricted the private licensing registry to new Professional business licenses. Personal issuance is rejected even if the registry service is called directly, and the admin screen no longer offers it. Historical Personal records remain visible only as legacy support and migration data.
- Added a central language-pack catalog for language codes, cultures, names, aliases, safe English fallback, and translation lookup. The shell, Settings, and Guided Setup language choices now come from this catalog instead of separate hand-maintained lists. A translation-management utility exports a reviewable UTF-8 CSV and reports missing entries and unsafe format-placeholder changes, making existing translations easier to maintain and future languages easier to add.
- Added owner-selectable Professional business profiles for performance/tuning shops, injector testing/cleaning businesses, and combined businesses. The Dashboard identifies the selected profile, orders its summary cards by the business's configured priorities, and prioritizes its Quick Launch actions. Reports opens at a relevant starting template with profile-specific guidance while keeping every report template available and preserving later user choices. Guided Setup presents a short recommended starting path for the selected business. Profiles are presentation choices only: every Dashboard summary and Professional workspace remains available, and changing profiles never moves, hides, or deletes records.
- Added a read-only, filterable chronological vehicle history that brings existing vehicle lifecycle events, linked logs, work-order activity, and injector-service records into one view without inventing missing history.
- Expanded German and Russian interface coverage across the Support and Vehicles workspaces.
- Added German and Russian translations for the complete offline Support help library, including instructions, notes, actions, and privacy guidance.
- Improved German and Russian wording for vehicle details, assignments, capacity summaries, archive controls, and vehicle state labels.
- Clarified the saved analysis-channel preset workflow so users can select channels, choose **Save Current**, name the preset, and reuse it later.
- Saved analysis workspaces now remember which analysis panels were left expanded or collapsed for each saved log.

### Fixed

- Corrected additional English fallback text that could appear while using German or Russian.
- Improved consistency of localized dynamic labels and vehicle states.

### Validation

- Verified an isolated PrivatePreview build still visibly identifies itself as `DEVELOPMENT LICENSE • PROFESSIONAL • SIMULATION` when the retired Personal override is deliberately set, while retaining its Preview label and backup-before-use warning.
- Replaced the obsolete Personal-owner validation path with coordinated checks for the three supported Professional business profiles.
- Verified that the private registry accepts Professional business registration and rejects attempted Personal issuance at its service boundary.
- Verified the language catalog, catalog-generated shell/Settings/Guided Setup choices, CSV export, English fallback, and numbered-placeholder safety. The controlled UI catalog currently contains 1,144 English keys; Spanish covers 942, and German and Russian each cover 617, with zero invalid numbered placeholders.
- Verified real Guided Setup behavior for the Business / Shop identity label, Professional Open Shop default, all five setup steps, revisiting, safe Quick Setup, Skip for now, and deferred re-prompt.
- Verified Professional business-profile selection, safety preview, immutable audit history, restart persistence, reversible switching, dashboard summary-card and Quick Launch priority, unchanged full navigation, profile-specific report starting points, retained access to every report template, preservation of a user's report-template choice during refresh, profile-specific Guided Setup instructions, and safe fallback for unknown or retired profile IDs.
- Verified the vehicle-history data contract and compatibility with supported libraries that do not yet contain injector-session detail tables.
- Expanded automated localization checks to protect German and Russian coverage from regression; each currently covers 617 verified mappings.
- Current development Release builds and all 88 foundation checks pass with zero build warnings and zero build errors.

## [0.8.99] - 2026-07-26

### Added

- Released the first five-day Public Demonstration Preview for Windows x64.
- Added a self-contained MSI installer and portable ZIP package; no separate .NET or PowerShell installation is required.
- Added local ECU-log importing, saved-log organization, full-resolution analysis, channel comparison, customers, vehicles, injector-service workflows, reports, exports, backup, and restore.
- Added English, Spanish, German, and Russian interface and report support.
- Added an encrypted, demonstration-specific local database.
- Added visible Public Demonstration and not-for-production identification.
- Added safe viewing, export, backup, and restore access after the five-day evaluation expires.

### Changed

- The five-day evaluation begins after the first successfully saved real log import rather than at installation.
- The Public Demonstration uses a separate application-data location and does not open, move, modify, or package data from another Husky installation.
- A new Public Demonstration installation starts with zero logs, vehicles, customers, and work orders.

### Privacy and safety

- Processing and storage remain local to the computer.
- Husky does not automatically upload logs, customer information, diagnostics, reports, or usage data.
- Reports and exports created during the demonstration remain clearly identified as trial output.

### Fixed

- Prevented the Public Demonstration from inheriting development or private-preview access.
- Prevented a new public evaluator from being blocked by private-preview backup requirements before the first import.
- Prevented the Public Demonstration from opening data preserved by another Husky installation.

### Known limitations

- This is unsigned pre-release demonstration software, so Windows may display an unknown-publisher warning.
- It is not approved or intended for production shop use. Use copied logs and fictional or test customer information.
- German and Russian specialized automotive terminology still benefits from review by native-speaking performance professionals.
- Analysis and injector calculations are descriptive aids, not automatic diagnosis, pass/fail, tuning, or machine-control decisions.
- Independent clean-machine coverage, Windows 10 acceptance, code signing, legal review, and production-release approval remain incomplete.

[Unreleased]: https://github.com/nbjelanovic/HuskyPerformance-Releases/compare/v0.8.99-public-demo...HEAD
[0.8.99]: https://github.com/nbjelanovic/HuskyPerformance-Releases/releases/tag/v0.8.99-public-demo
