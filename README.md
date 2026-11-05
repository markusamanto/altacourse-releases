# Altacourses downloads

Versioned Joomla installation packages and the extension update feed.

Installation packages include the new extension's PHP source. Legacy reference files and private development history are not included.

These alpha packages are for an isolated test site running Joomla 6.2 and PHP 8.4. They are not production releases. Alpha4 adds a read-only public course list with UGL/UL, region and date filters, and optional protected synthetic sample loading. Booking, editing and supplier ownership workflows are not yet available.

Download a ZIP from `packages/` and install it through Joomla's extension installer. Checksums are supplied beside each ZIP.

Update-feed address: https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/updates.xml

Install alpha3 manually once to register this feed. Joomla can then offer later versions through its extension updater. Configure the test site to allow alpha releases; production should accept stable releases only.

Latest test version: [Download alpha4](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/com_altacourses-2.0.0-alpha4.zip).

Alpha4 creates six empty course-list tables. It refuses legacy or unknown Altacourses tables; this is not a production-data migration. Update the installed component without uninstalling. Sample loading is off by default, requires course-administrator permission and a valid protected form, and only works when all six tables are empty. It sends no mail and creates no users.
