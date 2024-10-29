# Matrix Report for Craft 3/4/5

Version 5.2.0

Sites with large Matrix page-builders can make it difficult to know if and when different Matrix blocks are used. This template will give you a report for every Matrix block on your site. It can be filtered by:

- Matrix field
- Block types for that field
- Section, Category, or Global the block type is used on
- Site block is used on (when more than 1 site exists)
- Entry status of parent entry
- Block status

Any entry, category, or global associated with a Matrix block attached will output in this report.

## Setup

1. Copy the template to your craft templates folder. I prefer to keep a sub-folder called `queries` where I keep utility files like this.
2. Optional: add these environment variables to your .env file to specify your dev, staging, and prod baseUrls. If omitted it will just build links based off of your current environment url.
   - `MATRIX_REPORT_PROD_URL`
   - `MATRIX_REPORT_STAGE_URL`
   - `MATRIX_REPORT_DEV_URL`
3. Login to your control panel. There is a `requirePermission` conditional in the template so you must be logged in with permissions to access the control panel otherwise it will redirect to your front-end login page.
4. Go to the url where you placed the template, for me that is https://localsite.test/queries/blocks

## Gotcha’s

- Sometimes orphan matrix blocks exist on a site even after running `craft utils/prune-orphaned-matrix-blocks`. This will cause this template to output an error that gives the ownerId of the orphan. Take that ID and add it to an env named `MATRIX_REPORT_OWNER_FILTER`. For multiple values separate with a comma. It should look like: `MATRIX_REPORT_OWNER_FILTER=1989,2038`

## TODO

- See if there is a way to provide multi-environment entry urls for multi-site installs (currently it hides the urls in this situation)
- Matrix blocks inside of Neo behave differently and do not output data about the page
