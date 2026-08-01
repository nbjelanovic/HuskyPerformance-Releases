# Changelog

All notable public-facing changes to Husky Performance are recorded here.

For a plain-language overview, start with [Project Status](PROJECT-STATUS.md).

Husky Performance is still pre-release software. Entries under **Unreleased** describe work completed for a future preview but not yet included in the current public download. A change moves into a numbered release only after its package has been built and validated.

Unreleased entries are grouped by completion date, newest first.

## [Unreleased]

### 2026-08-01

#### Added

- Added consecutive local road-video selection for camera recordings split across multiple MP4/MOV chapters. Simulator orders selected files consistently, treats decoded chapter durations as one continuous video timeline, advances automatically at each boundary, and retains the same log offset and playback state. Single-file selection remains supported, and footage remains reference-only and local.

- Added the first synchronized local road-video mode to Simulator playback. An optional MP4 or MOV can now replace the synthetic scenery while the stable cockpit gauges and evidence-based overlays remain on top; play, pause, timeline seeking, playback speed, and a manual log offset stay synchronized. Video remains reference-only and local—nothing is uploaded. Multi-chapter footage, attachment persistence, codec validation, and owner visual acceptance remain open work.

- Added streaming import support for Car Scanner Pro semicolon-delimited long CSV exports (`SECONDS`, `PID`, `VALUE`, and `UNITS`). Asynchronous PID measurements are normalized to a deterministic 10 Hz review timeline while preserving the existing positional CSV path.

#### Improved

- Added a tightly bounded Simulator video-rate correction beside the log offset. Small camera/proxy clock differences can now be compensated from 0.95× through 1.05× without changing the recorded log timeline or exact gauge samples, and the applied six-decimal rate is disclosed. The supplied GoPro proxy set's evidence-based starting value is approximately `0.998364`.

- Added automatic local GoPro proxy fallback when Windows cannot decode a selected high-frame-rate camera original. Husky keeps the MP4 as the authoritative source, locates its matching `GL...LRV` sidecar, creates an isolated temporary `.mp4` playback proxy, and retries on the same synchronized timeline. Originals remain unchanged and nothing is uploaded. Native Windows probing confirmed that all three supplied 768×432 proxies open successfully; the 119.88-fps original is rejected by the current Windows WPF codec stack.

- Kept the Simulator responsive while a large local road-video file is verified. Reference-only identity work now runs away from the interface thread; playback waits for Windows to confirm that the codec opened, reports decoded dimensions, and safely restores generated scenery with a clear error when decoding fails. The file remains local and nothing is uploaded.

- Corrected arcade-like road markers exposed by native Simulator screenshots. Highway edge motion is now faint neutral gray, Brake Test uses subdued safety orange, and alternating red/white markers remain scoped to Drag Strip; peripheral-flow emphasis scales each scenario's intended opacity instead of brightening suppressed markers. A fresh six-screenshot review and the complete 26-assertion native scenario workflow pass.
- Added slow, bounded lane-and-shoulder width evolution to Simulator playback. Road-edge convergence now varies gently by integrated distance and scenario while cockpit geometry stays fixed; Drag Strip remains nearly uniform, Highway and Brake Test remain restrained, Closed Test Road receives more natural variation, and stationary playback returns to the exact baseline.
- Smoothed Simulator road evolution across evidence-detected scenario boundaries. Curvature, elevation, pavement texture, peripheral flow, and roadside density now blend through the photographic environment's 550-ms transition instead of snapping at one recorded sample; the blend remains deterministic during pause, seek, replay, and manual environment overrides.
- Added restrained, distance-synchronized pavement texture and scenario-specific roadside variation to Simulator playback. The subtle perspective layer follows the existing bounded curve and elevation model, remains subdued on Highway and Drag Strip, and disappears completely during stationary or unknown playback.
- Added bounded, distance-driven road evolution to Simulator playback. Scenario-specific bends, gentle elevation changes, and restrained peripheral flow now follow recorded speed and integrated visual distance while the cockpit and gauges remain stable. Drag Strip stays nearly straight, Stationary/unknown playback stays exactly still, and all visual movement remains tightly bounded.
- Limited whole-session Simulator playback to 10 recorded minutes or 250,000 samples. Five-minute segments are recommended for focused pulls, braking tests, and other events. Extended logs remain importable and reviewable, but Simulator rejects them before loading channel arrays and directs the operator to create a bounded segment.

#### Validation

- Imported the complete owner-supplied 219,636,786-byte Armada log containing 3,136,309 source measurements into 187,881 review samples across 66 numeric channels. It archived into the encrypted test library and reopened through the production log-review service; recorded vehicle speed ranged from 0 to 103.15 mph.
- The full development solution builds with zero warnings and errors, and all 111 foundation checks pass. These Unreleased changes are not included in public version 0.8.99.

### 2026-07-31

#### Added

- Added evidence-driven photographic Simulator environments for Highway, Drag Strip, Brake Test, Garage/Paddock, and a neutral closed test road. Auto mode classifies bounded recorded segments instead of treating every log as a race-track session.
- Added recorded-event overlays for qualified drag-tree staging and finish markers, the optional brake-test cow, and the optional non-drag 100+ mph “Welcome to Mexico” sign. Humor remains off by default and never changes recorded evidence.
- Added native end-to-end validation using owner-supplied real logs and isolated drag, brake, highway, and mixed-session fixtures.

