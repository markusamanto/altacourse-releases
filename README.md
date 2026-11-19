# Altacourses Beta2

Update the component first, then the three changed modules. Do not uninstall. Back up your files/database first. The task plugin, editable letter and evaluations module remain at Beta1.

| Package | Download |
|---|---|
| Component | [com_altacourses 2.0.0-beta2](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/com_altacourses-2.0.0-beta2.zip) |
| Course details | [mod_altacoursedetails 2.0.0-beta2](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altacoursedetails-2.0.0-beta2.zip) |
| Related courses | [mod_altarelatedcourses 2.0.0-beta2](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altarelatedcourses-2.0.0-beta2.zip) |
| Compact courses | [mod_altacourses 2.0.0-beta2](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altacourses-2.0.0-beta2.zip) |

In component Options → **Prisvisning**, choose **Variabelt kurspris (V)** for mixed Internat/Externat courses. **Totalpris (T)** remains the default. All existing/new courses default to Internat; edit non-residential courses to Externat using the new dropdown below the room/board checkbox. Price arithmetic remains unchanged. Schema2.0.28 adds the residential field automatically; no manual SQL import is required.

Variable-mode listings show matching superscript1/2 inclusion notes. Individual information/signup/email details show the applicable description. Saved historical submissions/messages stay unchanged. Super Users are excluded from supplier lists/choices. Both welcome pages now rely on your Joomla menus; administrator statistics and controls remain.

Compact module: **Visa knappen till fler kurser** defaults Yes. Course-details module: **Visa kurstyp** defaults No, with improved Övrigt/VAT spacing. Related-course tables are striped in both modes. Update the component before these three modules.

All four packages have native Joomla update feeds. Allow Beta minimum extension stability for Live Update; manual uploads do not require that global change. Other integrations/delivery settings are retained; updating never enables sending automatically. No hosted installation is performed by publishing these downloads.

---

# Fresh-install setup (original Beta1 guide; use current packages above)

The user has chosen to back up advenire.se and install directly, without staging. Hosting is HostUp, with user-reported Joomla 6.2 / PHP 8.4 and the same specifications as the existing test site. Local verification uses Joomla 6.2 / PHP 8.4 / MySQL 8.4; no connection to advenire.se has been made. This is a fresh UL-only installation, not a legacy migration.

## Fresh-install downloads and installation order

Download and install through **System → Install → Extensions → Upload Package File**. Install the component first; then the task plugin and whichever modules you will use. Do not uninstall to update an existing rebuild installation.

| Package | Download |
|---|---|
| Component | [com_altacourses 2.0.0-beta2](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/com_altacourses-2.0.0-beta2.zip) |
| Scheduled tasks | [plg_task_altacoursesmonthly 2.0.1-beta1](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/plg_task_altacoursesmonthly-2.0.1-beta1.zip) |
| Course details beside linked articles | [mod_altacoursedetails](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altacoursedetails-2.0.0-beta2.zip) |
| Upcoming courses for a leader/place article | [mod_altarelatedcourses](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altarelatedcourses-2.0.0-beta2.zip) |
| Editable letter with dynamic count | [mod_altacoursesletter](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altacoursesletter-2.0.0-beta1.zip) |
| Published evaluations | [mod_altaevaluations](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altaevaluations-2.0.0-beta1.zip) |
| Compact upcoming-course list | [mod_altacourses](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altacourses-2.0.0-beta2.zip) |

The details, related and compact modules are 2.0.0-beta2; the letter and evaluations modules remain 2.0.0-beta1. The plugin's 2.0.1 version preserves its existing version sequence. The Beta2 addons require the Beta2 component; remaining addons support Beta1 or newer. These are separate installation ZIPs, not a single Joomla package bundle. Existing versioned Alpha downloads remain available unchanged.

