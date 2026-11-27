# Altacourses Beta5.3

Beta5.3 updates the component only. The four migration-compatible modules remain at Beta5.1. Existing rebuilt sites can use Joomla Live Update with minimum stability Beta; component first. Back up files/database and do not uninstall. The first legacy ugl.biz installation needs the manual migration procedure below. Compact Courses and Scheduled Tasks keep their previous versions. Business schema stays2.0.28.

| Package | Current download |
|---|---|
| Component | [com_altacourses 2.0.0-beta5.3](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/com_altacourses-2.0.0-beta5.3.zip) |
| Compact courses | [mod_altacourses 2.0.0-beta3](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altacourses-2.0.0-beta3.zip) |
| Related courses | [mod_altarelatedcourses 2.0.0-beta5.1](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altarelatedcourses-2.0.0-beta5.1.zip) |
| Course details | [mod_altacoursedetails 2.0.0-beta5.1](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altacoursedetails-2.0.0-beta5.1.zip) |
| Scheduled tasks (unchanged) | [plg_task_altacoursesmonthly 2.0.1-beta1](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/plg_task_altacoursesmonthly-2.0.1-beta1.zip) |
| Editable letter | [mod_altacoursesletter 2.0.0-beta5.1](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altacoursesletter-2.0.0-beta5.1.zip) |
| Public evaluations | [mod_altaevaluations 2.0.0-beta5.1](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altaevaluations-2.0.0-beta5.1.zip) |

## Beta5.3 — public search help

Add a Joomla Custom module at position **altacourses_search_help** (type the position if not predefined by your template). It appears directly below the complete search panel on the component public course listing, before pricing and results, even when search is collapsed. Choose normal module publication/access/language/menu assignments. Its content is rendered without extra title/card chrome; style the content through your own classes and user.css. Empty/unpublished help leaves no position wrapper or gap.

Native component upgrade58 and public HTTP50 checks pass, including placement, menu/access/publication/order, filtering, no results and pagination. Only the component needs updating.

## Beta5.2 refinements

- Manage Courses: company names for suppliers, course leaders column, publication check/X icons with accessible status, no visible course-ID column, course-ID filter for administrators only, and only the Edit course action.
- Signup: hide personal postal address/postcode/city while retaining billing fields and existing data elsewhere; remove the redundant binding-booking sentence and visible terms-label asterisk; “Submit signup” / “Skicka anmälan”. Terms acceptance remains mandatory.
- uglkurser.se migration checklist: review4SEF duplicates and change the information-page destination from the old article to native component course information, preserving the current course ID.
- Native component update58, focused rendering/role/validation50 and company fallback18 local checks passed. No module, task-plugin or schema update is required for this increment.

## Beta5 changes and legacy installation

- Guarded offline adoption of the inspected ugl.biz legacy schema, retaining original IDs/history and source tables, with a recovery journal and backend report. Unknown inventories and nonempty legacy managers/rebooked/keyaccount histories requiring further mapping are refused.
- Converted working/public menus preserve frontend IDs/aliases/access and help-module assignments. Compatible related/detail/letter/evaluation module instances are handed over when replacements are installed. Old full-listing/page-layout/quick-statistics instances are deliberately held for component-based replacements and review.
- Ambiguous shared legacy evaluation credentials fail closed; unambiguous old credentials and public signup/enquiry GET entry routes retain compatibility.
- Remove New course from Manage Courses; translated native-calendar hints ÅÅÅÅ-MM-DD / YYYY-MM-DD; latest committed Swedish wording included.

**First legacy installation on ugl.biz:** do not upload this to Joomla5/PHP8.2. Keep the site offline; stop old external cron and disable legacy Finder plugins. Take a complete files/database backup, check the site's other extensions/template, switch to PHP8.4 and use Joomla's supported upgrade path to at least6.2. Keep the old module records/publication settings intact for migration; do not uninstall. Do not open old frontend working pages during the transition.

Take an additional upgraded-platform backup before replacing the component. Manually install the component Beta5 ZIP, inspect Components → Altacourses for the migration report, then install the four Beta5 module ZIPs. Review unmapped menus, public listing/information menu conversions, old full-listing and information-page module replacements, supplier access, original records, letter/image/links and the actual custom template before reopening. The inspected copy has menu220 (`mailtemplates_types`) and424 (`admin_courses`) needing manual review. The old full listing is not a drop-in compact-listing instance.

Delivery/API modes remain off. Configure/preview site-specific settings and the two existing active future signups before enabling replacement Joomla tasks. Never run old cron and new routines together. The original tables/journal are retained privately in the database; do not delete them as an installation workaround.

If installation stops, keep the site offline, correct a diagnosed permissions issue and retry the same package; the journal supports resuming the prepared database state. For full rollback, restore matching complete files/database and PHP version. Table archives alone do not roll back Joomla files/settings, and restoring an old backup after accepting new records requires reconciliation.

