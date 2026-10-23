# Case study review notes

## Details confirmed by the author

- The author estimates translating roughly 80–90% of the entire WACS application from Classic ASP to PHP/CodeIgniter MVC.
- The author maintained and updated the separate DEP Cleanup Sites application, written in Java with a Spring backend.
- Migration verification included visual comparisons against Classic ASP results and Excel exports used for data diff comparisons.
- The customer requested a visibility toggle for the previously always-visible Florida Institutional Controls Registry map layer.
- The GIS team maintained the embedded ArcGIS map and added the necessary API functionality; the author coordinated with them and integrated the capability into the application's filters beneath the title bar.
- Reporting pages paired a criteria-entry form with a generated report.
- The author received and validated submitted fields and constructed SQL with conditional filters.
- User-entered query values were passed through query bindings to mitigate SQL injection risks.
- The author also worked on PL/SQL stored procedures for daily database loads, error reports and email notifications.
- For Cleanup Sites' "Watch This Site" subscriptions, notification errors could fail the entire procedure. The author analyzed an existing database package of more than 2,000 lines, corrected the notification error and revised exception handling across the package.
- The author added database-table error logging and a separate procedure that emailed supervisors daily error reports from the nightly package run.
- The notification root cause was incorrect PL/SQL exception-handling logic and operation ordering: failure to validate or load one email field stopped the procedure before remaining notifications were processed. The fix allowed processing to continue for those failures.
- Local verification used database test data, direct stored-procedure execution and comparisons with expected results. Supervisor reporting was checked with manually inserted error records and a Watch This Site error recorded through PL/SQL, confirming inclusion in the supervisor email.
- Changes progressed from local testing through alpha, beta and production, with deployment verification and testing before each promotion.

## Metrics and attribution

Formal performance benchmarks were not collected. Keep numerical speed improvements out of outcome claims. The narrative labels faster responses as an observation, without assigning the cause to PHP alone. The author has now explicitly supplied an approximate 80–90% migration scope; the case study labels it as a retrospective estimate, not a measured code or feature count. The profile uses "most" to keep its summary concise.

The general database-loading account retains "worked on" because ownership of those procedures is not established. The Cleanup Sites example identifies confirmed work repairing and extending an inherited package, including the root cause, continuation after email-field failures, error logging, daily reporting and staged verification. Do not imply sole authorship of the full package, a measured notification success rate or isolation of every possible failure.

## Optional detail for a future revision

The case study now includes concrete migration verification, map integration, notification diagnosis, database tests and staged deployment verification. Further detail is optional. Do not invent specific exception names, tools used for comparisons, automated test coverage, incident reductions or business metrics.

The public WACS form establishes available search, output and column options, not individual feature authorship. Specific ownership of Excel output, optional column selection and each search mode has not been established. This does not prevent publication of the case study's confirmed migration, verification and map-integration examples. Do not infer that the registry toggle required changes to Java/Spring backend code or that the author implemented the GIS team's API.

## Resume bullets based on confirmed details

- Migrated legacy Classic ASP report-builder pages and generated reports to PHP/CodeIgniter MVC, implementing forms and server-side input validation.
- Constructed dynamic SQL filters from user-entered report criteria and used query bindings to mitigate SQL injection risks.
- Worked on PL/SQL stored procedures supporting daily database loads, error-report generation and email notifications.
- Verified migrated reports against Classic ASP output using visual comparisons and Excel-based data diffs.
- Collaborated with the GIS team to integrate an ArcGIS API capability and add a customer-requested registry-layer visibility toggle to the DEP Cleanup Sites application.
- Diagnosed and repaired site-watch email notification failures in an inherited database package of more than 2,000 lines; improved exception handling and added database error logging with daily supervisor email reports.
