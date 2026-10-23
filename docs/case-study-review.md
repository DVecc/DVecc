# Case study review notes

## Details confirmed by the author

- The author estimates translating roughly 80–90% of the entire WACS application from Classic ASP to PHP/CodeIgniter MVC.
- The author maintained and updated the separate DEP Cleanup Sites application, written in Java with a Spring backend.
- Reporting pages paired a criteria-entry form with a generated report.
- The author received and validated submitted fields and constructed SQL with conditional filters.
- User-entered query values were passed through query bindings to mitigate SQL injection risks.
- The author also worked on PL/SQL stored procedures for daily database loads, error reports and email notifications.

## Metrics and attribution

Formal performance benchmarks were not collected. Keep numerical speed improvements out of outcome claims. The narrative labels faster responses as an observation, without assigning the cause to PHP alone. The author has now explicitly supplied an approximate 80–90% migration scope; the case study labels it as a retrospective estimate, not a measured code or feature count. The profile uses "most" to keep its summary concise.

The PL/SQL wording deliberately says "worked on" rather than claiming sole authorship or distinguishing new procedures from maintenance. Refine that only when the author's exact contribution is established.

## Optional detail for a future revision

A specific non-confidential filter example or database-load issue could add depth. Do not invent validation rules, stored-procedure ownership, testing processes, incident reductions or business metrics.

The public WACS form establishes available search, output and column options, not individual feature authorship. Specific ownership of Excel output, optional column selection and each search mode has not been established. Specific Java/Spring maintenance examples and the migration verification process also remain to be described by the author.

## Resume bullets based on confirmed details

- Migrated legacy Classic ASP report-builder pages and generated reports to PHP/CodeIgniter MVC, implementing forms and server-side input validation.
- Constructed dynamic SQL filters from user-entered report criteria and used query bindings to mitigate SQL injection risks.
- Worked on PL/SQL stored procedures supporting daily database loads, error-report generation and email notifications.
