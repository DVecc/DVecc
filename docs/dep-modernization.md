# Modernizing reporting workflows at Florida DEP

**Role:** Application Systems Programmer, September 2023–April 2026  
**Technologies:** Classic ASP, PHP, CodeIgniter MVC, SQL, PL/SQL, HTML, CSS and JavaScript

## The reporting workflow

At the Florida Department of Environmental Protection, I worked on applications where users entered criteria into a report-builder page and received a generated report matching those criteria. The pages shared a common pattern, but the query needed to account for the values a user supplied.

My modernization work involved migrating these reporting workflows from Classic ASP to PHP/CodeIgniter MVC while maintaining their existing purpose and behavior.

## My contribution

I implemented report-builder forms, received and validated submitted values on the server, and constructed SQL queries with different filters according to the user's criteria. The application then used the query results to generate the requested report.

I used query bindings for user-entered values to mitigate SQL injection risks. Conditional SQL determined which filters applied; the values for those filters were passed separately through bindings rather than inserted directly into the SQL text. Input validation and bound parameters addressed different concerns: checking submitted values and keeping those values separate from SQL syntax.

The reporting workflow can be summarized as:

1. A user enters report criteria into text fields.
2. The server receives and validates the submitted values.
3. The application constructs the appropriate SQL filters and supplies values through query bindings.
4. The application queries the database and generates the matching report.

## Database loading and operational reporting

I also worked on PL/SQL stored procedures supporting daily database loads, error-report generation and email notifications. This was separate from constructing the conditional SQL for the interactive report-builder pages.

That work gave me experience with both the user-facing reporting application and the database processes supporting recurring operations.

## Outcome and engineering lessons

The migrated workflows provided report-building and report-generation functionality in PHP/CodeIgniter MVC. My contribution included form handling, server-side validation, conditional SQL filtering, query bindings and database procedure work.

This work required understanding existing behavior and expressing it in a different application structure. It also reinforced the distinction between validating input and binding query values: both matter, and neither should be described as a substitute for the other.

I observed substantially faster page responses following migration, but formal before-and-after benchmarks were not collected. I therefore do not claim a measured performance percentage or attribute the observed difference to PHP alone.

## Scope

This account describes my reported contributions. It contains no employer source code, records, credentials, internal screenshots or system diagrams, and does not imply an employer endorsement. Prepared with AI assistance and updated with implementation details I supplied for review.
