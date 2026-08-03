# Husky Performance Project Status

_Last updated: August 3, 2026_

This page is the easiest place to understand what people can download today, what is being developed, what may appear in the next trial release, and what remains on the longer-term roadmap.

Husky Performance is proprietary, pre-release Windows software for professional automotive performance shops. It is under active development and is not yet approved for production shop use.

## Quick links

- [Download the current Public Demonstration Preview](https://github.com/nbjelanovic/HuskyPerformance-Releases/releases/tag/v0.9.0-public-demo)
- [Read the detailed public changelog](CHANGELOG.md)
- [Learn about becoming a testing partner](TESTING-PARTNERS.md)
- [Follow Husky Performance on Facebook](https://www.facebook.com/HuskyPerformanceApp)

## Currently Available

### Husky Performance 0.9.0 Public Demonstration Preview

The current public release is a five-day Windows x64 evaluation intended to prove that Husky is a genuine working desktop application and to collect practical feedback.

It currently includes:

- Local ECU-log import and saved-log organization
- Full-resolution channel analysis and log comparison
- Multi-file import queues plus bounded large-log review
- Multi-select professional business types and composed starting recommendations
- Tune Library originals, lineage, relationships, and protected export workflows
- Bounded Husky-native customer session-report layouts
- Customer, vehicle, and work-order organization
- Injector Service workflows and reports
- PDF, CSV, HTML, image, and package-oriented export workflows where applicable
- Complete and configuration/records backup and restore workflows
- English, Spanish, German, and Russian interface support
- Local encrypted demonstration storage
- No automatic telemetry or uploads
- Simulator remains visible but every public-package entry point is intentionally disabled while its presentation remains in development

The five-day evaluation begins with the first successfully saved real log, not when the application is installed. After expiration, safe viewing, export, backup, and restore access remain available.

The current preview is unsigned pre-release software. Windows may show an unknown-publisher warning. Use copied logs and fictional or test customer information only.

## In Progress

### Log Simulator and virtual dashboard

Simulator remains an internal development workspace for replaying exact samples from a saved log on their original recorded timeline. It is deliberately disabled in the 0.9.0 Public Demonstration package until its realistic cockpit, scenery, gauges, controls, and packaged behavior receive owner acceptance.

Current validated development capabilities include:

- Play, pause, Stop and return to the beginning, restart, timeline scrubbing, and 0.25x through 4x playback
- A maximum of eight visible gauges so the dashboard remains readable
- Channel presets for common engine, fuel/air, temperature, wheel, and chassis views
- Per-gauge Analog, Dial, Digital, LED Ring, or Bar presentation
- Per-gauge Small, Medium, or Large sizing
- Optional recorded Min/Max display
- Edit Dashboard and Close Editor modes
- A visible alignment grid with position snapping
- Movable gauges and a movable or hideable performance panel
- Full-screen playback with a visible exit action
- Per-log dashboard-layout persistence
- Qualified 0–60 mph, 0–100 mph, 1/8-mile, 1/4-mile, custom acceleration, and braking calculations when the log truly contains enough compatible evidence

Performance results are deliberately withheld when their required starting conditions, speed, RPM, throttle, time continuity, or uninterrupted run are not present. Simulator values are analysis aids, not calibrated instrumentation, verified track timing, automatic diagnosis, or safety decisions.

The gauge artwork is being refined around original Husky designs informed by real automotive instrument conventions. Current work includes layered bezels, detailed scale divisions, numeric labels, tapered needles, high-contrast digital windows, and segmented LED-ring gauges.

An experimental inside-car/track visualization also exists in development, but it is not considered presentation-ready and is not approved for promotional screenshots. The gauge dashboard is the priority.

### Application quality and release validation

Development also continues on:

- Window sizing, scrolling, accessibility, and enlarged-text behavior
- Saved-log analysis and comparison workflows
- Vehicle and chronological session history
- Injector Service request/result exchange and reporting
- Backup, restore, recovery, and data-protection evidence
- German and Russian coverage and terminology review
- Package, installer, clean-machine, and supported-Windows validation

Passing local checks do not by themselves make a build production-ready. Package validation, independent-machine testing, owner acceptance, signing, licensing, and legal review are tracked separately.

## Potential Next Trial Release

Work after 0.9.0 will remain limited to validated corrections recorded under [Unreleased](CHANGELOG.md) and explicitly approved workflow increments.

Simulator can return to a public build only after its cockpit, scenery, gauges, controls, and packaged playback receive explicit owner acceptance. Until then, it remains visible but disabled in public packages.

Any later trial build remains candidate scope until its exact version and contents are reviewed, its safety language is correct, package and installer checks pass, and owner approval is recorded.

## Roadmap

### Nearer-term priorities

- Complete a trusted business-only Professional trial release
- Continue improving Simulator gauges and useful default layouts
- Expand practical ECU-log analysis, comparison, and reporting workflows
- Strengthen customer, vehicle, work-order, and session history
- Continue Injector Service intake, testing, exchange, analysis, and customer-report workflows
- Complete package, installer, backup/recovery, security, accessibility, and performance evidence
- Gather practical feedback from established gasoline and diesel performance shops

### Required before a paid production release

- Production licensing and Owner/team administration
- Trusted Windows code signing and publisher identity
- Privacy, terms, disclaimers, and legal review
- Clean-machine and supported Windows acceptance
- Independent shop testing and owner acceptance
- Final release-package and installer lifecycle approval

### Longer-term possibilities

These are possibilities rather than promises and are outside the immediate release path:

- Optional hybrid or multi-computer synchronization
- Multi-location shop operations
- Customer portals, scheduling, and remote dashboards
- Shared shop presets and templates
- Public plug-in capabilities
- AI-assisted interpretation with strict evidence and safety boundaries
- Calibration context tools

Calibration writing or automatic tune changes are not part of the current approved product scope.

## How status is reported

- **Currently Available** means included in the public download linked above.
- **In Progress** means implemented or actively being refined in private development; it is not necessarily downloadable yet.
- **Potential Next Trial Release** means candidate scope that still requires release approval.
- **Roadmap** means intended direction or possible future work, not a delivery promise.

The [public changelog](CHANGELOG.md) records completed public-facing development work by date. Numbered release sections describe what is actually included in a published package.
