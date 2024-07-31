# Matrix Report for Craft 3/4/5
Version 5.0.0

On sites with large matrix page-builders it can be difficult to know if and when different blocks are used. This template will give you a report for every Matrix block on your site. It can be filtered by:
- Matrix field
- Block types for that field
- Site block is used on (when more than 1 site exists)
- Entry status of parent entry
- Block status
Any entry, category, or global associated with a Matrix block assigned to it will output in this report.

## Setup
1. Copy the template to your craft templates folder. I prefer to keep a folder there called `queries` where I like to keep files like this.
2. Add these environment variables to your .env file to specify your dev, staging, and prod baseUrls.
    - `MATRIX_REPORT_PROD_URL`
    - `MATRIX_REPORT_STAGE_URL`
    - `MATRIX_REPORT_DEV_URL`
3. Login to your control panel as an admin. There is a `requireAdmin` conditional in the template so you must be an admin and logged in otherwise it will redirect to your front-end login page.
4. Go to the url where you placed the template, for me that is https://localsite.test/queries/blocks

## Gotcha’s
- Sometimes orphan matrix blocks exist on a site even after running `craft utils/prune-orphaned-matrix-blocks` and this will cause this template to error that gives the ownerId of the orphan. Add that ID to an env named `MATRIX_REPORT_OWNER_FILTER`. For multiple values separate with a comma. It should look like: `MATRIX_REPORT_OWNER_FILTER=1989,2038`

## TODO
- See if there is a way to provide multi-environment entry urls for multi-site installs (currently it hides the urls in this situation)
- Matrix blocks inside of Neo behave differently and do not output data about the page