The owner plans a direct production installation after backup, without a hosted staging site. Local native migration/interruption/retry, data/metadata reconciliation and runtime checks used a private copy of the supplied export, with no real email/API delivery. The actual core upgrade and deployed vendor/template files were not rehearsed. The fresh Joomla5.4.11 export supplied on2026-11-26 has now passed the final local comparison and repeat migration rehearsal; no package changes were required. Take a current complete backup at cutover. [Detailed installation and rollback guide (repository access required)](https://github.com/markusamanto/altacourse/blob/beta5-migration/docs/beta5-installation.md).

## Beta4 changes

- Joomla calendar pickers with week numbers on course forms and listing filters. Date-only ISO storage and strict validation remain.
- Supplier dropdowns show company name, falling back to account name when missing. Ownership and permissions stay unchanged.
- Remove dashboard-return links on Manage Courses, Participation reconciliation and Contacts; remove the redundant public listing subheading.
- Include the owner's committed Swedish wording edits and matching menu-type labels.
- No schema change or new module/plugin update. The legacy-install guard stays in place; migration readiness for ugl.biz is planned separately for Beta5.

## Beta3.1 correction

If Beta3 is installed, update **only Related Courses**. Version2.0.0-beta3.1 splits its text in both leader/place modes: VAT plus the relevant linked-name instruction first, then T inclusion or separate V Internat/Externat paragraphs. That module correction did not change component data/settings. CSS hooks: `.altarelatedcourses-price-notice`, `-total`, `-internat`, `-externat`.

## Beta3 changes and setup

- Public table caption is visually hidden. VAT/instructions come first, followed by separate inclusion paragraphs with stable CSS classes. Compact pricing paragraphs follow the listing button, VAT first.
- Variable-price numbered markers now explain themselves on hover/focus/tap. Tooltips support Escape/outside dismissal, one open at a time, viewport positioning, dynamic listings and multiple instances; visible explanations remain without JavaScript. Price arithmetic/residential numbering stay unchanged.
- Native menu types now cover administrator/supplier working pages with translated labels and record selectors where needed. Change existing **System Links → URL** items to the matching **Altacourses** type while preserving their alias/ID and access level. Login/Custom help modules can then use **Only on the pages selected**. No menu conversion or module reassignment happens automatically; existing page permissions still apply.
- Supplier welcome component output is only **Välkommen / Welcome** in H1. Use your Custom module for the remaining text. Administrator welcome/statistics remain unchanged.

Native reference forms offer Add new; contextual pages require the appropriate record. Supplier profile defaults to the logged-in supplier; administrators select a supplier. Key-account billing uses R# current requests or L# legacy records with the matching data-source selector. Public token/receipt/submission screens and obsolete redirect aliases are not admin menu destinations.

Component pricing CSS hooks: `.altacourses-price-notice`, `-total`, `-internat`, `-externat`. Compact equivalents: `.altacourses-compact-price-notice`, `-total`, `-internat`, `-externat`. Tooltip hooks: `.altacourses-price-marker`, `.altacourses-price-trigger`, `.altacourses-price-tooltip`, with `--altacourses-tooltip-background`, `--altacourses-tooltip-color`, `--altacourses-tooltip-border` variables for user.css.

Local Chromium checks cover hover/keyboard/Escape, movement into the tooltip, touch emulation/outside taps, viewport bounds, multiple instances, dynamic IDs/removal, duplicate-handler prevention, no form submission/navigation and JavaScript-disabled explanations. Real iPhone Safari and branded desktop Chrome/Edge remain manual checks, particularly orientation/zoom and interaction with the site's own CSS. Chromium touch emulation is not Safari verification.

## Public course-listing menu

**Menus → your menu → New → Altacourses → Public course listing / Publik kurslista** provides All or selected course types. All includes future types. Visitors can narrow but cannot broaden that menu's selection; searches/pagination retain its Itemid. Standard browser page title, heading/visibility and metadata are honoured. Direct/module listing links retain their existing behaviour.

## Fresh-install essentials

Compatible with the verified Joomla6.2 / PHP8.4 / MySQL8.4 baseline. Install the component first, then only the addons the site needs. Set module positions/menu assignments and publish them deliberately. Keep synthetic sample loading disabled on real sites. No legacy database import is part of this installer; legacy migration retains its separate guarded procedure.

Frontend welcome: `index.php?option=com_altacourses&view=dashboard`. Public courses: `index.php?option=com_altacourses&view=courses`. Super Users can administer the frontend; ordinary suppliers need the component's **Frontend supplier access** permission and a linked supplier profile with booking terms.

Before creating courses, initialise/publish availability status codes in Platsindikeringar: **1=3+**, **2=Fullbokat**, **3=Få**, **4=Inställd**. These are status codes, not record IDs. Create course types, regions, places, leaders, suppliers and terms, then course occasions/sessions/prices. Set multiple-types display appropriately. Total price mode T remains default; choose V for mixed Internat/Externat courses and mark the non-residential occasions explicitly (all existing/new courses initially default Internat).

Review site branding, articles/category/image references and mail templates. Configure reCAPTCHA v2 keys for the site's domain and explicitly enable protection (recaptcha.net). Configure evaluation public URL/thank-you Custom module if used. Numeric Joomla IDs from another site do not identify the same content here.

Fresh email and marketing modes default Disabled. Configure authenticated encrypted SMTP and explicitly choose Sandbox/Production per feature only when ready; old Disabled/Sandbox messages do not automatically become production-eligible. Keep the UGL-only Mailchimp series off for UL sites; configure an appropriate Zenler funnel or leave newsletter delivery off. Create/enable scheduled routines only when configured; CPanel cron invokes Joomla Scheduler. Installation does not create live schedules. Updating retains existing settings.

After real bookings begin, preserve/reconcile new records before restoring an older backup. Publication does not install anything on hosting or change live mail/API settings.

Each package has its own native update feed and SHA-256 file. Earlier immutable ZIPs remain in packages/. Installation ZIPs include readable new PHP source; private history, legacy reference and database exports are excluded.
