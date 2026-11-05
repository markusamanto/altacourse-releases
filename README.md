# Altacourses downloads

Versioned Joomla installation packages and the extension update feed.

Installation packages include the new extension's PHP source. Legacy reference files and private development history are not included.

These alpha packages are for an isolated test site running Joomla 6.2 and PHP 8.4. They are not production releases. Alpha5 adds a protected read-only frontend Manage courses overview: administrators see all courses and suppliers see only courses assigned to their Joomla user ID. The public course list supports UGL/UL, region and date filters. Booking, editing and supplier profile management are not yet available.

Download a ZIP from `packages/` and install it through Joomla's extension installer. Checksums are supplied beside each ZIP.

Update-feed address: https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/updates.xml

Install alpha3 manually once to register this feed. Joomla can then offer later versions through its extension updater. Configure the test site to allow alpha releases; production should accept stable releases only.

Latest test version: [Download alpha5](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/com_altacourses-2.0.0-alpha5.zip).

Alpha4 creates six empty course-list tables. It refuses legacy or unknown Altacourses tables; this is not a production-data migration. Update the installed component without uninstalling. Sample loading is off by default, requires course-administrator permission and a valid protected form, and only works when all six tables are empty. It sends no mail and creates no users.

Alpha5 preserves the six alpha4 tables and existing ownership assignments. The original synthetic sample courses remain unassigned, so supplier accounts initially have an empty management list. No user accounts or assignments are created by this update.
