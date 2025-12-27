<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket — Post-Installation Configuration</h1>
After successfully installing osTicket, several post-installation steps are required to secure, configure, and prepare the system for production or testing.<br />


<h2>Environments and Technologies Used</h2>

- Operating System & Platform-"IIS + PHP"
- Web Application Stack-"MySQL"
- Database Layer-"SMTP"
- Email Services-"TLS, firewall, permissions"
- Security & Access-"Admin panel, phpMyAdmin, CLI"
- Backup & Monitoring-"Logs, mysqldump, Task Scheduler"
- Tools / Utilities

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Post-Install Configuration Objectives</h2>

- Secure the Installation
- Configure Email
- Create Departments and Help Topics
- Configure Ticket Forms and Fields 
- Add Agents and Assign Roles
- Configure Business Hours and SLA Policies
- Enable Required PHP Extensions
- Backup & Maintenance
- Monitor and Maintain
- Recommended Checks


<h2>Configuration Steps</h2>

<p>
<img width="778" height="730" alt="image" src="https://github.com/user-attachments/assets/4e6a3f83-6735-42b4-8dd1-e418b895f5d6" />

</p>
<p>
Step 1: Secure the Installation

Remove the Setup Directory:

Delete: C:\inetpub\wwwroot\osTicket\setup
Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
Configure SSL/TLS in IIS or your web server.

</p>
<br />

<p>
<img width="1153" height="890" alt="image" src="https://github.com/user-attachments/assets/e252eaaf-ee8f-49df-86ad-c1b86d6b51d9" />
 Step 2:
</p>
<p>
Incoming Emails (IMAP/POP3 Fetching)
Recommended: Configure a mailbox for support tickets.
Admin Panel → Emails → Email Fetching → Add mailbox (IMAP preferred).
Test email retrieval to ensure tickets are created automatically.
</p>
<br />

<p>
<img width="1194" height="723" alt="image" src="https://github.com/user-attachments/assets/445816ff-3a8c-41ae-9668-f21f90bd2024" />

<img width="1194" height="559" alt="image" src="https://github.com/user-attachments/assets/f85afd42-2219-4560-9d5d-1355f8632748" />

<img width="1058" height="801" alt="image" src="https://github.com/user-attachments/assets/b0fb15fd-4e13-4b25-8e88-cbacf30cdefb" />

<img width="1143" height="632" alt="image" src="https://github.com/user-attachments/assets/08583a59-c23a-455d-ae02-7c31009c8a5b" />

Step 3:
</p>
<p>
3: Create Departments and Help Topics
Admin → Agents → Departments → Add logical teams (e.g., IT, HR, Finance).
Admin → Manage → Help Topics → Add topics mapping to departments.
</p>
<br />


<img width="1167" height="898" alt="image" src="https://github.com/user-attachments/assets/ae162c95-6752-4ff0-a288-92b23af79320" />


<img width="1198" height="929" alt="image" src="https://github.com/user-attachments/assets/137a013e-eaa7-48b9-a9b9-c9112bbed029" />


<img width="1191" height="921" alt="image" src="https://github.com/user-attachments/assets/f80110f4-fc3d-4e04-93f5-bb9a3c9587fd" /> 


<img width="1190" height="901" alt="image" src="https://github.com/user-attachments/assets/2d01b6a0-ca4a-4f48-9b4c-3b99334e8ddd" />



<img width="1188" height="826" alt="image" src="https://github.com/user-attachments/assets/f2af4359-93dc-4e80-8ab4-951ebf7f1238" /> 


<img width="802" height="663" alt="image" src="https://github.com/user-attachments/assets/71663ecd-a671-4981-8ec2-e8c70d2b8af6" />


<img width="809" height="530" alt="image" src="https://github.com/user-attachments/assets/a76665f1-4325-47ae-8b15-571dea2bb0af" />



Step 4:


