# Altacourses downloads

Versioned Joomla installation packages and the extension update feed.

Installation packages include the new extension's PHP source. Legacy reference files and private development history are not included.

These alpha packages are for an isolated test site running Joomla 6.2 and PHP 8.4. They are not production releases. The current package provides read-only frontend entry pages; course and booking functions are not yet available.

Download a ZIP from `packages/` and install it through Joomla's extension installer. Checksums are supplied beside each ZIP.

Update-feed address: https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/updates.xml

Alpha2 does not yet register this feed automatically. A subsequent bootstrap package will register it; Joomla's extension updater must then be configured to allow alpha releases on the test site. Production should accept stable releases only.