#### Improved

- Synchronized scenery, scenario transitions, drag timing, finish distance, brake-stop behavior, road motion, and subtle cockpit body response to the recorded playback timeline while keeping gauges on exact saved samples.
- Corrected packaged cockpit resources, initial Track View rendering, full-screen compact gauge placement, per-segment drag/highway scope, and cross-scenario overlay cleanup.

#### Validation

- Real-log import, saved review, scenario detection, native overlay workflows, full-screen behavior, and zero-warning builds passed their recorded checkpoints. Packaged owner visual acceptance remains a separate open gate.
- None of the July 31 Unreleased work is included in public version 0.8.99.

### 2026-07-30

#### Added

- Added a dedicated Log Simulator workspace in private development. It replays exact samples from a saved log on their original recorded timeline with play, pause, explicit Stop/reset, restart, timeline scrubbing, and 0.25x through 4x playback.
- Added editable virtual dashboards with up to eight available numeric channels, common channel presets, per-gauge Analog, Dial, Digital, LED Ring, or Bar presentation, Small/Medium/Large sizing, optional recorded Min/Max values, a snapping alignment grid, and per-log layout persistence.
- Added qualified 0–60 mph, 0–100 mph, 1/8-mile, 1/4-mile, custom acceleration, and braking calculations. Results remain unavailable unless the selected log contains the required speed, RPM, throttle, time-continuity, starting-condition, and uninterrupted-run evidence.
- Added a public [Project Status](PROJECT-STATUS.md) page that clearly separates Currently Available, In Progress, Potential Next Trial Release, and Roadmap information.

#### Improved

- Reworked Simulator gauges with original Husky instrument artwork: layered bezels, recessed faces, detailed major/minor scales, numeric scale labels, tapered needles, dimensional hubs, high-contrast digital windows, and a progressive 24-segment LED-ring presentation.
- Improved Simulator full-screen ownership and exit behavior. Full screen now provides a visible exit action, supports Escape, removes the redundant nested Full Screen action, and closes with the main application.
- Added Essentials, Engine Performance, Fuel and Air, Temperatures, Wheel and Chassis, and Clear All gauge presets that select only compatible channels recorded in the current log and preserve the eight-gauge readability limit.
- Improved the high-channel-count editor with search, a wider control area, usable vertical scrolling, disabled horizontal overflow, and unclipped style, size, and Min/Max controls.
- Added explicit Edit Dashboard and Close Editor states, automatic per-log layout saving, movable gauges, and a movable or hideable performance panel. Playback locks layout changes.
- Added complete Simulator help and English, Spanish, German, and Russian interface coverage.

#### Safety and limitations

- Simulator visual bands and LED colors represent position within a channel's finite recorded range. They are not calibrated warning limits or vehicle-safety thresholds.
- Simulator performance values are analysis aids, not certified track timing, automatic diagnosis, tuning instructions, or machine-control decisions.
- An experimental inside-car/track visualization exists in private development but is not considered presentation-ready and is not approved for promotional screenshots. Gauge-dashboard quality remains the priority.
- None of the July 30 Unreleased work is included in public version 0.8.99 merely because it appears here.

#### Validation

- Current private-development Release builds complete with zero build warnings and zero build errors.
- Coordinated native Windows testing passes Simulator playback, Stop/reset, presets, independent gauge choices, layout persistence, edit locking, full-screen exit, main-window shutdown, selected-log handoff, malformed-preference recovery, and qualified performance disclosure.
- Spanish literal-interface coverage is complete for the current development surface, and the German and Russian catalogs pass their current automated coverage and placeholder checks.
- Package, installer, clean-machine, Windows 10/11, signing, licensing, legal, owner, and independent-shop acceptance remain separate release gates.

### 2026-07-29

#### Improved

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

#### Fixed

- Corrected additional English fallback text that could appear while using German or Russian.
- Improved consistency of localized dynamic labels and vehicle states.

#### Validation

- Verified an isolated PrivatePreview build still visibly identifies itself as `DEVELOPMENT LICENSE • PROFESSIONAL • SIMULATION` when the retired Personal override is deliberately set, while retaining its Preview label and backup-before-use warning.
- Replaced the obsolete Personal-owner validation path with coordinated checks for the three supported Professional business profiles.
- Verified that the private registry accepts Professional business registration and rejects attempted Personal issuance at its service boundary.
- Verified the language catalog, catalog-generated shell/Settings/Guided Setup choices, CSV export, English fallback, and numbered-placeholder safety.
- Verified real Guided Setup behavior for the Business / Shop identity label, Professional Open Shop default, all five setup steps, revisiting, safe Quick Setup, Skip for now, and deferred re-prompt.
- Verified Professional business-profile selection, safety preview, immutable audit history, restart persistence, reversible switching, dashboard summary-card and Quick Launch priority, unchanged full navigation, profile-specific report starting points, retained access to every report template, preservation of a user's report-template choice during refresh, profile-specific Guided Setup instructions, and safe fallback for unknown or retired profile IDs.
- Verified the vehicle-history data contract and compatibility with supported libraries that do not yet contain injector-session detail tables.
- Expanded automated localization checks to protect German and Russian coverage from regression.

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