Configure Ticket Forms and Fields, step by step guide: "Customize ticket forms and field structures in osTicket to collect standardized data during ticket creation, ensuring consistent information capture for all help topics". Open the Forms Manager -Login to the Admin Panel.-Navigate to Manage → Forms.-Review built-in forms (Ticket Details, Contact Information, etc.) and any custom forms. Step 2 — Create a Custom Form. -Click Add New Form. -Enter a descriptive name (e.g., Hardware Request Form).-Add an internal description for staff reference. -Select the form type (Ticket, Task, User, or Organization). Step 3 — Add Fields -Click Add Field. -For each field, configure: .Label: User-facing name (e.g., Dell Latitude) .Variable Name: Internal identifier (e.g., Dell Latitude)
.Type: Select input type — Short Answer, Dropdown, Date, Checkbox, etc. .Visibility: Client, Agent Only, or Both. .Required: Yes/No .Help Text: Short instruction for users.-Save after adding all necessary fields. Step 4 — Link Custom Form to Help Topic. -Go to Manage → Help Topics. -Edit the target topic (e.g., Hardware Requests) -Under the Forms section, attach your custom form -Save changes. Step 5 — Edit Built-In Forms (Optional) -From Manage → Forms, open Ticket Details or Contact Information.-Add or modify fields to capture universally required information.-Save configuration. Step 6 — Test the Form-Open the Client Portal.-Select the Help Topic linked to the new form.-Verify that all custom fields appear and required validation works.-Submit a test ticket.-In Agent Panel, open the ticket to confirm internal-only fields are visible to agents. Step 7 — Optional Automation Integration.-Record each field’s variable name.-Use variables in canned responses, email templates, or API requests.-Example variable usage: {{ticket.custom_data.device_type}} Step 8 — Validation & Documentation.The step-by-step document for configuring ticket forms and fields in osTicket has been created.




<p>
<img width="1197" height="743" alt="image" src="https://github.com/user-attachments/assets/79bcf401-2a0c-4c7c-8bdd-f69e2ea5faf1" />

<img width="1002" height="890" alt="image" src="https://github.com/user-attachments/assets/193fc8d9-cec2-4803-9b38-54575b759ca2" />


<img width="1203" height="633" alt="image" src="https://github.com/user-attachments/assets/8a8e84d9-788d-46b3-b245-c4d2c5d7d9bf" />


</p>
<p>


Step 5
Add Agents and Assign Roles Guide: Admin → Agents → Add new agents. Assign roles and departments to each agent.
Ensure permissions follow the least privilege principle.


<img width="1201" height="567" alt="image" src="https://github.com/user-attachments/assets/b11ad424-48ae-44a1-b057-53206551608e" />

Standard1


<img width="1201" height="525" alt="image" src="https://github.com/user-attachments/assets/c260467d-2cef-46f6-a417-48512bd27bc6" />

Urgent1

<img width="1198" height="477" alt="image" src="https://github.com/user-attachments/assets/9e2b96b2-9005-45a4-aa3c-eee59e330c6e" />

Urgent2



 Create three different SLA Plans: Admin → Manage → SLA Plans → Add New SLA Plan. For each SLA plan: Name: 1 Standard (48h) and 2 Urgent (8h). Description: short purpose and scope.
Duration: set measured interval (hours/minutes) that the SLA enforces. Example field semantics: Response SLA: 8 hours (counted during assigned schedule). Resolution SLA: 48 hours. Assign Schedule: select HQ Business Hours so the SLA is calculated only during those hours. Transient: enable if the SLA should be overridable by filters or department changes (optional). Save each SLA plan.



<img width="1207" height="667" alt="image" src="https://github.com/user-attachments/assets/3038de98-9982-4870-abea-871078d563a8" />



Assign SLAs via one or more of the following methods; record the mapping: "Department-level"  Go to - Admin → Manage → Departments → Edit Department → SLA Plan field → select SLA plan. → Save.


<img width="1200" height="598" alt="image" src="https://github.com/user-attachments/assets/244c84f0-7f0d-4123-b9d5-d54bce6f8444" />



Assign SLAs via one or more of the following methods; record the mapping: "Help Topic-level" Go to - Admin → Manage → Help Topics → Edit Topic → SLA Plan → select SLA plan. → Save.


<img width="1196" height="853" alt="image" src="https://github.com/user-attachments/assets/ce44ba15-8767-47ac-a8a0-130ae1409138" />

Ticket Filters / Automations: Go to Admin → Manage → Ticket Filters → Add New Filter. Conditions: (e.g., Help Topic = “Incident” OR Subject contains “outage”) → Actions: Set SLA = Urgent (8h), Set Priority = High. → Save. Ensure filter ordering executes before routing/assignment filters.

