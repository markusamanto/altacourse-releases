# Altacourses downloads

Versioned Joomla installation packages and the extension update feed.

Installation packages include the new extension's PHP source. Legacy reference files and private development history are not included.

These alpha packages are for an isolated test site running Joomla 6.2 and PHP 8.4. They are not production releases. Alpha6 adds protected availability editing: administrators can update any course; suppliers can update only their own upcoming courses. Stale forms and concurrent overwrites are rejected. The public course list supports UGL/UL, region and date filters. Alpha11 adds full frontend course editing with supplier assignment and 3+1/2+2 dates. Supplier profiles/terms and public information enquiries are now available. Binding signup with saved terms acceptance is now available. Controlled Mailtrap notifications are now available and disabled by default.

Download a ZIP from `packages/` and install it through Joomla's extension installer. Checksums are supplied beside each ZIP.

Update-feed address: https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/updates.xml

Install alpha3 manually once to register this feed. Joomla can then offer later versions through its extension updater. Configure the test site to allow alpha releases; production should accept stable releases only.

Latest test version: [Download alpha20](https://raw.githubusercontent.com/markusamanto/altacourse-releases/main/packages/com_altacourses-2.0.0-alpha20.zip).

Alpha4 creates six empty course-list tables. It refuses legacy or unknown Altacourses tables; this is not a production-data migration. Update the installed component without uninstalling. Sample loading is off by default, requires course-administrator permission and a valid protected form, and only works when all six tables are empty. It sends no mail and creates no users.

Alpha5 preserves the six alpha4 tables and existing ownership assignments. The original synthetic sample courses remain unassigned, so supplier accounts initially have an empty management list. No user accounts or assignments are created by this update.

Alpha6 adds an availability revision counter through schema migration 2.0.1. Existing records and relationships remain intact. There are no delete, trash or purge actions. No mail or external integrations are invoked. Update without uninstalling; older packages cannot be used to downgrade this schema.

Alpha7 adds administrator-only supplier assignment to active Joomla accounts with supplier permission. Assignment updates invalidate older availability forms, and removing assignment retains the course. No supplier profiles, mail, external integrations or additional schema migrations are included.

Alpha8 adds additional-session storage and displays all date ranges in public and protected course lists. Date-to filtering uses the final session end; date-from uses the original first start. Location and leaders remain shared. Schema 2.0.2 adds one linked table without changing existing course dates. An opt-in protected fixture action extends the two UL synthetic samples. Course-creation/session-editing forms are not included yet.

Alpha9 adds frontend course creation: administrators select the supplier in the form; suppliers create courses assigned to themselves. One or two sessions, required core fields, retained values on validation errors and immediate publication are supported. Schema 2.0.3 adds a unique nullable creation-submission key to prevent duplicate saves. Existing records remain unchanged. Full course editing and bookings are still forthcoming.

Alpha10 simplifies the Swedish supplier label to Arrangör and defaults new-course availability to 3+. Submitted or explicitly provided availability values are retained. No schema or existing record changes.

Alpha11 unifies course details and supplier assignment in one frontend editor. Administrators edit all courses; suppliers edit their own upcoming courses. Saved sessions and record history are preserved, stale writes are rejected, and updates remove the retired standalone assignment screen. There is no schema change or production-data migration.

Alpha12 adds public course details, linked directly from the component listing, with all session ranges, shared location/leaders, prices/lodging, availability and escaped public notes. The back link preserves search filters and pagination. Direct URLs use the same visibility rules as the list. No additional modules, business-data writes or schema changes are introduced. Booking/enquiry forms and legacy article/4SEF mapping remain separate work.

Alpha13 corrects the lodging display for older records: when a price exists and inclusion is unset, the price is displayed without an additional “not specified” label. Existing included/separate labels and all stored values are preserved. No schema or integration changes.

Alpha14 changes only public pricing: the listing and details show one total followed by kr. Two entered prices are added; a single course fee with lodging included is the total. Protected editing retains both fields and the checkbox. No stored data or schema is changed. Supplier profiles and booking terms are planned for alpha15.

Alpha15 adds protected frontend supplier profiles and booking/cancellation terms. Administrators manage supplier profiles; suppliers manage their own. Joomla account email remains the notification address and account editing remains native Joomla. Schema 2.0.4 adds the legacy-shaped supplier table with safe keys, Unicode/transactional storage and revision checks. Existing course/session data is retained; legacy table collisions and schema downgrades are refused. No booking submission or notifications are included.

Alpha16 adds a public six-field information-enquiry form with course/session summary, transactional persistence and private administrator review. Schema 2.0.5 adds clients, requests and immutable submission snapshots while preserving existing records. Repeated submissions are deduplicated and existing participant profiles are never overwritten by anonymous email matches. No email, newsletter integration or CAPTCHA is included yet. Keep Send Mail disabled; this increment saves enquiries only.

Alpha17 adds binding UGL/UL signups with fifteen participant/billing fields, displayed total and explicit supplier-terms acceptance. Course/price/terms changes invalidate an open form and require renewed acceptance. Saved agreement and contact snapshots are immutable; duplicate POSTs cannot create another booking, and anonymous email matches never overwrite existing participants. Frontend administrator review includes the saved terms and acceptance time. Schema remains 2.0.5; no email, newsletter or CAPTCHA integration is added. Update without uninstalling and keep Send Mail disabled.

Alpha18 changes signup Visa into a separate, administrator-only participant page with submitted details above combined signup and enquiry history. Every history entry opens its saved contact/course details; split-session dates and originally accepted terms/prices are retained. The back link returns to the signup list. No data/schema changes or email are included; controlled notifications are planned separately for alpha19. Keep Send Mail disabled and update without uninstalling.

Alpha19 adds disabled-by-default Mailtrap-only notifications for enquiries and binding signups, with two immutable messages per new submission, administrator previews/status and reviewed recovery for unconfirmed attempts. It permits only authenticated sandbox.smtp.mailtrap.io SMTP on port 587/2525 with STARTTLS; no production transport, PHP mail or sendmail fallback. Schema 2.0.6 adds one outbox table; existing records are preserved and historical messages are not backfilled or sent automatically. Duplicate forms do not resend mail and SMTP failure cannot undo a saved booking. Keep Send Mail off until the documented controlled test; this remains an isolated-site test release.

Alpha20 adds private, sanitised SMTP failure diagnostics: a fixed reason category and numeric SMTP/enhanced codes where available. Raw server text, addresses and credentials are not stored in diagnostics or displayed. Sending order, database-first saving, retry policy, sandbox-only restrictions and schema 2.0.6 are unchanged. This diagnostic release helps establish the cause of a second-message failure; it does not assume sandbox throttling or add a background worker.

Alpha21 adds frontend Kontakter with searchable/filterable enquiry and signup submissions, separate details and mixed participant history. Suppliers see only their own historical submissions, even when a participant has contacted several suppliers. Course reassignment does not transfer previous contacts. Administrator history remains complete. This is read-only, with no mail, data or schema changes; keep sending disabled and update without uninstalling.

Alpha22 adds frontend participation confirmation for enquiries and signups from the first course day, including UL before its final session. Suppliers report only their own historical contacts; administrators can correct outcomes across suppliers. Notes, reporting dates/actor and stale/concurrent-save protection are included. Schema 2.0.7 adds two request columns while preserving all existing records. No mail or invoice generation is added. Keep sending disabled and update without uninstalling.

Alpha23 changes participation to Interface A: a queue of started courses with outstanding confirmations, a Stäm av link to each course form, and one Save for all visible unreported enquiries/signups. Partial completion keeps the course listed; full completion removes it. A conflict or failed write rolls back the entire form. Existing individual correction links remain available. Schema 2.0.7 and existing data are unchanged. Keep sending disabled and update without uninstalling. Rebooking remains separate.

Alpha24 adds the administrator frontend commission overview by confirmation month, supplier totals, one fixed supplier rate for UGL/UL, and reviewed manual CSV downloads. Download records the displayed amounts so later current-rate changes cannot rewrite them. Missing rates block export. Schema 2.0.8 adds three nullable request fields without automatic historical backfill. CSV keeps seven semicolon-separated columns and adds UTF-8 BOM for Excel. This is invoice preparation, with no invoice sending or monthly task yet; scheduled administrator email is planned for alpha25. Keep sending disabled and update without uninstalling.


Alpha25 adds the controlled monthly administrator CSV and private delivery archive. Update the component first. Install `packages/plg_task_altacoursesmonthly-2.0.1-alpha25.zip` once to add the native Joomla Scheduled Tasks routine; later plugin versions use `updates-monthly.xml`. Both monthly and booking mail default to disabled. This release allows only Mailtrap sandbox SMTP; no production SMTP. Schedule daily to send the previous calendar month once; commission amounts are captured automatically without a manual CSV download. Task activation, recipient and SMTP configuration are explicit test-site setup steps.

Use task plugin **2.0.1-alpha25** for the first installation. The earlier 2.0.0-alpha25 plugin ZIP is retained for immutable release history; its shared update-feed address was corrected in 2.0.1-alpha25. The component remains 2.0.0-alpha25.