1. Take the full site/files/database backup you planned and retain the restore instructions.
2. Install the component. Check **System → Maintenance → Database**; the schema is 2.0.28. No manual SQL import or test database copy is required.
3. Install the selected addons. Newly created module instances are unpublished. Set their titles, positions, menu assignments and individual options before publishing them. Use two instances of Related Courses if both leader and place modes are needed.
4. Keep sample-data loading disabled. Email modes and Mailchimp/Zenler delivery default to Disabled; installing packages does not create scheduled tasks or enable delivery.

## Initial configuration

Open component Options in the backend. Set the site language, article categories for course leaders/places and **multiple course types = No** for this UL site. Review statistics commission/goal settings if using them. For frontend administration use your Joomla account with component management permission (Super Users already qualify). Supplier accounts require the separate supplier permission and a matching supplier record linked to their Joomla user; do not grant backend administration merely to enable supplier access.

Frontend administrator entry: `/index.php?option=com_altacourses&view=dashboard`.
Public course listing: `/index.php?option=com_altacourses&view=courses`.
Create suitable Joomla menu items for these routes as required by the site's navigation.

Before creating courses, open **Platsindikeringar** from the administrator dashboard and add/publish these four entries. The numeric value is a status code, separate from the database record ID:

| Value | Suggested label |
|---|---|
| 1 | 3+ |
| 2 | Fullbokat |
| 3 | Få |
| 4 | Inställd |

Create the UL course type, regions, course places, leaders and suppliers with their booking terms. Select this site's article references and existing images where appropriate. Then create course occasions, dates/sessions, prices, ownership and availability. Do not load synthetic sample data as a shortcut.

Review all outgoing mail templates, public wording and module text for UL/advenire branding. Only the editable type 12 introduction is initially seeded; create the required mail templates before enabling the corresponding email functions. Configure the evaluation thank-you Custom module and public evaluation URL if using evaluations. Article/module/category IDs from another site do not identify the same content here.

## Controlled acceptance and delivery

First test anonymous listing/information, signup and enquiry, administrator/client editing, supplier ownership/access, availability, participation/rebooking, commissions and whichever public modules are published. Use clearly identified test contacts. With delivery Disabled, messages can be recorded without being sent.

Configure reCAPTCHA v2 checkbox keys for advenire.se and explicitly enable protection. Check missing/expired challenges and successful submission. Frontend scripts and verification use recaptcha.net.

When ready for controlled delivery tests, configure Joomla SMTP and sender details and select Sandbox or Production separately for notifications, reminders, evaluation invitations and monthly reports. Production requires authenticated SMTP with TLS and Joomla Send Mail enabled. SMTP changes alone do not enable delivery. Previously queued Disabled/Sandbox messages retain their original provenance and require explicit reviewed production approval; changing modes never releases the old queue automatically. Production delivery retains per-message review and sandbox protections.

Leave the UGL-only Mailchimp series disabled for this UL site. Zenler newsletter delivery is separate: configure an appropriate funnel/account or leave it disabled; do not assume the UGL newsletter funnel is suitable for advenire.se.

Enable the task plugin and create only the Joomla Scheduled Tasks you want, after checking their configuration and controlled recipients. The CPanel cron invokes Joomla's scheduler, which runs the plugin routines. No external FastCron job is needed for these new routines. Monthly reminders are due on the 20th at/after 09:00 Stockholm time; daily/hourly scheduler polling must actually run, and UTC execution settings must account for daylight saving. Review each routine's setup, delivery mode and results before relying on it.

## Updates and launch

Manual upload installs Beta1 without changing Joomla's minimum extension stability. Future Beta Live Updates require Joomla's minimum extension stability to allow Beta; that global setting also affects other extensions. Stable-only sites will not discover prereleases. Each installed addon has its own update feed.

Decide when real bookings begin and distinguish retained business records from disposable test records. A full backup restore is straightforward before real activity; after real requests arrive, preserve/reconcile those new records before restoring an older backup. This guide does not mark advenire.se as installed, tested on-host or publicly launched. Legacy installation protection remains in place; ugl.biz and uglkurser.se migration rehearsal follows separately.

Installation ZIPs contain the new extension’s readable PHP source. Private development history, legacy source and database exports are excluded. Checksums are supplied beside every ZIP.