Steps 6
</p>
<p>
Configure Business Hours (Schedules) and SLA Policies — Step-by-Step Technical Guide: Objective: Define business hours (schedules) and SLA plans in osTicket so SLA timers count only during operating hours and alerts trigger per policy. Prerequisites: Admin access to osTicket (/scp/) with Manage permissions. Working background job (cron) ability on the server or external webcron access. Timezone determined for helpdesk (document absolute timezone, e.g., America/New_York). 1 — Plan schedules and SLA targets: Decide business hours (e.g., Mon–Fri 09:00–17:00) and holidays. Define SLA targets (examples): Standard Response — respond within 8 business hours. Resolution Standard — resolve within 48 business hours. Urgent — respond within 1 business hour, resolve within 8 business hours. Decide assignment scope: per Department, per Help Topic, or via Ticket Filters. Document plan names, durations, and assignment rules in your repo. 2 — Create Schedule (Business Hours): Admin → Manage → Schedules → Add New Schedule.
Configure: Name: HQ Business Hours Timezone: set to helpdesk timezone. Business Hours entries: add one row per pattern, e.g.: Monday–Friday | 09:00 | 17:00, Holidays / Exceptions: add specific dates or ranges (YYYY-MM-DD). Save schedule. Note: Holidays must be entered so SLA timers pause on those dates. 3 — Create SLA Plans: Admin → Manage → SLA Plans → Add New SLA Plan.
For each SLA plan: Name: Standard (48h) / Urgent (8h). Description: short purpose and scope. Duration: set measured interval (hours/minutes) that the SLA enforces. Example field semantics:Response SLA: 8 hours (counted during assigned schedule). Resolution SLA: 48 hours. Assign Schedule: select HQ Business Hours so the SLA is calculated only during those hours.
Transient: enable if the SLA should be overridable by filters or department changes (optional). Save each SLA plan. 4 — Assign SLA Plans: Assign SLAs via one or more of the following methods; record the mapping: Department-level Admin → Manage → Departments → Edit Department → SLA Plan field → select SLA plan. → Save. Help Topic-level Admin → Manage → Help Topics → Edit Topic → SLA Plan → select SLA plan. → Save. Ticket Filters / Automations Admin → Manage → Ticket Filters → Add New Filter. Conditions: (e.g., Help Topic = “Incident” OR Subject contains “outage”) → Actions: Set SLA = Urgent (8h), Set Priority = High. → Save. Ensure filter ordering executes before routing/assignment filters. 5 — Ensure Scheduled Tasks (cron / rcron) Run Regularly SLA timers, overdue checks, and alerts require the osTicket task runner. Recommended cron (run as web user or user with PHP CLI access): # run tasks every 5 minutes
*/5 * * * * /usr/bin/php /var/www/osticket/api/tasks/cron > /dev/null 2>&1 Alternate (web cron calling rcron.php — less preferred):*/5 * * * * /usr/bin/curl -s 'https://helpdesk.example.com/rcron.php?key=YOUR_RCRON_KEY' > /dev/null 2>&1 Place the line in crontab (crontab -e) for the appropriate system user. Verify execution in osTicket System Logs (Admin → Dashboard → System Logs) for entries like Cron executed or SLA check. 6 — Test SLA Calculation and Alerts Create test tickets for combinations:Department A → Standard SLA Help Topic X → Urgent SLA For predictable testing, create short-duration test SLAs (e.g., 5 minutes) assigned to a test schedule. Use these to validate overdue behavior without waiting days.
Validate: Due date calculation respects business hours (falls within business schedule). SLA status (Active / Warning / Breached) updates after expected time. Alert emails are sent per SLA breach rules. Audit log shows SLA assignment and timer events. Test behavior across holiday dates to confirm pause/resume.7 — Escalation & Automation (optional) Create Ticket Filters that escalate on SLA warning or breach: Condition: SLA status = Breached → Action: Assign to Escalation Team; Add Alert to Managers; Change Priority. Use auto-responses to inform requesters on SLA escalation changes. 8 — Reporting & Monitoring Use osTicket reporting (or export) to track SLA metrics: % met vs breached, average response time during business hours. Schedule a regular review cadence (weekly/monthly) to refine SLA windows and staffing. 9 — Troubleshooting: SLA not honoring business hours: Confirm SLA Plan is associated with the correct Schedule and timezone settings match system timezone. No overdue alerts: Verify cron jobs execute and system logs show cron runs. Confirm alert recipients are valid users/emails. Incorrect due date calculation: Check holidays/exception entries and that Tasks/cron are not delayed.Filter overwrites SLA unexpectedly: Review Ticket Filters order and transient SLA settings.

</p>
<br />



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
