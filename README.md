# Altacourses Beta4

Beta4 updates the component only. Compact Courses remains Beta3 and Related Courses remains Beta3.1; install their updates if not already installed. Back up files/database first; do not uninstall to update. Use Joomla Live Update with minimum extension stability Beta, or upload these ZIPs. Updating retains business records, settings, delivery modes, module instances/assignments and schedules; schema stays2.0.28.

| Package | Current download |
|---|---|
| Component | [com_altacourses 2.0.0-beta4](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/com_altacourses-2.0.0-beta4.zip) |
| Compact courses | [mod_altacourses 2.0.0-beta3](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altacourses-2.0.0-beta3.zip) |
| Related courses | [mod_altarelatedcourses 2.0.0-beta3.1](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altarelatedcourses-2.0.0-beta3.1.zip) |
| Course details (unchanged) | [mod_altacoursedetails 2.0.0-beta2](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altacoursedetails-2.0.0-beta2.zip) |
| Scheduled tasks (unchanged) | [plg_task_altacoursesmonthly 2.0.1-beta1](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/plg_task_altacoursesmonthly-2.0.1-beta1.zip) |
| Editable letter (unchanged) | [mod_altacoursesletter 2.0.0-beta1](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altacoursesletter-2.0.0-beta1.zip) |
| Public evaluations (unchanged) | [mod_altaevaluations 2.0.0-beta1](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/mod_altaevaluations-2.0.0-beta1.zip) |

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
