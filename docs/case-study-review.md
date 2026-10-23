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

## Metrics and attribution

Formal performance benchmarks were not collected. Keep numerical speed improvements out of outcome claims. The narrative labels faster responses as an observation, without assigning the cause to PHP alone. The author has now explicitly supplied an approximate 80–90% migration scope; the case study labels it as a retrospective estimate, not a measured code or feature count. The profile uses "most" to keep its summary concise.

The general database-loading account retains "worked on" because ownership of those procedures is not established. The Cleanup Sites example now identifies confirmed work repairing and extending an inherited package, including error logging and daily reporting. Do not imply sole authorship of the full package, a specific root cause, a measured notification success rate or complete per-email fault isolation.

## Optional detail for a future revision

The case study now includes concrete migration verification, map integration and database notification examples. Further detail is optional. Do not invent validation rules, testing processes, incident reductions or business metrics. The exact notification root cause and the method used to verify the package fix have not been supplied.

The public WACS form establishes available search, output and column options, not individual feature authorship. Specific ownership of Excel output, optional column selection and each search mode has not been established. This does not prevent publication of the case study's confirmed migration, verification and map-integration examples. Do not infer that the registry toggle required changes to Java/Spring backend code or that the author implemented the GIS team's API.

## Resume bullets based on confirmed details

- Migrated legacy Classic ASP report-builder pages and generated reports to PHP/CodeIgniter MVC, implementing forms and server-side input validation.
- Constructed dynamic SQL filters from user-entered report criteria and used query bindings to mitigate SQL injection risks.
- Worked on PL/SQL stored procedures supporting daily database loads, error-report generation and email notifications.
- Verified migrated reports against Classic ASP output using visual comparisons and Excel-based data diffs.
- Collaborated with the GIS team to integrate an ArcGIS API capability and add a customer-requested registry-layer visibility toggle to the DEP Cleanup Sites application.
- Diagnosed and repaired site-watch email notification failures in an inherited database package of more than 2,000 lines; improved exception handling and added database error logging with daily supervisor email reports.
