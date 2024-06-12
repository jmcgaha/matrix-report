# Matrix Report for Craft 3/4
Version 4.0.0

On sites with large matrix page-builders it can be difficult to know if and when different blocks are used. This template will give you a report for every Matrix block on your site. It can be filtered by:
- Matrix field
- Block types for that field
- Site block is used on (when more than 1 site exists)
- Entry status of parent entry
- Block status

## Setup
1. Copy the template to your craft templates folder. I prefer to keep a folder there called `queries` where I like to keep files like this.
2. Add these environment variables to your .env file to specify your dev, staging, and prod baseUrls.
    - `MATRIX_REPORT_PROD_URL`
    - `MATRIX_REPORT_STAGE_URL`
    - `MATRIX_REPORT_DEV_URL`
3. Login to your control panel as an admin. There is a `requireAdmin` conditional in the template so you must be an admin and logged in otherwise it will redirect to your front-end login page.
4. Go to the url where you placed the template, for me that is https://localsite.test/queries/blocks

## TODO
- Develop a version for Craft 5
- See if there is a way to provide multi-environment entry urls for multi-site installs (currently it hides the urls in this situation)