# Modernizing WACS and maintaining applications at Florida DEP

**Role:** Application Systems Programmer, September 2023–April 2026  
**Technologies:** Classic ASP, PHP, CodeIgniter MVC, SQL, PL/SQL, HTML, CSS, JavaScript, Java and Spring

## Migrating WACS from Classic ASP

At the Florida Department of Environmental Protection, I migrated most of the [WACS application](https://prodapps.dep.state.fl.us/www-wacs/) from Classic ASP to PHP/CodeIgniter MVC. I estimate that I translated roughly 80–90% of the application.

WACS includes solid waste facility reports and reference information. The [Solid Waste Facility Inventory Report](https://prodapps.dep.state.fl.us/www-wacs/Solidwastedatasystem/facilityinventoryreport) is one example: users can search for facilities or build reports using district, county and facility-class criteria. The application also offers browser and Excel output with selectable report columns.

My job was to understand the existing ASP behavior and carry it over to the new application. I implemented report-builder forms, validated submitted values on the server and built SQL filters based on the criteria entered. I used query bindings to keep user-entered values separate from the SQL text.

I compared the migrated reports directly against the ASP results. I checked them visually and exported results to Excel for data diffs. That helped me check both how the reports looked and whether they returned the expected data.

I also worked on PL/SQL stored procedures supporting daily database loads, error reports and email notifications.

The migrated pages felt substantially faster, but I did not collect formal before-and-after benchmarks. The 80–90% figure is my estimate of the migration scope, not a measured code or feature count.

## Maintaining DEP Cleanup Sites

I also maintained and updated the [DEP Cleanup Sites application](https://prodapps.dep.state.fl.us/dep-clnup/), which was written in Java with a Spring backend. My work included fixing database notification processing and adding a map-layer control in collaboration with the GIS team.

### Fixing Watch This Site notifications

The application's "Watch This Site" feature let users sign up for email notifications when a site entered a different phase. When I worked on it, a failure to validate or load one email field could stop the entire procedure, leaving the rest of the notifications unprocessed.

I went through the existing PL/SQL package, which was over 2,000 lines, to understand how it worked and find the cause. The problem was in the exception-handling logic and order of operations. I corrected that logic so those email-field failures would not stop the remaining notifications from being processed. I also revised exception handling throughout the package.

While working on the fix, I added code to record errors in a database table. A separate procedure used those records to email supervisors a daily report of errors from the nightly package run. This gave the team a record of failures to investigate and a regular report to review.

### Testing and deployment

I added test data to my local database, ran the stored procedures and compared the results with what I expected. I tested the notification fix and the error logging and reporting this way.

For the supervisor report, I created test entries in the error-recording table and checked that they appeared in the email. I also checked that an error recorded by the Watch This Site PL/SQL made it into the supervisor email, so I could verify the logging and reporting together.

After local testing, the changes moved through alpha, beta and production. I verified the deployment and tested the changes in each environment before they moved to the next one.

### Adding the registry-layer toggle

The Florida Institutional Controls Registry layer was originally always visible on the map. The customer wanted a way to turn it on and off through the filters beneath the title bar.

The application used an embedded ArcGIS map maintained by the GIS team. I worked with them to get the required functionality added to their API, then used it in the Cleanup Sites application to control the layer's visibility. The GIS team implemented the map API change, and I integrated it with the application's filter controls.

## What I took from the work

These projects involved understanding existing systems before changing them. For WACS, I used the ASP reports as a reference and compared the data as well as the presentation. For Cleanup Sites, I traced a failure through a large database package, corrected the processing behavior and added reporting so errors would be easier to investigate.

The map update also required working with another team: I could implement the application controls, but the embedded map needed an API change from the people who maintained it.

This case study describes my work at a high level. I have included public application links, without employer source code, internal records or screenshots. It does not imply an endorsement by Florida DEP.
