# Modernizing WACS and maintaining applications at Florida DEP

**Role:** Application Systems Programmer, September 2023–April 2026  
**Technologies:** Classic ASP, PHP, CodeIgniter MVC, SQL, PL/SQL, HTML, CSS, JavaScript, Java and Spring

## Application and migration scope

At the Florida Department of Environmental Protection, I translated most of the [WACS application](https://prodapps.dep.state.fl.us/www-wacs/) from Classic ASP to PHP/CodeIgniter MVC. I estimate that my migration work covered roughly 80–90% of the application. This is my retrospective estimate of scope, rather than a measured code or feature count.

The public application includes solid waste facility reports and reference information. The [Solid Waste Facility Inventory Report](https://prodapps.dep.state.fl.us/www-wacs/Solidwastedatasystem/facilityinventoryreport) provides a concrete example of the reporting workflows involved: users can locate facilities or generate lists using district, county and facility-class criteria. Its public form also offers browser or Excel output and selectable report columns. These describe the application's visible capabilities; they do not imply that I independently authored every feature.

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

## Verifying the migration against the legacy application

I compared the migrated application's results directly against the Classic ASP version. I checked the reports visually and exported results to Excel for diff comparisons of the returned data. This let me assess both presentation and data consistency against the existing application, rather than relying on appearance alone.

These comparisons were my approach to checking the migrated reporting behavior. They were not a formal performance benchmark or a claim of exhaustive automated test coverage.

## Outcome and engineering lessons

The migrated workflows provided report-building and report-generation functionality in PHP/CodeIgniter MVC. My contribution included form handling, server-side validation, conditional SQL filtering, query bindings and database procedure work.

This work required understanding existing behavior and expressing it in a different application structure. It also reinforced the distinction between validating input and binding query values: both matter, and neither should be described as a substitute for the other.

I observed substantially faster page responses following migration, but formal before-and-after benchmarks were not collected. I therefore do not claim a measured performance percentage or attribute the observed difference to PHP alone.

## Cleanup Sites: application maintenance and backend reliability

Alongside WACS modernization, I maintained and updated the [DEP Cleanup Sites application](https://prodapps.dep.state.fl.us/dep-clnup/), a separate application written in Java with a Spring backend. Its public interface presents a contamination locator map. This work extended my professional experience beyond PHP/CodeIgniter to maintaining an existing Java/Spring application.

### Repairing site-watch email notifications

The application's "Watch This Site" feature let users subscribe to email notifications when a site entered a different phase. Incorrect exception-handling logic and operation ordering in PL/SQL meant that, if an email field failed validation or could not be loaded, the procedure stopped at that point. Remaining notifications were left unprocessed.

I analyzed an existing PL/SQL package of more than 2,000 lines to understand its processing flow and locate the notification error. I corrected the handling and ordering so that those email-field failures did not stop processing the remaining notifications, and revised exception handling throughout the package.

I also added code to record errors in a database table. A separate procedure used those records to email supervisors a daily error report covering the nightly package run. This gave supervisors a recurring way to see processing errors and gave the team stored error records to investigate.

### Testing the notification and error-reporting changes

I added test data to the local database, ran the stored procedures and compared the results with the expected behavior. This checked the notification fix and the error logging and reporting changes.

For the supervisor report, I created test entries in the error-recording table and checked the resulting email. I also verified that an error recorded by the Watch This Site PL/SQL appeared in the supervisor email, checking the path from procedure-generated error to stored record to report.

The changes were tested locally before progressing through alpha, beta and production servers. Deployment verification and testing took place at each stage before promotion to the next environment.

This work combined debugging inherited database logic, containing individual notification failures and making nightly processing errors visible to supervisors. My contribution was repairing and extending an existing package; I did not write the full package from scratch.

### Adding control over the registry map layer

The Florida Institutional Controls Registry layer was originally always visible. The customer requested a way to turn its visibility on and off using the application's filters beneath the title bar.

The application used an embedded ArcGIS map maintained by the GIS team, so the change required coordination across application boundaries. I collaborated with that team to have them add the necessary functionality to their API. I then used that functionality in the Cleanup Sites application to implement the registry-layer visibility toggle.

The resulting control gave users a choice over whether the registry layer appeared on the map. The GIS team supplied the map API capability; my contribution was coordinating that dependency and integrating it with the application's filter controls. This example shows how I translated a customer request into an application change while working with the team responsible for the embedded map.

## Scope

This account describes my contributions, with public application links provided for context. It contains no employer source code, records, credentials, internal screenshots or system diagrams, and does not imply an employer endorsement. Prepared with AI assistance using implementation details I supplied.
