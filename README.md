# Altacourses downloads

Versioned Joomla installation packages and the extension update feed.

Installation packages include the new extension's PHP source. Legacy reference files and private development history are not included.

These alpha packages are for an isolated test site running Joomla 6.2 and PHP 8.4. They are not production releases. Alpha6 adds protected availability editing: administrators can update any course; suppliers can update only their own upcoming courses. Stale forms and concurrent overwrites are rejected. The public course list supports UGL/UL, region and date filters. Full course editing, booking and supplier profile management are not yet available.

Download a ZIP from `packages/` and install it through Joomla's extension installer. Checksums are supplied beside each ZIP.

Update-feed address: https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/updates.xml

Install alpha3 manually once to register this feed. Joomla can then offer later versions through its extension updater. Configure the test site to allow alpha releases; production should accept stable releases only.

Latest test version: [Download alpha10](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/com_altacourses-2.0.0-alpha10.zip).

Alpha4 creates six empty course-list tables. It refuses legacy or unknown Altacourses tables; this is not a production-data migration. Update the installed component without uninstalling. Sample loading is off by default, requires course-administrator permission and a valid protected form, and only works when all six tables are empty. It sends no mail and creates no users.

Alpha5 preserves the six alpha4 tables and existing ownership assignments. The original synthetic sample courses remain unassigned, so supplier accounts initially have an empty management list. No user accounts or assignments are created by this update.

Alpha6 adds an availability revision counter through schema migration 2.0.1. Existing records and relationships remain intact. There are no delete, trash or purge actions. No mail or external integrations are invoked. Update without uninstalling; older packages cannot be used to downgrade this schema.

Alpha7 adds administrator-only supplier assignment to active Joomla accounts with supplier permission. Assignment updates invalidate older availability forms, and removing assignment retains the course. No supplier profiles, mail, external integrations or additional schema migrations are included.

Alpha8 adds additional-session storage and displays all date ranges in public and protected course lists. Date-to filtering uses the final session end; date-from uses the original first start. Location and leaders remain shared. Schema 2.0.2 adds one linked table without changing existing course dates. An opt-in protected fixture action extends the two UL synthetic samples. Course-creation/session-editing forms are not included yet.

Alpha9 adds frontend course creation: administrators select the supplier in the form; suppliers create courses assigned to themselves. One or two sessions, required core fields, retained values on validation errors and immediate publication are supported. Schema 2.0.3 adds a unique nullable creation-submission key to prevent duplicate saves. Existing records remain unchanged. Full course editing and bookings are still forthcoming.

Alpha10 simplifies the Swedish supplier label to Arrangör and defaults new-course availability to 3+. Submitted or explicitly provided availability values are retained. No schema or existing record changes.
