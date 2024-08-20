# Release notes: Version 2024.54.0

### Release Date: Aug 26, 2024 – 1:00 AM PST

## New Functionality

- FT-995: API - Bulk Export of Document Summary Data 
To streamline the process of exporting document summary data, we have introduced a new API endpoint that allows bulk export of this data.  With the new endpoint, you can retrieve all document summary records that have been updated recently, in a single request. This enhancement significantly reduces the number of API calls required, improving efficiency and reducing the time needed to access document summary data across multiple patients. For more details, please refer to the Welkin public collection in Postman.

- FT-1020: Automation for Generating and Sending Superbills
We have introduced a new feature that allows the automation, generation, and delivery of superbills to patients. This automation can be configured to send superbills via both regular and secure email, with the option to select a preferred email template. Organizations can set conditions based on Billing Type (e.g., Self-Pay) and use Encounter properties, such as Delivery Method or Billing Type, as triggers. Additionally, fields from Encounter Dispositions can be used to refine the automation criteria. If no invoice is generated for the Encounter, the automation will be failed, and an appropriate record will be logged in the automation audit within the Admin portal.

- FT-1078: Custom Logo Display in Care Portal
We have introduced a feature that allows you to customize the Care portal UI by displaying your own logo instead of the Welkin logo. This enhancement enables you to personalize the portal, aligning it with your branding and creating a more cohesive experience for users.

- FT-1066: Generated Invoices and Superbills Added to Patient Document Center
We have implemented a feature that automatically adds generated invoices and superbills to the patient’s Document Center under new predefined document types. You can now easily access these billing documents directly from the Document Center as soon as they are generated, streamlining the process of providing patients with necessary billing information.

- FT-1094 (WS-4039): Customizable Authorization Page for Patient Login Screen
You may now customize the Authorization page on the patient-facing login screen for questionnaires, assessments, and surveys: enabling or disabling the Authorization page or modifying the header text of the authorization form directly within the Care portal. This new functionality provides greater flexibility in tailoring the login experience to better meet your needs.

## Improvements and Bug Fixes

- FT-996: Email Export API eto Include Attachments
We’ve modified the Email export endpoint to ensure all email attachments are now included in exports. 

- FT-925: Improved Rich Text Handling for Variables with Quotes
We’ve enhanced the rich text editor in message templates to better support variables containing quotes. The editor accurately processes and displays these variables, ensuring consistent performance between plain text and rich text formats. 

- FT-1072: Improved PDF Naming Convention for Invoices and Superbills
We have improved the document management experience by standardizing the naming convention for PDFs of invoices and superbills. Invoices are now named as “Invoice_Number_ClientName_Date.pdf.” Superbills use the format “Superbill_Number_ClientName_Date.pdf.” This improvement makes it easier for users to identify and locate downloaded documents by the document name.

- FT-1062: Enhanced Language Options in Designer, Care Portal, and Admin
We have expanded the language options to include German and Italian, along with French and Albanian. These languages are now available for selection in the primary and secondary language lists across the Designer, Admin, and Care portals.

- FT-1099: Updated Visual Design for Sign-In Page
We have updated the look and feel of the sign-in page, including a redesigned Welkin sign-in button. 

- FT-1113 Localization Support for Switzerland
We have added a new locale for Switzerland to accommodate region-specific formatting (time zone and date).

- FT-1021: Bugfix for Patient Deletion Error in Sandbox
We have resolved an issue that prevented users from deleting patients in the Sandbox environment.

- FT-1028: Bugfix for Missing Data in Admin Data Log
We have implemented a fix to ensure that events related to CDT updates are correctly recorded in the Data Audit log.

- FT-1051: Bugfix for Incorrect "Edited" Status on Assessments After Adding Medispan Record
We have resolved an issue where Assessments were incorrectly marked as "edited" after adding a Medispan record. Now, once an Assessment is completed, it will no longer display as edited if only Medispan records are added, ensuring accurate status reporting.

- FT-1052 Bugfix for 404 Error When Editing Medispan Answers
We have resolved an issue that caused a 404 error when editing Medispan answers in an Assessment. Previously, this error prevented answers from being updated correctly. With this fix, edits to Medispan answers will now be processed successfully, ensuring that updates are saved as expected.

- FT-1068: Access Issue Resolved for Insights with 403 Error
We have addressed an issue where users with access to the Insights section were receiving a 403 error. This error occurred when users had the appropriate role but lacked additional policies required for access. With this fix, users with the correct role will now be able to access Insights without encountering permission errors.

- FT-1095 Bugfix for Unrecognized Communications Link
We have resolved an issue where the link to the unrecognized communications page was missing from emails. The link is now correctly included, allowing users to forward and access the unrecognized communications page as expected.

- CT-853: Expanded Automation Flexibility for Webhook Actions
We’ve enhanced the automation system to allow the creation of automations with webhook-only actions, even if the trigger might overlap with another automation. Previously, such configurations were blocked to prevent infinite loops, but this restriction has been lifted for webhook actions since they don’t create internal loops.
This update simplifies automation workflows and reduces the need for complex workarounds, giving users more flexibility while maintaining system integrity. 



# Release notes: Version 2024.53.1

### Release Date: Aug 20, 2024 – 1:00 AM PST

## New Functionality

- CT-675: Pre-authorization of Payments Instead of Charge
For customers needing pre-authorization of payments, we have introduced configurable parameters in the admin panel at the environment or account level. This allows for the following behaviors: If an Encounter is booked more than e.g. 48 hours before the appointment, the credit card is pre-authorized 48 hours before the appointment. If an Encounter is booked less than 48 hours before the appointment, pre-authorization occurs immediately. If an Encounter is canceled more than 48 hours before the appointment, no action is needed. If an Encounter is canceled less than 48 hours before the appointment, the patient is charged a fee, and the remaining amount is released. If an Encounter is marked as finalized, the pre-authorized amount is charged. 
These actions are managed via automation. If an Encounter is rescheduled, the rules apply to the new appointment time.


# Release notes: Version 2024.53.0

### Release Date: Aug 14, 2024 – 1:00 AM PST

## New Functionality

- FT-833: Dataviews Labeling Simplification
To simplify the labeling process for Data Views, labels are pre-filled at Add Form and Edit Form once they are set at View (Fields). This applies if Add Form and Edit Form are “On” and the labels are blank.  They can still be manually changed in each area as needed.

- FT-1016 (WS-4002): Patient - Searchable by Middle Name
As a Care portal user, you can now search for patients using their middle name to quickly and accurately find the correct patient record. The system allows users to search for patients by entering Middle Name only, or combined with First Name/Last Name.

- FT-994 (WS-2762): API - Adding Profile Export
We have added the ability to bulk export Profile data via the API, which is available under the /export/PDT_RECORD route. For more details, please refer to the Welkin public collection in Postman.

## Improvements and Bug Fixes

- FT-990: Move Configuration of Acuity UserID to Admin Panel
For customers using Acuity Enterprise integration, we have moved the configuration of the Acuity User ID field from User Attributes to the Admin panel. This change simplifies the configuration process.

- FT-504: Completed Assessments Sometimes Showing Blank Fields When Viewed
Fixed an issue where completed Assessments sometimes showed blank fields when Profiles were used.

- FT-701 (WS-3503): Save and Add Another in Profiles Get Stuck
Fixed an issue where the interface gets stuck when adding two or more answers to a question linked to Profiles.  Previously, after adding and saving multiple answers, the third addition would retain old information, requiring manual clearing before adding.

- FT-890: Availability Blocks UI Improvement
Added display of Encounter type icons and color coding of Encounter templates to make it easier to differentiate between different Encounter template availabilities.

- FT-975: Encounter Variables in Forms
Added support for new variables {{ENCOUNTER..startDateTime}}, {{ENCOUNTER..endDateTime}}, {{ENCOUNTER.*.location}} to Forms/Assessments. Previously, support for these variables was added to assessment PDFs.

- FT-1013 (WS-3985): Message in Dialog Box Is Off Frame for Messages with Long Links
Fixed the issue where messages in the dialog box would be off-frame if they contained long links.


# Release notes: Version 2024.52.0

### Release Date: July 31, 2024 – 1:00 AM PST

## New Functionality


- CT-805: Billing section
With the new release, Welkin is enhancing billing functionality. A Billing page can now be activated in the main layout in Care to provide a cross-patient view. It will include sub-pages for Invoices and Claims (for accounts with Candid Health integration activated). Sub-pages for Payments and Subscriptions will be added in the future. Additionally, a Billing page has been added to the patient layout, allowing similar information to be managed at the patient level.

- CT-813: Invoices 
We are introducing a new entity - Invoices. These can be used as a payment intent for a patient or as a receipt. In Designer, it is possible to upload a combination of templates for different patient and billing types to generate the appropriate Invoice PDFs. Invoices can be generated for Encounters and predefined services within the Encounter, or from the Billing page without reference to an Encounter, for services like paperwork. Future releases will automatically add Invoices to the patient Document Center.

- FT-900: Superbills
We are introducing Superbills, which can be sent to patients for reimbursement. A new section called “Superbill Template” has been added to Designer, allowing templates to be uploaded for generating Superbills. Superbills can be generated from the Encounter page and list all paid services within the Encounter. Future updates will include an automation for sending Superbills.

- FT-482 (WS-366): Variable Builder for Tables in Assessment PDF
We are adding new capabilities to build variables that will produce tables as outputs in assessment PDFs. This can be used to create documents requiring a table structure, such as listing medications. Variables can be configured to pull information from certain CDTs, filtering and sorting as needed.

## Improvements and Bug Fixes

- FT-885 (WS-3764, WS-3682): PII Information is Hidden in Tasks and Calendar
With this release, when a user views a Provider’s calendar who has patients to whom the user does not have access (due to Territories, Region, or Care Team restrictions), they will see “*****” instead of the first and last name, age, and gender in the calendar event blocks. Tasks for patients to whom users do not have access and for whom they are not the assignee will also be hidden. If the user is the assignee but does not have access to the patient, they will see “*****” instead of the first and last name.

- FT-919: External Profiles (e.g., MediSpan) Usable in Assessments
Previously, when a field attached to an external profile, such as our MediSpan medications, was used in an assessment, it could not search the external profile. It behaved like an internal profile, allowing selection only from items added via a data view. We have improved this functionality, and it will now enable searches within the external database.


# Release notes: Version 2024.51.0

### Release Date: July 15, 2024 – 1:00 AM PST

## New Functionality

- FT-832 (WS-3655): Improved Viewability of Encounter Titles
With this release, we’ve enhanced the readability of long Encounter titles on the list-drawer that appears when a user is creating an Encounter.

- FT-934 (WS-3391): Task Creation for Supervisor Co-Signature
Users can now create a Task from the signature interface to inform supervisors about Assessments pending their signatures.

## Improvements and Bug Fixes

- FT-932 (WS-3923): Default Value 0 Not Saved for Numeric Fields in Data Views
We fixed an issue where the value 0 was not being saved as the default for numeric fields in Data Views in Designer.

- FT-974 (WS-3916): Editing Usernames with Capital Letters
We resolved an issue where it was not possible to edit a user’s first and last name in the admin panel if the username contained capital letters.


# Release notes: Version 2024.50.0

### Release Date: July 3, 2024 – 1:00 AM PST (tentative)

## New Functionality

- FT-936 (WS-3601): Sorting for Data Views based on CDTs where Profiles are used
The sorting capabilities within Data Views has been improved to include CDTs that are connected to Profiles. An additional field ‘Profile Data Type Field’ is added in the Designer to allow this.

- FT-936 (WS-3391): Rich Text Editor for Text Area
A simple rich text editor can now be activated in Designer for Textarea CDTs. Text styling options such as bold, italic, bold italic, and checkbox styles will be available in the Care Portal when text is selected for CDTs with the rich text editor enabled. The added styles will be preserved in the assessment PDF.

- FT-720 (WS-3519): Encounter Variables Added to Assessment Templates
Support for new Encounter-related variables has been added to the Assessment Templates and will be available in the Assessment PDFs:
{{ENCOUNTER_START_DATETIME}}
{{ENCOUNTER_END_DATETIME}}
{{ENCOUNTER_LOCATION}} 
Please note that in the next release, this support will be extended to Assessments/Forms themselves, allowing this information to be viewed as read-only.




# Release notes: Version 2024.49.0

### Release Date: June 17, 2024 – 1:00 AM PST (tentative)

## New Functionality

- FT-912 (WS-3806): Display of Patient-related Contacts Completing Assessments
With this release, when Assessments are completed by patient-related contacts, the Assessment in Care will show the name of the patient-related contact instead of the patient’s name. Additionally, a “Contact” label will be displayed next to the name.

- FT-792: Synchronization of Users’ Availability With Acuity 
For customers with an enterprise plan in Acuity or those created under a Welkin parent account, the availability set for the Encounter templates will be synchronized with the corresponding appointment type in Acuity. This ensures that patients will see accurate availability for various Encounter types when self-scheduling.

- CT-852 (WS-3833): Sourcing NPI Field from CDTs (Candid Integration)
Prior to this release, the NPI field passed to Candid was taken from the user profile of the care member assigned to an Encounter. If the user did not have an NPI (e.g., RN, etc.), they had to enter the supervising provider’s NPI. With this release, the system will first check for the NPI field value in a CDT, and if it does not exist, it will then take the value from the user’s attribute.

- FT-795: Changes to the Font Used for Generating Assessment PDFs
With this release, we will change the default font used to generate Assessment PDFs. The reasoning behind this change is that the current font does not support the necessary styling for some documents, including handling Unicode symbols like checkboxes in different states, and more.


# Release notes: Version 2024.48.0

### Release Date: June 3, 2024 – 1:00 AM PST (tentative)

## New Functionality

- FT-835: Indication of Availability While Scheduling Encounters in Calendar
We have introduced an enhanced feature for scheduling Encounters that displays the availability of care team members in the calendar. When scheduling an Encounter, users can now see when specific users are available according to the selected Encounter template. This makes it easier to suggest suitable time slots to patients for different Encounter types, such as specific appointment types that are only available on certain days of the week. Available time slots for care team members will be displayed in green. This visibility enhancement is available in Day, Week, and Workday views.
In the next release, we will add synchronization of configured availability with Acuity for customers who hold an enterprise account or are maintained as a sub-account under Welkin's enterprise account in Acuity.

- FT-878: Patient Type field in Patient Profile
A new field has been added to the Patient Profile called "patient type," allowing to specify whether the patient record belongs to an adult, minor, or couple. This field can be added to the Top Info section, used as a variable within templates, and is exportable via API.

- FT-928: Change of Sisense domain to https://analytics.welkinhealth.com 
The Sisense domain will be updated from https://sisense.live.welkinhealth.com to https://analytics.welkinhealth.com as Welkin aims to better reflect our enhanced integration of analytics into the Welkin Health platform.

- FT-910 (WS-3759): Saving Phone Without Capabilities
With the new release, users can save primary and secondary phone numbers for patients without assigning any capabilities to them. Previously, saving a phone number required either Voice Call or SMS capabilities to be enabled. This enhancement now allows users to remove both Voice Call and SMS capabilities from a patient’s phone number and save the changes without the system automatically re-enabling these features. This update provides greater flexibility and accuracy in managing patient contact permissions.


# Release notes: Version 2024.47.0

### Release Date: May 22, 2024 – 1:00 AM PST (tentative)

## New Functionality

- CT-764: Provider Signature Capability in Care Portal 
Building on the recently introduced feature for patient e-sign consents, we are now expanding the functionality to allow providers to sign Assessment notes within the Care Portal. Users can now include new document types that require either one or two signatures - from a care team member and a supervisor, respectively - when creating forms in Designer. These forms will incorporate either one or both of the following variables into the Assessment template document: {{care_member_signature}}, {{supervisor_signature}}.  Security Policies will need to be updated to ensure that users can sign notes. 
To use, open the assessment PDF in Care, click on "Sign," add the signature, and then click "Save" to complete the process.
Please note that new document types will be automatically added the next time a Draft is created.


# Release notes: Version 2024.46.0

### Release Date: May 8, 2024 – 1:00 AM PST (tentative)

## New Functionality

- FT-622 - Calendar: working/availability hours per Encounter template
This feature caters to scenarios where users maintain varying availability for different Encounter types. For instance, users may take certain types of appointments only on specific days; or provide services onsite during designated hours. With this enhancement, users can now reflect their availability based on the type of Encounter.
When used, the New Encounter form in the Care Team Member drop down list will have a label appearing next to the users that are not available for a selected template, date, and time. This is similar to the one that currently appears in the case of non-working hours.  

- FT-691 - Connected Stripe accounts
If a customer uses Stripe for collecting patient payments and has separate Stripe accounts for different legal entities, Welkin can now support this scenario by linking connected Stripe accounts to a Master account. This is achievable in the Admin Portal by entering credentials from the Stripe account. Stripe accounts will be linked to a specific billing NPI, which will be incorporated into the attributes of the rendering provider in users' profiles to ensure payments are processed through the correct Stripe account.

# Release notes: Version 2024.45.0

### Release Date: Apr 23, 2024 – 1:00 AM PST (tentative)

## New Functionality

- CT-575 - E-Signing consent forms by patients
This functionality enhances the management of consent forms for patients by introducing a new entity, "Consent," into the Forms section of the Designer portal. This allows for the uploading of a Consent Form template, which can then be sent to patients for e-signature. Patients are required to review the document, create a signature, and e-sign the document, which will subsequently be added to the patient's Document Center. 
A second phase where users in the Care portal can add e-signatures to assessments, enabling them to lock and sign assessment notes, is currently being developed by the engineering team. 

- FT-685 -  External profiles: Medi-Span
A new attribute called "Type" has been added to the Profiles entity in Welkin. Profile types include “Internal” and “External.”  All existing Profiles will be classified as Internal because they are managed, added, or modified in the Care Portal. External-type Profiles will be utilized when the source of Profile values is external or involves large data volumes such as data dictionaries.
The first dictionary connected to Welkin is Medi-Span. Please note that a license with Medi-Span is required to use this feature in Welkin. If you need Medi-Span or other dictionaries added to Welkin, please contact the Welkin Account Management team or enter a Work Request ticket.

- FT-691 - Connected Stripe accounts
If a customer uses Stripe for collecting patient payments and has separate Stripe accounts for different legal entities, Welkin can now support this scenario by linking connected Stripe accounts to a Master account. This is achievable in the Admin Portal by entering credentials from the Stripe account. Stripe accounts will be linked to a specific billing NPI, which will be incorporated into the attributes of the rendering provider in users' profiles to ensure payments are processed through the correct Stripe account.

- FT-808 -  Replace "NA" with "-" in PDF templates
This task modifies how variables with empty values are displayed in the PDF template output, changing from "NA" (not answered) to "-", to improve the patient experience.



## Improvements and Bug Fixes

- FT-790 - Variable fonts from docx templates in assessments PDFs
This update corrects the interpretation of DOCX templates and improves the rendering of text styles(in particular bold, italics) in Assessment PDFs.

- FT-791 -  Running title syntax specifics in DOCX templates and related PDF markup issues
This update enhances the interpretation of running titles in DOCX templates. Due to inconsistencies in the XML structure produced by different versions of MS Word, special guidelines will be issued on how to structure running titles to avoid layout issues in the PDF output. 

- FT-796 (WS-3592) - UX improvement for Data Views "Add Form" with linked Profile record field
This update enhances the behavior of the "Add Form" in Data Views, particularly when containing CDT fields linked with Profile records. Previously, when adding a new Profile record within the "Add Form," the data entered into the fields would not be preserved. With this improvement, the data entered into the fields prior to adding a new Profile record is now preserved, ensuring a smoother and more user-friendly experience.





# Release notes: Version 2024.44.0

### Release Date: Apr 8, 2024 – 1:00 AM PST (tentative)

## New Functionality

- FT-620, FT-621 - Calendar: Time Zones switching and display functionality
This feature allows users to control updating their own time zone within the Calendar to impersonate the view of other users. Viewing other time zones is useful for customers with patients or a presence in two or more time zones. 
Users involved in scheduling for other care team members can now view time zones in the calendar as seen by users in different time zones. This capability is also convenient when arranging Encounter times with a patient on the phone. 
Time Zone switching is optional, and can be enabled at the individual level in the User Profile view in Care.

- FT-739 - Update UI of clickable area in profile records in Data Views
This update enhances the behavior of the web links displayed in data views, letting links navigate to the web page the links point to. The behavior when clicking on the other values remains unchanged, navigating to the profile screen.



# Sisense Release notes: Version 2024.1.0

### Maintenance dates: Saturday Mar 23, 2024 – 12:01 AM EST through Monday March 25, 2024 - 6:00 AM EST

Customer Benefits/Highlights

Dashboard Designer Benefits
- Additional dashboard & widget layout presentation options provide dashboard designers additional tools to deliver stunning professional dashboards.
  
- Perspectives a more streamlined, business-focused interface for dashboard designers to interact with the data tables & fields while developing dashboards.
  
- The filter relationship editor allows dashboard designers to express filters in more advanced ways when required, such as nested OR conditions.
  
- The ability to customize the layout Of email-embedded scheduled dashboards significantly improves the viability of scheduling KPI dashboards to email. With this feature, dashboard designers can better control the presentation and layout of the resulting embedded dashboard.
  
- Improved formula and export functions, such as numbers formatting for CSV downloads & DateDiff support for Now(), and more...

Dashboard Viewer Benefits
- New dashboard filter bookmarks allows users to save their series of filters for quick access, improving productivity and efficiency.

- Improved performance & formatting when exporting To Excel
  
- High Resolution widget image downloads
  
Data Cube Designer Benefits
- Direct relations support enables joining data tables in a significantly more streamlined way, lightening data models, making them easier to maintain, and producing query results in a more predictable manner.
  
- Perspectives empower data designers to organize their data model into smaller, more business-focused sub-models, improving building and maintaining dashboards for dashboard designers.
  
- The data model list view allows data designers to see quick stats for their data model at a glance, such as the number of columns and rows per table.



# Release notes: Version 2024.43.0

### Release Date: Mar 26, 2024 – 1:00 AM PST (tentative)

## New Functionality

- CT-678 - Billing & Payments section in Encounters: Services and Modifiers
Following the update, it will be feasible to link a default service/CPT code, modifiers, and fee within the encounter template directly from the Designer. Such configurations will be automatically filled in (but are editable) when an encounter is initiated via the Care portal. All newly added fields seamlessly integrate with Candid Health and are set to be transmitted accordingly.
A new section has been introduced under the security policy titled ‘Billing & Payments’, designed to manage user permissions regarding visibility and interactions with billing and payments data.	

- FT-568 - Billing & Payments section in Encounters: Card Addition through the Care Portal Care portal users now have the capability to input card details manually within the Billing & Payments section found in Encounters.

## Improvements and Bug Fixes

- FT-714 (WS-3514) - Notification load optimization
This improvement focuses on optimizing the logic for loading notifications lists, resulting in enhanced loading speed.

- FT-773 (WS-3327) - Source_id and source_type fields in assessments export
This update ensures that assessments export now includes the source_id and source_type fields. 


# Release notes: Version 2024.42.0

### Release Date: Mar 11, 2024 – 1:00 AM PST (tentative)

## New Functionality

- FT-678 -  Enhancement of text area in table data view
This update enhances Textarea CDTF field values displayed in Data Views.  Data Views now allow the display of multiple lines of text in Care, 3 lines by default. It also allows you to see the full text box by selecting "Show more". Column width is now also auto-adjusted.

- FT-619 -  Predefined user attribute variable: Title
This update enables the User Attribute value “Title” to be utilized as a variable within Message Templates, Assessments, and other areas of Designer.


## Improvements and Bug Fixes

- FT-469 (WS-3324) - Notification does not lead to email on click
This fix addresses the issue with certain notifications not leading to the related email when clicked.

- FT-543 (WS-3387) - Hidden fields preventing completing assessments 
This update fixes the issue occurring sometimes where assessments were not available to be completed due to fields hidden by conditional logic.  

- FT-584 (WS-3441) - Unable to delete certain calendar events
This fix rectifies behavior of the system preventing deletion of certain events created via API.

- FT-481 (WS-3332) - Assessment pre-populates wrong values
This update addresses the issue when assessments pre-populate answers with option labels instead of option values.

- FT-511 (WS-3362) - Assignee filter behavior issue on the Tasks list screen
This item fixes the behavior of the Task filter for assignee that sometimes did not display the correct list on the Tasks screen. 


# Release notes: Version 2023.41.0

### Release Date: Feb 26, 2024 – 1:00 AM PST (tentative)

## New Functionality

- FT-485 -  Calendar UI improvements: Patient names in calendar events 
This update enhances the Calendar by adding patient names to be displayed on Encounters, as well as participants' names on Events. Additionally, the UI within the Calendar has been updated, streamlining the color logic to make it more straightforward and easier to understand.

- FT-500 -  Predefined user attributes to variables: License, NPI
This update enables the values of License and NPI User Attributes to be utilized as variables within Message Templates, Assessments, and other areas of Designer.

## Improvements and Bug Fixes

- FT-594 (WS-3455) - Encounter start date / time variable
This fix addresses the logic of populating the ENCOUNTER.*.startDateTime variable, ensuring accuracy. 


# Release notes: Version 2023.40.0

### Release Date: Feb 12, 2024 – 1:00 AM PST (tentative)

## New Functionality

- FT-341, FT-342, FT-515 - Encounter location: field and variable 
This feature introduces a new field within the Encounter to specify meeting details. Users can now include address details for in-person meetings or a video link and phone number for telehealth formats. The value of this new field is also available as a variable, which can be utilized in message templates for sending Encounter invites and reminders.  
Users also have the flexibility to set the field value when creating an Encounter, or they can pre-configure it at the template level in Designer. It's possible to link the field to a Profile that hosts addresses (such as company offices, clinics, meeting areas, etc.). This connection allows users to conveniently select the desired location from a dropdown menu when creating an Encounter, eliminating the need for manual entry of event details.

- FT-495 - Hide canceled events in calendar - saving preference
With this update, the state of the "Hide canceled events" checkbox in the calendar is now saved on a user-specific level. This enhancement ensures that users' preferences regarding hiding canceled events are retained, offering a more personalized and efficient calendar experience.


# Release notes: Version 2023.39.0

### Release Date: Jan 29, 2024 – 1:00 AM PST (tentative)

## New Functionality

- FT-433: Patient Payments Collection via Stripe
This feature enables the connection of a Stripe account, streamlining various transaction types. It empowers you to send payment links to patients via email, record cash transactions, charge cards on file within the context of Encounters, and initiate refunds directly within the Welkin platform. Furthermore, it offers users access to current Encounter balances and payment statuses, providing a comprehensive financial overview. For additional information, please reach out to your account manager.

## Improvements and Bug Fixes

- FT-419 (WS-3184): Notification Issue Related to Point of Contact Update
This update resolves the issue where clicking on notifications sent by the automation, which was triggered by the "Patient Point of Contact Updated" event, did not open the patient record.




# Release notes: Version 2023.38.0

### Release Date: Jan 15, 2024 – 1:00 AM PST (tentative)

## Improvements and Bug Fixes

- FT-445 - Writing Profile-Related CDT Variables to a Template
This update resolves the issue of displaying data in assessment templates, where certain CDTs source data from Profiles.

- FT-350(WS-3243) - Assessments Forms Order in PFA Folders
This update ensures that the order of Assessments in PFA folders aligns with the settings configured in Designer.

- FT-442(WS-3299) - Blank Encounters List Screen 
This addresses the issue of seeing a blank Encounters list screen when navigating from the Nth page of the Encounters list of a different patient.



# Release notes: Version 2023.37.0

### Release Date: Jan 3, 2024 – 1:00 AM PST (tentative)
## New Functionality

- FT-224 - Self-scheduling for Patients and Leads via Acuity
  - The integration with Acuity equips the Welkin platform with a self-scheduling interface, allowing patients the convenience of booking their own appointments directly. This functionality enables them to: 
       - Browse through a provider's schedule to see available time slots
       - Choose a time that fits their schedule for booking an appointment
       - Select the specific type of appointment they need
       - Find providers based on location and other criteria
   - Acuity self-scheduling can be embedded directly into your marketing website or shared as a link through email or SMS. When a patient books an appointment, they automatically receive an invitation with all the meeting details. This invitation can be customized using our new email template builder for a more personalized touch. Additionally, we can gather the required information before the appointment by incorporating an intake form into the notification template.
Please contact your account manager to learn more.


- CT-323 - Revenue Cycle Management via Candid Health
  - The integration between Welkin and Candid Health streamlines the insurance claim submission process, allowing for the immediate transfer of claims to Candid after an encounter is completed in Welkin. This system gathers and organizes all essential data needed for claim submission, including patient payments, and efficiently sends it to Candid. Moreover, it enables real-time tracking and monitoring of claim submissions directly within Welkin, providing up-to-date status information. 
  - On the Candid platform, users can track claims comprehensively from start to finish, automate the correction process, access valuable insights, and scale their digital health operations effectively. Candid Health serves as a trusted resource for comprehensive revenue cycle management.
Please contact your account manager to learn more.


- FT-156 - Creating tasks from unrecognized communications
New icons and buttons have been added within the Unrecognized Communications screen to initiate Task creation in the UI. This is designed for cases when users would like their colleagues to handle requests from Unrecognized Communications.



## Improvements and Bug Fixes

- FT-295 (WS-3208) - Incorrect Interpretation of Encounter Disposition Values by Automation
This update addresses the issue of incorrect interpretation of certain values in Encounter Disposition fields when an automation relies on them in conditions. 

- FT-351(WS-3244) - Incorrect User Name in Live Chat
This update fixes incorrect user names displayed in the Live Chat in certain cases when there were two or more users participating in communication.




# Release notes: Version 2023.36.0

### Release Date:  Dec 18, 2023 – 1:00 AM PST (tentative)
## New Functionality

- FT-120 - Periodical Data Synchronization for Dr. First
We are introducing periodic 5-minute data polling in addition to the existing synchronization upon logout in Dr. First, to enhance data retrieval. Both methods of synchronization will operate concurrently, ensuring more frequent and efficient data updates. Please note that the scope of the data being polled remains the same.

- FT-340 - Cross-patient Sticky Filters and Ordering
This feature now saves filters and ordering preferences for users as they navigate from patient to patient within various lists:
Assessments list
Encounters list within a patient
Tasks list within a patient

- FT-137 - Addition of “Notes” Field in Patient Data View
A new free-text field titled “Notes” has been added to the Patient Data View in Care. This field can be included in the Top Info section under “Edit Patient Data View” in Designer. If the “Notes” field is not empty, its contents will be displayed in red to draw staff attention. This feature is useful for highlighting critical information such as allergies or other important patient details.


## Improvements and Bug Fixes

- FT-163 (WS-3120) - Time Zone Issues when Creating Encounters
This update addresses the issue of incorrect time being displayed in certain cases within the "Already scheduled" element of the Encounter creation UI.

- FT-262 (WS-3184) - Misleading Notifications
This improvement focuses on enhancing notifications related to Encounters, Assessments, Tasks, and Programs. Clicking on notifications will now navigate users to the most relevant area of the system.

- FT-304 (WS-3221) - Encounter View Accuracy for Assessment Status
In certain cases, completed Assessments were inaccurately displayed as "Not started" in the Encounter UI. This fix rectifies this behavior. 

- CT-509 (WS-3034) - New Event "Task Updated" in Automations
Previously, when a task's status was updated, the system would publish either the TASK_COMPLETED or TASK_CANCELED event, but not TASK_UPDATED event. For updates to task fields, the system would publish a TASK_UPDATED event, but automations did not trigger on this event. 
This update introduces the following changes: 
When a task's status is updated, the system will now publish either the TASK_COMPLETED or TASK_CANCELED event, in addition to TASK_UPDATED
For updates to other task fields, the system will continue to publish TASK_UPDATED
Automations can now be triggered on the TASK_UPDATED event.  Configure this in Automations in Designer


# Release notes: Version 2023.35.0

### Release Date:  Dec 4, 2023 – 1:00 AM PST (tentative)

## New Functionality

- FT-95 - Profile Integration with Encounter Disposition:
This update allows for the integration of profiles with encounter disposition. Typically, entities such as services, procedures, diagnoses, pricing, etc., used as encounter attributes, are housed within Profiles. With this release  it is now possible to utilize profiles as a source for values in Disposition selection fields. Previously, the only method available was manual addition or update of values.

- FT-96 - Encounter Disposition Fields Based on Profiles in Automation Conditions:
This update introduces the capability to establish conditions in automations (triggered by Encounter-related events) based on specific values selected in the Encounter Disposition fields, where values are sourced from Profiles. 


## Improvements and Bug Fixes

- FT-12 (WS-3028) - Boolean Type Pre-population Fix:
This update addresses an issue where the pre-population of boolean types (radio buttons/checkboxes) was not functioning correctly in Data Views.

- FT-56 (WS-3048) - Date of Birth Format Correction:
An issue where the Date of Birth (DOB) variable was displayed in the format YYYY-MM-DD Thh:mm:ss.000Z has been rectified. It will now be presented in the MM/DD/YYYY format as expected.

- FT-265 (WS-3186) - Visibility Fix for Conditional Logic in Assessments:
The problem where certain questions with conditional logic were not visible to users reviewing assessments completed by patients has been successfully resolved.

- FT-209 - Calendar Page Table Rendering Issue Fixed:
This update addresses and resolves a rendering issue with tables on the Calendar page.



# Release notes: Version 2023.34.0

### Release Date:  Nov 20, 2023 – 1:00 AM PST (tentative)

## New Functionality

- FT-34 - CDT Arrays: CDT Arrays allow for the selection of multiple options within one assessment question or data view.  Previously, when creating a CDT linking a Profile with a Patient, users were limited to establishing one-to-one relationships. This restriction meant that, for example, if a Profile used ICD-10 as the answer option source for a diagnosis question in an assessment, users could only select a single option. The enhancement in this feature now allows for one-to-many relationships, enabling the selection of multiple options in scenarios similar to the one described above.

- FT-44 - A new action has been added to Welkin Automations: Generate and Send Assessment PDF to Patient. This feature is compatible with the 'Assessment Completed' event as a trigger and includes the ability to securely deliver the PDF via Paubox.

## Improvements and Bug Fixes

- FT-238 (WS-3169) - This update resolves a bug where scheduled emails were not being delivered to patient-related contacts and remained marked as 'scheduled' in the Communication Center.



# Release notes: Version 2023.33.0

### Release Date:  Nov 8, 2023 – 1:00 AM PST (tentative)

## New Functionality

- FT-25: Introducing the Email Template Builder, with a new user interface (UI) in the Message Templates section of Designer. This feature allows users to construct email templates from various built-in elements, such as buttons, text, images, columns, etc., and style them without the need to use HTML or CSS code directly. You can now effortlessly create branded emails, enhance your content for a more engaging experience, and seamlessly integrate call-to-action elements to improve the conversion rates of your campaigns.

- FT-145: We are introducing a Live Chat Download Policy, which allows you to restrict users from downloading files sent or received via Live Chat. By default, this policy is checked, meaning there are no restrictions applied to any users. To prevent downloading, you should uncheck this option. 
Note 1: If you are importing a Designer configuration that was exported before this release, it may cause the policy to become unchecked. In that case, please go to Designer and manually check it. 
Note 2: This policy is going to be renamed as “Files Download Policy” in a future release.


## Improvements and Bug Fixes

- FT-164 (WS-3118) This update resolves a bug in the Communication Center that occurred after clicking the Refresh button.  Emails now display the correct status after selecting Refresh.

- FT-162 (WS-3122) This update resolves the missing ability to edit assessments with certain required fields.  Assessment edits can now be made for all required and non required fields.



# Release notes: Version 2023.32.0

### Release Date:  Oct 23, 2023 – 1:00 AM PST (tentative)

## New Functionality

- FT-43 - A new checkbox option, "Secure Email (via Paubox)," has been added to the "Email patient" automations action. This allows you to automatically send secure emails to patients via Paubox, enhancing the security of your patient communications.

# Release notes: Version 2023.31.1

### Release Date:  Oct 9, 2023 – 1:00 AM PST (tentative)

## New Functionality
- FT-8 - Create a Task from communications: This feature allows users to create Tasks from messages, including chat, emails, and SMS, and assign the Task to themselves or other users. This functionality is especially useful when a patient requests something that cannot be fulfilled instantly, and a Task can be created as a reminder.

- WEL-6649 - Files Screen in the Communications Center: Introducing the new "Files" screen within the Communication Center, which presents a table listing all files sent or received via any communication channel. Items in the table are listed in chronological order. Users can download or preview files in the full-screen viewer, and they can also open them in a separate browser tab for multitasking. For example, you can open a voice message and fill out an assessment while listening to it.

- WEL-6650 - Files filters (related to WEL-6649): This feature adds filtering capabilities to the Files table, making file searches even simpler. Users can filter files by date, file type (image, text, audio), and communication channel (Email, SMS, Live Chat, WhatsApp).

- WEL-6648 - Chat UI Export permission: Users can download the Live Chat history of patients through the new user interface (UI), as a file. To access this feature, users should have the "Chat UI Export" policy enabled.

## Improvements and Bug Fixes

- WEL-7688 (WS-2869) - This update fixes a bug that was preventing the attachment of documents when communicating with Related Contacts, which are contacts related to patients and created from their profiles.

- FT-39 (WS-3047) - A minor UI issue has been fixed where a close button was erroneously appearing while choosing an option for sending a document via DocuSign.


# Release notes: Version 2023.30.1

### Release Date:  Sept 25, 2023 – 1:00 AM PST (tentative)

## New Functionality

- WEL-7118 - Updated the permission logics covering Assessments within Encounters. Users no longer need Encounter Update permissions to update and complete such Assessments.


## Improvements and Bug Fixes

- WEL-7827 - Renamed the Delete button, which appears in the drop-down menu behind the ellipsis icon in the Encounter list, to Cancel. This name is more relevant to its action.  

- FT-36 (WS-3037) - Corrected the inaccuracies occurring in certain cases with the Started Date and Completed Date in the Assessment list within Encounters.


# Release notes: Version 2023.29.1

### Release Date:  Sept 11, 2023 – 1:00 AM PST (tentative)

## New Functionality

**WEL-7606 "I am on it"**
- Introducing the "I am on it" button for notifications sent to multiple users. This feature allows users to indicate their intention to take care of a related activity themselves, improving team efficiency, and reducing distractions.

**Benefits:**
- Reduced Distraction: Users can signal their commitment to handle notifications, reducing distractions for others.
- Improved Coordination: Minimize cases where multiple users act on the same notification simultaneously, optimizing workflow.
- Workload Distribution: Facilitate the equitable distribution of tasks within the team, promoting teamwork.
- Supervisor Oversight: Enable team supervisors to track which notifications are yet to be addressed by the team, ensuring comprehensive coverage.

**How it works:**
- Activation: This feature can be activated by the admin through the Notifications section.
- Archiving Notifications: Users can click the "I am on it" button within the notification. This action archives the notification copies sent to other users, indicating that they will take responsibility for the related task.
- Archived List: The archived notifications are accessible to other team members in a dedicated "Archived" list. The list includes labels indicating which user archived each notification.
- Undo Functionality: Users who initially clicked "I am on it" can undo their commitment by clicking the button again. This action returns the archived notification from the "Archived" list back to the "All" notifications list, making it available for others to address.

**WEL-7606 Editing Completed Assessments**
- Now, users have the ability to edit completed assessments, a functionality previously unavailable. This feature allows for the addition of extra information, correction of typos, and updates to previous selections, enhancing assessment accuracy and completeness.

**How it works:**
- Permission Control: Admins can grant the "Update completed" permission to specific users and specific forms, offering fine-grained control over who can access this feature.
- Permission Location: The "Update completed" permission can be configured in the Security Policy -> Patients -> Forms section, ensuring secure and organized permission management.
- Label and Timestamp: Edited assessments receive a special label with a timestamp in both the viewer (Drawer) and assessment lists, making it easy to identify and track changes.
- Audit Log: A record of assessment edits is automatically added to the audit log, providing transparency and accountability in the editing process.
- PDF Regeneration: After editing, the PDF version of the assessment is re-generated and appended to the assessment document, ensuring that the most up-to-date information is available in all formats.


# Release notes: Version 2023.28.1

### Release Date:  Aug 28, 2023 – 1:00 AM PST (tentative)

## New Functionality
- WEL-7699: Addresses the issue of error messages arising when the system logs out users. A new dialog will now appear as the session approaches its expiration, offering users the opportunity to extend it.

## Improvements and Bug Fixes
- WEL-7607(WS-2802): Resolved an issue where automations triggered by Encounters updating were erroneously firing twice in certain cases.
- WEL-7727(WS-2916): Rectified an issue that occasionally led to the display of incorrect assessments in the patient assessment list screen when transitioning from the Encounter screen.

# Release notes: Version 2023.27.1

### Release Date:  Aug 14, 2023 – 1:00 AM PST (tentative)

## New Functionality
- WEL-7037: Enabled the deletion of patients via an API endpoint. Please note that once deleted, this action cannot be undone. For more details, refer to the API documentation.
- WEL-7218: The Assessments drawer (viewer) can now be collapsed. Users can now collapse it, navigate to a different section within the patient layouts, and expand the drawer back when needed.
- WEL-7497: Phone Names' source is now exclusive to Designer (previously they were managed via support). Following the recent update, Phone Names are created and edited in Designer and associated with phone numbers in Admin.
  
## Improvements and Bug Fixes
- WEL-7686 (WS-2894, WS-2904): Task priority interaction issue resolved. Fixed a user interface problem where selecting values in the Priority field was difficult.
- WEL-7705 (WS-2858): 500 Error when attempting to delete a patient.  The 500 error that sometimes occurred when deleting a patient has been resolved.
- WEL-7512: Permissions for working with Contacts via the API.  Permissions to work with contacts via API are now tied in Designer to permissions to work with a patient.  To manage Contacts, you will need Patient read and update permissions (Patients -> General -> My Patients) in the Security Policy for your API.

# Release notes: Version 2023.26.1

### Release Date:  Jul 31, 2023 – 1:00 AM PST (tentative)

## New Functionality
- WEL-7310 - With the release in Live Chat, it became possible to work with audio files. Audio tracks can be sent, received, listened to, forward and rewind, downloaded and opened in a new tab. The system supports mp3, ogg, wav audio formats
- WEL-7522 - The function of resending a message has been added to the Live Chat. If the message was not delivered, then a "Failed" status will be displayed. The user can resend the message by clicking on the validation message.
- WEL-6851 - With the release, a new "Chat Files Download" security policy for Live Chat has been added to Designer. This policy controls the ability to download files when working with Live Chat. This policy is disabled by default.
- WEL-7192 - International Phone Number Handling. To improve work with Phone type fields, the ability to select a country from the list has been added. After selecting a country, the country code is displayed in the field so that the user does not have to enter it manually. For the convenience of the user, the country that is set in the locale in the user profile will be set by default (US, Singapore, Australia, UAE). PFA forms will also default to one of the 4 system countries, if the patient's locale does not match one of the 4 locales, then the US will be the default. 
- WEL-7172 - With the release, a new Encounter condition was added under the Automation settings. When choosing the Entity Type of 'Encounter', the user must specify the Delivery Method (In-person, Call, Video), too. Also, for convenience, information about the delivery method of the encounter has been added to Actions. When choosing the "Encounter" action, an "i" icon was added to the template field, when hovering over it, the user can find out the Delivery Method of the template.
- WEL-7152 - It is now possible to click on links in task descriptions within Care. If the cursor is in the focus of the Description field, then the link will be in edit mode. As soon as the focus is removed from the field, the link will become clickable and will launch into the links associated URL.


## Improvements and bug fixes
- WEL-7336 (WS-2657) - Unrecognized Australian patient SMS message. Work with phone numbers has been improved to avoid confusion with unrecognized communications. The system recognizes national and international phone numbers as being different from each other.  If the user enters the phone format in the national format (with an additional zero), then after saving the zero will be automatically deleted and the phone format will be converted to international. There will be no automatic phone conversion for the API, it will display an error related to the phone format. The public API documentation will be updated with more information about the phone format.
- WEL-7431 - With the release “Contacts” have been renamed to “Related contacts” in the system.
- WEL-7635 (WS-2829) - Get Patient by ID endpoint returns Patient Program information as empty. The problem with empty information has been fixed. 
- WEL-7613 (WS-2809) - Unable to save changes to Scoring Groups. This has been resolved - changes to scoring groups can now be saved.  
- WEL-7592 - Fixed an issue where the “Clear All” button did not clear the search box on the Patients page.


# Release notes: Version 2023.25.1

### Release Date:  Jul 17, 2023 – 1:00 AM PST (tentative)

## New Functionality
- WEL-7223: Enhanced User Experience for Accessing Welkin Resources. An improvement has been made to the system's behavior when users attempt to access Welkin resources, such as opening links to assessments, without authentication. Previously, users encountered an error message stating "This page can't be found" and were redirected to the home page after logging in. However, with the latest release, the system now verifies the user's authentication status and access rights before proceeding. If the user is not authenticated, they will be presented with a login screen. After successful login, they will be directed to the intended page associated with the accessed link.
- WEL-7385: Seeing and Copying Long Titles in List Field. In certain scenarios, long titles in list fields were being truncated due to their excessive length, making it impossible to view the complete content. Now, to access the full value, users simply hover over the field and pause for a moment. The complete name will be displayed in a tooltip, along with a copy button. This functionality applies to both the Care and Designer portals, providing an improved user experience.



## Improvements and bug fixes
- WEL-6927 (WS-2386): Handling of Null Values in the Designer Configurations. Previously, an error was displayed when working with configurations in the Designer, specifically when encountering config files containing null values. The system now accepts null values so that errors will not be displayed when one is present within the configuration. 
- WEL-7319 (WS-2652): Improved Display of "Not Set" Option for List-Radio Type in Assessments. In the past, there was an issue where the "Not Set" option would be displayed for the list-radio type in assessments, even when it was not configured in the Designer. Now, for required fields, the "Not Set" option will no longer be displayed. However, for optional fields, the 'Not Set' option will still be available. This allows users the flexibility to choose "Not Set" in case they accidentally select an option and wish to reset it.
- WEL-7498 (WS-2721): Inaccurate "Completed By" value for Reassigned Assessments. Previously, the "Completed By" field would inaccurately display the name of the user who reassigned an assessment to another Encounter, even though they were not the actual completer of the assessment. This behavior has been addressed. The system now accurately displays the name of the user who completed the assessment, ensuring that the "Completed By" field reflects the correct completer's name.
- WEL-7467 (WS-2721): Fix for assessment completed day in the drawer. Previously, the assessment drawer displayed the updated date instead of the completed date. The correct assessment completion date is now displayed in the drawer.

# Release notes: Version 2023.24.1

### Release Date:  Jul 3, 2023 – 1:00 AM PST (tentative)

## New Functionality
- WEL-7220 - Introducing “Contacts” endpoints for API clients. With the goal of streamlining contact management for the "Communication with Patient Representatives" feature, we have developed an API that significantly simplifies the process.This API allows clients to easily retrieve, create, and update patient related contacts. New endpoints will be added to the public collection in Postman,  along with essential details about each request.
- WEL-6624 - Support of Media files in Live Chat. With the latest release, we have introduced support for media files within the Live Chat module. Welkin users can now send and receive PNG, PDF, and JPEG files seamlessly during live chat sessions. Additionally, files can be viewed in full-screen mode and easily downloaded and opened in a new tab. For comprehensive guidance on utilizing the API, the Postman public collection will be updated with the latest information.
Please be aware that the successful sharing of media files relies on ensuring compatibility with the recipients' application, as it should support the specific media file formats being transmitted.



## Improvements and bug fixes
- WEL-7432 - Auto-assigning unrecognized communication. We have made enhancements to the logic of the Default assignee field. Now, when configuring the Default assignee field, it is possible to select only those patients whose email or phone number matches the incoming unrecognized communication. This improvement ensures that the assignment of default assignees is more accurate and aligned with the specific criteria of the incoming communication.
- WEL-7472 - Resolution of WhatsApp Message Order Issue. We have implemented a fix to address an issue regarding the display order of WhatsApp messages that were sent during the AWS outage experienced last week. This fix is specifically designed to rectify the incorrect message ordering, ensuring that the messages are now displayed in the correct chronological order as intended.



#Release notes: Version 2023.23.1**

### Release Date:  Jun 19, 2023 – 1:00 AM PST (tentative)

## New Functionality
- WEL-6786 - Auto-assign for Unrecognized Communications: In certain cases, there may be multiple patients, patient-related contacts, or a combination of both, who share the same phone number or email in the profile. When a new SMS, email or a call arrives from such a number, it is directed to the Unrecognized Communications section. During an active text message exchange, the user needs to navigate to this section every time to assign the SMS to the appropriate patient. To streamline this process, we are introducing an auto-assign feature. This feature allows you to choose a patient or patient related contact as the default assignee when assigning a message or call to a patient. Once set, the system will automatically route incoming communications to the assigned patient's Communication Center until a different default assignee is specified or the default assignee is removed. 
Please note that the Default assignee field will only be displayed if there are duplicate email or phone numbers in the system.
- WEL-7247 - From Number Configuration for SMS automations: We have introduced a new feature that allows users to specify the sending phone number, thereby improving SMS-related automations and creation of draft SMS for customers who utilize multiple phone numbers. 
A new section called Phone Names has been added in the Designer Portal, it allows you to create names for phones, which can be referenced during automation configuration. To associate names with phone numbers, you will need to indicate the correspondence between the phone and the name within the Admin Portal's Integrations tab, specifically the Communication page. If a name is specified in an automation but no phone is associated with that name, the automation will not be executed, and this can be tracked in the automation logs.
The assigned phone names will also be displayed in the Care Portal's Communication Center, specifically in the "From" field. Additionally, you can find these phone names in the Designer Portal's Phone Trees page.
It is possible to leave the "From" number empty in automation. In this case, the system will behave as it does currently and use the phone number marked as "Main" in the admin settings.
Please note that the phone number selected for the automation will take precedence over a phone number set as default on a patient profile. In other words, if you have configured a default number for a patient, it will only be utilized if no specific phone number is chosen for the automation.
At present, certain phones are already assigned names through Welkin's internal admin system, managed by our support department. However, our future plans involve phasing out these names and exclusively showcasing the phone names established within the Designer Portal. This modification will grant you, as our client, the ability to independently manage the names instead of relying on support. We kindly request you to replace the existing labels by generating your own within the upcoming two weeks, preferably before July 3rd.
Currently, some phones already have names assigned through Welkin's internal admin system, managed by our support department. However, we plan to decomision these names in the future and display only the phone names set within the Designer Portal. This change will allow you, as our client, to manage the names yourself instead of relying on support. We kindly request that you replace existing labels by creating your own within the next two weeks, preferably by July 3rd.


## Improvements and bug fixes
- WEL-7034 (WS-2624): Users are unable to change phone numbers in their profiles. We have addressed the issue where some users were unable to modify their data on the Care Portal.
- WEL-7201 (WS-2585): Required fields are not highlighted properly when empty. We have addressed the problem where required fields, which are connected to condition logic, were not appropriately highlighted in certain scenarios. This issue has been fixed, and now required fields will be correctly highlighted as intended.
- WEL-7282 (WS-2606): Fix for Last Record CDTF Field Not Populating in Forms: We have fixed the issue related to the Last Record CDTF field not populating correctly. This problem specifically affected fields of the List type. 
- WEL-7295 (WS-2626): Fix calling through encounter. The call drawer now opens immediately when a user clicks on a phone number in an encounter.
- WEL-7372 (WS-2681): Unable to call Get Patients list by PDT. It was noticed that the "Get Patients List by PDT" endpoint was inaccessible, despite being documented as open and supported in the Welkin Public API. We have addressed this issue and you should now be able to access the endpoint as intended.



# Release notes: Version 2023.22.1

### Release Date:  Jun 5, 2023 – 1:00 AM PST (tentative)

## New Functionality
- WEL-6646, WEL-6647 - Introduction of emoji support in Live Chat. Users can now utilize unicode emojis in their Live Chat conversations, allowing them to send and receive emoji seamlessly.
- WEL-6897 - Enhanced chat design and readability. Notable changes include the relocation of the search field to the right side for improved accessibility. Moreover, messages from logged-in users are now displayed on the right side, while messages from patients and other care members appear on the left side. Additionally, the sender's First and Last Name are now shown for messages, with the label "Patient" assigned specifically to patient messages.
- WEL-5741 - Open Profiles APIs for external users. Profiles in Welkin are “generic” objects that can represent individuals as well as non-person lists such as ICD-10, CPT codes, family members, doctors, and non-Welkin care staff, etc. Profiles are backed by CDT's, so it’s possible to customize them. With this release, we're enabling the ability to interact with Profiles (including actions like get, create, and update) through our API. Documentation is available in the Welkin Public collection on Postman.


## Improvements and bug fixes
- WEL-7129 - Scrolling when adding regions/territories. In the Admin portal, an automatic scrolling feature has been implemented to ensure that the "Add Region" button is always visible while adding regions and territories to users.
- WEL-7032 (WS-2453) - Appointments not appearing on the Homepage. The issue has been fixed where appointments were not appearing on the Homepage for users with a large number of associated policies.
- WEL-7070 (WS-2497) - Assessment record retrieval with disabled / deleted physicians. Empty entries will no longer occur when the profile field is deleted.
- WEL-7240 (WS-2617) - Blank assessment drawer. Floating bug addressed in encounter assessment, preventing a blank drawer from being displayed.
- WEL-7124 (WS-2527) - Added pagination for Program view. Program view pagination has been implemented to address the previous limitation of displaying only up to 20 programs.
- WEL-7120 (WS-2544) - Incorrect Zoom links displayed for encounters. Resolved an issue when instead of showing the care team member's Zoom link for encounter, it displayed the viewer's own Zoom link. This problem has been fixed, and now the appropriate Zoom link associated with the encounter is shown for all users.


# Release notes: Version 2023.21.1

### Release Date:  May 22, 2023 – 1:00 AM PST (tentative)

## New Functionality
- WEL-6412 Communication with patient representatives. This feature is designed to empower customers in facilitating communication between their users and third-party entities associated with patients, such as legal guardians, providers, and relatives. It utilizes the comm center as a means of communication.
According to Welkin's design, these entities should be stored within profiles. To make a profile record contactable, two requirements must be met: 1) it should be linked / added as a contact to a patient, and 2) it should belong to a profile with the "contactable" switch enabled in the Designer, which is introduced as part of the current feature.
Once these conditions are fulfilled, communication icons will appear next to phone numbers and emails on the profile record within a patient's screen. Care users have the freedom to click on these icons to initiate communication with the relevant entities. Clicking on an icon will redirect the user to the comm center, where all standard features, including making and receiving calls, sending SMS, and emails, are available. Detailed instructions will be provided shortly.
- WEL-7102 (WS-2528) - Ability to copy the link to the assessment. In the assessment drawer, a sharing function has been added, featuring an icon located at the top right corner. By clicking on this icon, users can easily copy the link to the specific assessment. Regardless of whether the link was copied within the context of an encounter, it will consistently direct the recipient to the assessments page. It is important to note that the link to the assessment will only be accessible for viewing if the user has the necessary rights to view that particular assessment. Furthermore, the link contains an assessment ID, which helps identify and access the assessment accurately.
- WEL-7135 - Add Mandarin language. With the release, Mandarin has been added as a language option to the user and patient profiles. 
- CT-11 - Exporting Chat and WhatsApp Messages Using the Export API. With the latest release, users now have the ability to export chat logs through the Export API. Additionally, these exported logs can be uploaded to an S3 Bucket for further analysis and utilization in Sisense. Please keep in mind that in order to export the data, it is necessary to enable the CHAT and WHATS_APP policies in the Export Data section of the Security Policy page in the Designer.


## Improvements and bug fixes
- WEL-7055 (WS-2496, WS-2537) - Clicking to encounters page after using new "assign to encounter" feature filters encounter list to in-progress only. Fixed incorrect behavior of filters when assigning an assessment to an encounter.
- WEL-7105 - To improve the readability of the label for phones, the location of the From and To fields in the SMS and Call drawers has been changed. Now the fields are located under each other so that users can see most of the phone’s label.
- WEL-7061 -  “Select All” option for Territories field in API client configuration. An option to “Select All” has been added when editing “Accesses, Policies, Roles, Territories” for API clients in the Admin portal.



# Release notes: Version 2023.20.1

### Release Date:  May 10, 2023 – 1:00 AM PST (tentative)

## New Functionality
- WEL-5783 (WS-1476) - Ability to view images in SMS and emails in browser. The capability to view images sent via SMS and emails has been incorporated into the Communication Center, thereby eliminating the need for downloading.

## Improvements and bug fixes
- WEL-6930 (WS-2381) - Calendar event time zone jumps while editing. Fixed the problem when users with different time zones work with the same events.  When a user created an event in their timezone, and another user in a different timezone accessed the event to edit, the event time was automatically changing to the timezone of the second user.
- WEL-7069 (WS-2503) - Not able to send chat if not in the care team. Fixed an issue with security policies for Live Chat where a user with access could not write a message in the chat.


# Release notes: Version 2023.19.1

### Release Date:  April 26, 2023 – 1:00 AM PST (tentative)

## New Functionality
- WEL-6878, WEL-6879 - Assign and remove assessments to/from an encounter. You can assign an assessment to an encounter by clicking the "Assign to Encounter" button in the assessment drawer if the drawer is opened from the assessments page. Please note that it is only possible to assign an assessment to an encounter if it has not already been associated with another encounter. To remove an assessment from an encounter, simply click on the "..." icon next to the assessment you wish to remove in the corresponding encounter, and then select the "Remove (Unassign)" button. If you need to link the removed assessment to an encounter again, you can do so using the assign functionality.
- WEL-6875 (WS-2197) - Notification grouping improvement. In this release, we have made an improvement to the notifications block by grouping notifications based solely on their date rather than both date and time as was done previously. Additionally, to improve user experience, we have included a sticky date that will remain visible when scrolling through the notifications. This enhancement makes it easier for users to quickly identify and navigate through their notifications.
- WEL-6936 (WS-2064) - Display the number of unread notifications on the notification bell. We have made an update to the Care portal's notification bell with this release. Instead of the previous red dot indicating the presence of unread notifications, the notification bell now displays the actual number of unread messages. If the number of unread messages exceeds 99, the notification bell will show "99+" to indicate that there are more than 99 unread notifications. This enhancement provides users with a more accurate and informative representation of their unread notifications.
- WEL-6921 (WS-2262) - Change to Read All button behavior in the Notifications drawer. In the notification block of the Care portal, we have made a change to the behavior of the Read All button. Previously, the button was hidden if there were no unread messages in the list. However, with our latest update, the Read All button will now remain in place but become inactive when there are no unread messages to read. This change allows for consistency in the placement of the Archive All button, which will replace the Read All button when users have unread notifications.
- WEL-6876 (WS-2189) - Enhanced Validation for empty required fields in PFAs. We have enhanced the functionality of the system when working with PFAs. If a required field is left empty, clicking the Next or Complete button will now prompt the system to scroll to the empty field and display a validation message indicating that the field must be filled out before proceeding. This improvement ensures that users are notified of any missing required fields and helps to streamline the process of filling out PFAs.

## Improvements and bug fixes
- WEL-6874 (WS-2336) - Fix of Patient contains non-existent territories error due to extra space in name. Previously, the system was displaying an error message indicating that the patient contains non-existent territories due to extra spaces in the territory names. This error occurred when there were unnecessary spaces at the beginning or end of a territory or region name. To address this issue, we have implemented a fix that will remove any unneeded spaces in the names of the objects at both the start and end, thus preventing this error from happening again.
- WEL-6932 (WS-2371) - Graph Not Updating Correctly When Changing Date Range Manually. Previously, users encountered an issue where the graph would not update properly after manually changing the date range (i.e. entering dates instead of selecting from the dropdown options) for a second time. Specifically, the graph would only reflect the changes made during the first manual update. With our latest release, we have resolved this issue and the graph will now accurately update with any subsequent manual changes to the date range.
- WEL-6961 (WS-2376) -Issues with recording phone calls. We resolved an issue where calls were not being recorded correctly due to double recording. There are two webhooks for call recording: one for the call made to the user (child call) and another one for when the user hung up while the patient was still on the call. In some instances, the second webhook would overwrite the first one. This second webhook was commonly used when all users were busy and no one picked up the call. With our fix, this issue has been addressed and calls will now be recorded properly.



# Release notes: Version 2023.18.1

### Release Date:  April 10, 2023 – 1:00 AM PST (tentative)

## New Functionality
- WEL-6865 - Allow saving valid phone numbers with a country code of any country. With this release, the ability to save a valid phone number for any country has been added. This has been added for both the patient and the user. When using communications such as SMS or calls, please note that the appropriate country-specific settings must be set. Please contact support if you want to connect communications for a new country.
- WEL-6870 - Custom patient profile field data for Sisense export. This release adds the ability to export custom patient fields to Sisense. 
- WEL-6877 - Displaying encounter indicator on assessment at assessments list. With this release, a new column titled "Encounter" has been added to the header row in the Assessments menu. An icon is displayed if the assessment is associated with an encounter. When a user clicks on an assessment that is 'In Progress' and is associated with an encounter, the encounter's name, and scheduled date and time are shown in the opening drawer of the assessment's header. Clicking on the encounter's information will take the user to the encounter's view.


## Improvements and bug fixes
WEL-5263 (WS-1489) - "Territories of user and patient are not matched" error populates on Home Page if a user has an event with a mismatched patient. Fixed message display issue; now events related to a mismatched patient will not be displayed on the home page.




# Release notes: Version 2023.17.1

### Release Date:  March 27, 2023 – 1:00 AM PST (tentative)

## Improvements and bug fixes
- WEL-6720 (WS-1676) - Forms on mobile - scroll to the top. With this release, the behavior in PFA assessments has been improved, after a patient goes to the next page, the new page is automatically scrolled to the top of the page. The user will see the first question on the new page instead of having to manually scroll to the top.
- WEL-6845 (WS-2292) - Form dropdown scrolling for mobile. Improved behavior for the dropdown fields in PFA assessments on mobile devices. The ability to search for values, by typing, was removed on mobile devices, because the keyboard's appearance made it difficult to see the last values in the list.
- WEL-5998 (WS-2041) - Boolean field in Patient Fields does not display correctly in Patient Data View. Fixed the problem of displaying Boolean values in the patient table in the Care portal.
- WEL-6721 (WS-2191) - PFA Branding and Data Type Display issues. Fixed the problem with the logo displaying incorrectly in svg format for the PFA assessments.
- WEL-6746 (WS-2214) - Tasks Bug - can't find team members. Resolved an issue in the user filter where users were unchecked when using search in a field.
- WEL-6777 (WS-2230, WS-2280) - Secure emails are stuck in the "sending" state. Fixed issue displaying the correct status for secure emails.
- WEL-6797 (WS-2238, WS-2348) - Search by profile field with more than 2000 records. Fixed search problem in profile fields when filling out assessments with more than 2000 entries.
- WEL-6853 (WS-2296) - Time zone issue in Account Created On field in patient summary view. Fixed an issue where the “Created at” field was displayed in the UTC time zone instead of the user's timezone.



# Release notes: Version 2023.16.1

### Release Date:  March 13, 2023 – 1:00 AM PST (tentative)

## New Functionality
- WEL-6372 - Option to control the frequency of wait message repetition in the Phone Tree. A new setting has been introduced to the Phone Tree configuration which allows a Welkin Admin user to control whether a wait message should be played multiple times until the final action is taken, or only once.
- WEL-6598 - "Busy" status for phone calls in Comm Center. The system now includes a "Busy" status, which is displayed when a phone call to a patient is attempted, but a busy signal is received. The status is now available in the Comm Center within the Care Portal, Audit Logs, and API responses. 
- WEL-6619 - Trigger automation for new document upload. A new trigger criteria has been added to Automations.  This allows an action to be triggered when documents are uploaded via the Care web interface. API, or when a new document is created from an attachment in the Comm Center.
- WEL-6704 - Select All option for Territories field in user configuration. An option to "Select All" has been added when editing "Accesses, Policies, Roles, Territories" for a user in the Admin portal.
- WEL-6805 - Expand the list of supported Patient Profile variables. The system now includes new general variables that can be utilized in Assessments, PFA folders, Message Templates and Action Bar for custom buttons.
{{PATIENT_CITY}}
{{PATIENT_STATE}}
{{PATIENT_ZIP}}
{{PATIENT_COUNTRY}}
{{PATIENT_ADDRESS_LINE_1}}
{{PATIENT_ADDRESS_LINE_2}}
- WEL-6740 (WS-2191) - Support of Primary Team Contact variables in PFA folders. PFA folders now have the capability to utilize variables that can display information about a patient’s Primary Team Contact, such as their name, phone number, or email, on the Welcome and Conclusion pages.
- WEL-6622 (WS-2114) - Expose Export Patient Programs API. The Export Patient Programs API is now part of Welkin's Public API collection and is accessible for use by API clients if “Program” security policy is active in the Export Data section.
{{url}}/{{tenantName}}/{{instanceName}}/export/PATIENT_PROGRAM


## Improvements and bug fixes
- WEL-6676 (WS-2164) - Altered time data when typing in the time field. The problem of the system changing time data entered via the keyboard in an incomplete format e.g. without AM/PM has been resolved.
- WEL-4300 (WS-523, WS-565) - "Today's date" variable is showing the wrong date. The Date/Time field is now tied to the time zone of the user who is filling in the assessment. If it's a PFA, then the field value is linked to the patient's time zone, which is configured in their profile. If neither the user nor the patient has a time zone specified in their profile, then UTC is used. For the Date field, it is dependent on the time zone of the user filling it in. In the case of PFAs, the date value is recorded when the link is sent, taking into account the user's time zone. If a time zone is not set in the user’s profile, then UTC is used. When submitting a PFA through an automation, the UTC value is used.
- WEL-6027 (WS-1709) - Assessment drawer resizing is not limited to browser width. UI improvement that prevents a user from expanding the drawer to greater than the width of the browser screen.
- WEL-6504 (WS-2042) - Not possible to create a task for a patient that is assigned to a deleted care team member. The problem of being unable to create a task for a patient whose assigned care team member had been removed from the system has been resolved.
- WEL-6719 (WS-2190) - Calculated scores return a NULL value via Export API. The issue where score values were not being returned by the Export API has been resolved.
- WEL-6700 (WS-2176) - Copying user profiles in Admin does not carry-over regions/territories. An issue has been resolved in the Admin portal where regions and territories were not being carried over when user profiles were copied.
- WEL-6699 - "Press 1 to connect to patient" Phone Tree message is repeated three times. The optional message for phone tree is now repeated three times instead of being played only once. If the message is played thrice and the user doesn't press 1 to confirm a connection, the call will be disconnected in 5 seconds.



# Release notes: Version 2023.15.1

### Release Date :  Feb 27, 2023 – 1:00 AM PST (tentative)

## New Functionality
- WEL-6503 - User locale support for Australia (AUS) and the United Arab Emirates (UAE). With the release, it is now possible to select the Australian or United Arab Emirates locale for the user. When setting the locale for the user, the dates and times are displayed in the format of the selected country in the Care portal (Australia AUS → day-month-year format, 12-hour time format; UAE → day-month-year format, 12-hour time format), as well as placeholders for the field phone (Primary Phone and Secondary Phone in the patient profile). The locale can be set when creating or editing a user in the Admin Portal, as well as in "My Profile" on the Care Portal.
- WEL-6585 - Time zones for Australia and the United Arab Emirates. With the release, it is now possible to select the Australian or United Arab Emirates time zones for the user and patient. The time zone can be set when creating or editing a user in the Admin Portal, as well as in the "My Profile" section of the Care Portal. For a patient, the time zone is set in the patient profile. 
- WEL-6577 - Add timestamp to encounter history log. On the view of the encounter, a timestamp has been added to all History blocks (Details block, Notes and Ratings block, View Meeting Location block, Comments block).

## Improvements and bug fixes
- WEL-6686 (WS-1078) - An incorrect version of a template is used to generate PDF for assessments there were completed prior to 11/24/2022. After the release, the system will utilize the template version that was current at the time the assessment was completed to generate a PDF.
- WEL-5614 (WS-1757, WS-1756) - Users are being kicked out multiple times per day with JWT token errors. Fixed an issue with users being logged out by reworking the authorization logic and changing the approach for updating tokens in the application.
- WEL-6001 (WS-1669) - Time shift for recurring events in the calendar. The problem of time shift for recurring events due to daylight savings time has been fixed.
- WEL-6613 (WS-2067) - Production notifications are appearing in Stage. Addressed the problem when notifications from a different environment were being displayed to users under specific circumstances.
WEL-6712 (WS-2170) - API Create Assessment Record. An error that prevented retrieval of assessment information by ID through the client API has been fixed.
- WEL-6767, WEL-6768 (WS-2219) - Phone number entry validation. The validation process for phone number entries has been enhanced to allow only phone numbers with valid extensions to be stored in the system. Furthermore, the validation message will now specify that the phone number must be entered in international format and include a (+) symbol when entering details in the Care portal and PFA links.
- WEL-6771 (WS-2229) - International phone number + Automation Condition. A problem that prevented triggering of an automation when a phone number was included in the triggering condition has been resolved.
 

# Release notes: Version 2023.14.1

### Release Date :  Feb 13, 2023 – 1:00 AM PST (tentative)

## New Functionality
WEL-6502 - Support of AUS and UAE phone numbers. With the release it’s now possible to enter Australian (+61 x xxxx xxxx) and United Arab Emirates (+971 x xxx xxxx) phone formats for users and patients.

## Improvements and bug fixes
- WEL-6113 (WS-1708) - On/off toggle appearing for custom data type. The issue has been fixed where custom fields that have a similar name to the default profile fields were showing on/off toggles.
- WEL-6439 - The problem of displaying working hours in the calendar. The issue of incorrect display of working hours for users with significant time zone differences has been resolved.
- WEL-6575 - There is no validation message for the Date and Date/Time fields in the patient profile. The problem of missing validation messages for required date or datetime fields in the patient profile has been fixed.




# Release notes: Version 2023.13.1

### Release Date :  Jan 30, 2023 – 1:00 AM PST (tentative)

## New Functionality 

- WEL-6292 - Automation for Live Chat messages. With the release, "Chat message received" event was added to the automation list of events in the Designer portal to trigger an automation for an inbound message in the Live Chat. Additionally, the "Message" condition can be used in conjunction with this event to create specific automation rules for incoming messages.

## Improvements and bug fixes

- WEL-6491 (WS-1943, WS-2039, WS-2100) - Adding unique identifiers for notifications to prevent duplicates. A unique identifier hidden from users will be added to every notification in the Care portal to prevent duplicate messages. Extended call logs have also been added. 
- WEL-5646 (WS-1489) - User seeing error message "Territories of user and patient are not matched". Fixed the problem of filtering records to which the user does not have access.
- WEL-5891 (WS-1592) - Calls not showing up on schedule under encounters but show up on calendar view. Fixed an issue with displaying encounters related to the user's timezone.
- WEL-6434 (WS-2015) - "Terminate after inactivity" setting not saving time frame if <1 day. Fixed an issue where it was not possible to save 0 days in the settings in the Admin portal.
- WEL-6444 (WS-2022) - Can't add new user - getting error. Fixed problem with adding user attributes when creating a new user.



# Release notes: Version 2023.12.1

### Release Date : Jan 17, 2023 – 1:00 AM PST (tentative)

## New Functionality

- WEL-6084 - Displaying "From" phone number labels in the Сommunication center. With the release, it will be possible to add a label for the From phone field in the communication center for SMS and calls. 
This function is not available directly. In order to set labels for phones, you need to create a support ticket (JSM ticket type = work request) indicating which label to specify for which phone number.

## Improvements and bug fixes

- WEL-6314 - Redundant screen for SSO login experience. The redundant screen, which requires users to enter their credentials while autorizing through Google SSO , will no longer be displayed.
- WEL-5976 (WS-1994) - Template variable in assessment not pulling in populated CDT information. Fixed problem with filling in information for fields.
- WEL-6206 (WS-1899), (WS-1928) - Issue When Putting In Birth Date. Fixed the problem of entering the date of birth of the patient when using the keyboard.
- WEL-6380 (WS-1945) - Incorrect display in the calendar of an event that lasts 10 minutes. Fixed display of a ten-minute event in the calendar (event size reduced).



# Release notes: Version 2022.11.1

### Release Date : Dec 22, 2022 – 1:00 AM PST

## New Functionality

- WEL-6088 – URL shortening and Patient Verification for PFAs. After the release, URLs for PFAs will be generated in a new format which should be more convenient for SMS as it uses fewer characters, e.g. https://wh1.io/49a47f.
   - Another new feature has been added to authorize the patient when opening the PFA URL. The "Require Authorization" checkbox has been added to the PFA Folder in the Designer Portal. If the setting is enabled, then the patient will need to enter their First Name, Last Name, and Date of Birth to open the PFA folder with assessments. The setting is disabled by default and it’s recommended to enable it for all questionnaires that may contant PHI/PII data in it. 
   - Please note: The 'Require Authorization' setting can only be used for the PFA folders and is not available for individual PFAs. PFA folders are the preferred method to send assessments to a patient and individual PFAs will eventually be phased out. More information about transitioning to PFA folders will be provided in the future.
    
- WEL-6199 – Displaying friendly names of patient numbers in the communication center. It’s now possible to add labels for primary and secondary patient phone numbers. Two new fields (phone_label and secondary_phone_label), have been added to the Patient Profile section in the Designer Portal. It’s possible to add it to
Patient Profile
Top Info
Add Form 
Edit Form
After adding labels, they can be seen in the commcenter when sending SMS or calling a patient.
WEL-6229 – Attachments should be viewable in the Sent folder in the Emails. Added the ability to see attached files in sent emails. Files have a basic set of functions: it’s possible to download it or create a document based on the attached file.

## Improvements and bug fixes

- WEL-5912 (WS-1678) – Encounter creation showing an incorrect summary of calendar events status. Fixed the issue of displaying incorrect count and presentation of items that are already in the calendar when scheduling an encounter.
- WEL-6026 (WS-1706) – "Working Hours" are wrong for clinicians with different time zones. Fixed the issue when Working Hours of another user were not converted automatically to a timezone of the current user. 
- WEL-6302 (WS-1877) – If a user goes to any page other than Page 1 of a client's Assessments page, they are unable to return to Page 1. The problem with pagination on the list of assessments has been fixed.
- WEL-6272 - Deprecated the "userAttributes" section in favor of the new "customUserAttributes". When working with users (creating, editing, getting) through the API, please note that "userAttributes" is no longer supported, but "customUserAttributes" is supported instead. When creating a user with "userAttributes" it will be ignored, there will be no error in the console. Please make changes if you have used this option.






### Release Date : Dec 11, 2022 – 11:00 PM PST

## New Functionality
- WEL-6010 - Pre-set "From" phone number for a specific patient. New functionality has been added for more convenient communication with patients via SMS. Users can select a default phone for each patient from which SMS will be sent to this patient. This setting is located on the commcenter page under the gear icon, Default Phone. 
- WEL-5643 - Docusign integration: show multiple documents in the same envelope during template preview. Added the ability to view all files contained in a docusign template in the Care Portal under Docusign Document.

## Improvements and bug fixes

- WEL-6028 (WS-1710) - Unknown error in assessments. An error that occurred when trying to submit an assessment has been fixed.
- WEL-6236 - (WS-1839) - Users are not able to login to Welkin. Fixed an issue where users could not go through the organization entry page and login.
- WEL-6076 (WS-1755) - Permanent phone fields are required in UI, but not in Designer. Corrected the text of the validation message that is displayed if the user deletes the patient's phone number but leaves the phone's capabilities.
- WEL-6191 (WS-1807, WS-1821) - Ongoing "network error" issues despite strong internet connection. Fixed an issue with displaying an error when navigating through the portal.
- WEL-5918 (WS-1617) - Communication tab under patient profile has phone icon not showing correctly. Fixed icon for displaying Not Answer incoming call in the commcenter.
- WEL-5826 (WS-1523) - Attachments not appearing in Template Message. Fixed an issue where files were not added to SMS when selecting an SMS template with attachments.
- WEL-5947 (WS-1651) - Email not found error. Fixed an error that occurred if the user was on the patient's page, but opened a new incoming letter from another patient using the notification block.
- WEL-5986 (WS-1679) - Template Message Carryover. Fixed an issue where the SMS template text was copied from the SMS creation drawer to the text field of the SMS dialog.




# Hotfix Release notes: Version 2022.9.1.1

### Release Date : Nov 22, 2022 – 1:00 AM PST

## Improvements and bug fixes

- WEL-6177 (WS-1781) - New setting "Prevent updating an assessment (from an encounter) if it's in progress and assigned to the different encounter".
It’s now possible to configure on organization level whether users can add an assessment record to an encounter if there is already an In Progress record for a patient with the same assessment template originated in another encounter.
If the setting is enabled, users will see an error message that will prevent them from seeing and updating an assessment record until there will be no In Progress record with the same assessment template. Otherwise, users will see an In Progress assessment record with the possibility to update it in a context of previous encounter or reassign it to the current one. Please note that the setting can be changed by Welkin support team. 

# Release notes: Version 2022.9.1

### Release Date : Nov 18, 2022 – 1:00 AM PST

## New Functionality

- WEL-5927 - Add access_code field to Patient Profile. A new field access_code has been added to the Patient Profile in the Designer. The new access code field can be used to generate unique values ​​similarly to the MRN field. 
The field is configured similarly to other fields, it has user-set length attributes, only numbers, only letters, and so on. If the length is not set, it will default to 6 characters. At this moment the configuration of Mask Symbol, Start position, End position is not supported by access_code field.
The field is also available in the Patient Data View page on the View (Fields), Add Form, Edit Form tabs. The field can’t be added to the Top Info section.
- WEL-5904 - Access_code can be used in templates and sent via email or SMS. To be able to use the access code field in templates for sending letters and SMS, the variable {{PATIENT_ACCESS_CODE}} has been added to Message Templates in the Designer. 
- WEL-5869 - Access_code is searchable via API and UI. The access code field can be used to search for patients on the Care portal user interface, as well as through the API.
- WEL-5909 - Generate value for access_code field. New action types have been added to automation: Generate MRN and Generate Access Code. With these types, you can generate unique values for the appropriate fields for the patient profile. If fields are disabled on the Patient Profile in the Designer (OFF) then Generate MRN and Generate Access Code options are disabled for selection. If the MRN and Access Code fields are already used in automations and the user disables them in the patient profile in the Designer and tries to save, then a consistency check error message will be displayed. If the MRN and Access Code fields are already filled in, then they will NOT be overwritten when the automation is triggered again. Fields will be generated only if the fields are null.
- WEL-6011 - Setting assessment variables in template header and footer. With the release, variables added to headers and footers of assessment templates will be converted to assessment values when the PDF is generated.
- WEL-6012 - Assessment complete variables in assessment template. When creating an assessment, on the Template tab, new variables were added to reflect a person who completed the assessment
{{FORM_COMPLETER_ID}}
{{FORM_COMPLETER_EMAIL}}
{{FORM_COMPLETER_PHONE}}
{{FORM_COMPLETER_FIRST_NAME}}
{{FORM_COMPLETER_LAST_NAME}}
{{FORM_COMPLETER_ACUITY_ID}}
{{FORM_COMPLETER_ZOOM_ID}}
If the form was completed by the user, then the variables will be replaced with the user's data in the PDF file. If the assessment was completed by the patient, then the patient's data will be displayed (this situation is possible if the PFA link was sent to the patient, and the form being filled out had the autocomplete setting).
Please keep in mind that the {{FORM_COMPLETER_ACUITY_ID}} and {{FORM_COMPLETER_ZOOM_ID}} values ​​can only be set by the user and cannot be filled in for the patient.
- WEL-5917, WEL-6005 - Sticky filters on UI (Assessments, Task, Calendar). Filters on the pages of Assessments, Tasks, and on Calendar will be remembered and will not be reset when switching to other pages of the application. You can use the “Clear All” button to clear the filters.
For the Calendar, sticky filters are the display of the calendar (day, week, etc.), as well as the added calendars of other users.
After logout, the filters will reset to their default.

## Improvements and bug fixes

- WEL-5938 (WS-883) - Issue with DocuSign in-person signing. Fixed the issue, when after the signature process in DocuSign, the page redirects to an error screen if in-person signing is selected.
- WEL-6000 (WS-1694) - Multiple Working Hours Do Not Appear In the Day View of the Calendar. Fixed the issue when a user sets up multiple blocks of working hours in the Calendar. The blocks can be seen in the Week and Work Week views of the Calendar, but only one block of the working hours appeared in the Day view. 
- WEL-5988 (WS-1681) - Unknown Error when Exporting Assessment as PDF. Fixed the issue where an “unknown error” was displayed when trying to export the specific assessment as a PDF (using a template).
- WEL-6076 (WS-1755) - Permanent phone fields are required in UI, but not in Designer. Fixed the issue with Primary and Secondary phone fields in patient profile shown as required in the Care portal, although these fields are not set to be required in Designer. 
- WEL-6053 (WS-1736) - Unable to scroll in global search. Fixed the issue with global search when it was not possible to scroll through the search results and the list reached the bottom of the screen.
- WEL-5920 (WS-1622) - Not possible to open the 2nd page of the Unrecognized Communication. Fixed the issue where the system did not open the 2nd page of the Unrecognized Communication and takes the user back to the 1st page.
- WEL-6100 (WS-1734) - Forms on iOS Safari not auto sized. Fixed autoresizing issue for PFA links, the content automatically sizes to fit the browser page.
- WEL-6079 (WS-1779, WS-1759, WS-1816) - Invalid behavior of assessments in encounters. Fixed a bug that one assessment record could be assigned to several encounters at the same time. At the moment there can be a connection one specific assessment one encounter.


# Hotfix Release notes: Version 2022.8.2.1

### Release Date : Nov 14, 2022 – 1:00 AM PST

## Bug fixes
WEL-6097 (WS-1741, WS-1743, WS-1772, WS-1782) - This hotfix release fixed an issue that was blocking the successful completion of assessments. The problem arose with checkbox and radiobutton fields. The fields did not save the selected value, and therefore the data was not saved or it was impossible to complete the assessment, with required fields.


# Release notes: Version 2022.8.1

### Release Date : Oct 27, 2022 – 1:00 AM PST

### Please note that this list is not final and is subject to change.

## New Functionality
- WEL-5297 – Custom Data Fields in Patient Profile. With the new release, it’s possible in Designer to create new custom Data Fields for Patient Profiles. Once a custom Data Field is created, it can be added to the Patient Data View as a field to be displayed on the Patients Profile, Add and Edit Patient interfaces on Patient Profile. Please note that in order for a custom Data Field to be displayed in the Care portal, it’s required to set a corresponding security policy.

- WEL-5298 – Grid view options on Patient Data View. In Designer, it’s now possible to select one of multiple grid view options for Add and Edit Patient interfaces in the Care portal.

- WEL-5464 – Patient Profile security policy. New Patient Profile tab is added to Security Policy configuration where it’s possible to review permissions for default fields and set Create, Ready, Read Masked, Update and Delete permissions for custom patient profile field individually. 

- WEL-5701 – Automation for Chat messages. It’s now possible to create an automation in Designer to send a template message to a patient in Live Chat. It’s required to have a notification template with a Message Type of “Chat” and select Chat Patient as a triggering action of an automation.
- WEL-5385 – Resize of Assessment Drawer. To make filling out assessments more convenient, an Assessment Drawer can be expanded by dragging an edge of the drawer or pressing the expand button in the top right corner of the drawer. It can be set back to its normal size by pressing the collapse button.
- WEL-5668 – Sticky filters on UI (Encounters and Patients). With the release, Welkin will remember filter settings on Encounters and Patients pages. Users can update their  settings or navigate away to work with other parts of the application.  Once they go back, filter settings will be persistent. Please note that after log out, filter settings will be restored to the default. 

## Improvements and bug fixes
- WEL-5683 – New Phone Tree UI. Visual representation of Phone Trees have slightly improved in Designer by changing colors and adding labels.  The selected Phone Tree is now highlighted.
- WEL-5601 – Zoom ID in Encounter Message Templates belongs to the primary contact, not the user on the Encounter. A new variable {{ENCOUTNER.*.careTeamMemberZoomId}} has been added to the Message Templates to surface the Zoom ID that corresponds to the participant on the Encounter (regardless of whether that user is the primary point of contact for the patient).
- WEL-5645 – Previously, after documents were signed the system did not automatically refresh the page. With this improvement, documents that are completed and signed via DocuSign will automatically appear in the Documents page. This eliminates the need to refresh the page.
- WEL-5500 – Improved interface of Insights export. Slightly improved the UX/UI of request export interface on Insights page.
- WEL-5640 – Unify pagination and search across the Comm Center. Improved pagination and search functionality on Emails and SMS tabs of Comm Center to look and work in the same way.
- WEL-5985 – Export patients API doesn't contain info about Programs. Fixed the issue when Programs were always returned as empty in URL/export/PATIENT API response.
- WEL-5842 (WS-1543, WS-1625) – “Assessment record for patient is already started” error when assigning it to encounter. Fixed the issue when it was not possible to assign in progress assessment to an encounter while the encounter already contains an assessment.
- WEL-5528 – Issue with format of Date/Time fields in template-generated PDFs. Fixed format for date and time fields in template-generated PDFs that should now correspond to what is displayed on UI.
- WEL-5618 – Exploring Document Formatting in template-generated PDFs. Support of  “Courier New” font has been added to template-generated PDFs
- WEL-5619 – File Name change in template-generated PDFs. File name for in template-generated PDFs is updated for the following format: [patientName]-[assessmentTitle]-[finalizedDate].pdf 
- WEL-5546 – Can't null out phone field without NULLing out primaryPhoneCapabilities field. Fix for a scenario where it was not possible to erase phone number without erasing  primaryPhoneCapabilities field. Now both fields can be modified/erased independently. 
- WEL-5605 (WS-1336) – Filters not pulling in full list of users with the attribute(s). Fixed an issue where filters were not pulling all admin users by license state accurately.
- WEL-5674 (WS-1399) – Text message reminders going out to primary phone only. Fixed an issue where text message reminders would only be sent to primary phone number even if it was voice only. Now primary phone will be used to deliver text message if it’s SMS, otherwise system check SMS capabilities of secondary phone. 
- WEL-5744 (WS-1422) – Some downloaded files appear as no extension. Fixed a problem when zip files that contain “.” in its name were downloaded without an extension and were not recognized by OS.  
- WEL-5786 (WS-1547, WS-1493) – Export from Insights page is empty. Fixed an issue where data export from Insights would return an empty zip file. 
- WEL-5948 (WS-1650) – The calendar shows ‘invalid date’ instead of the day of the month on tables. Fixed the issue for tablet devices where the calendar displayed “invalid date” instead of the days of the month.  
- WEL-5603 (WS-1184) – Encounter PATCH doesn't update startDateTime without passing an endDateTime. Fix to return parse error instead of a success for a scenario where startDateTime has passed without passing an endDateTime for Encounter PATCH endpoint.
- WEL-5274 – Messaging and PDF template display CDT data element, not label. Fixed the issue where a value of CDT record was displayed instead of the label if CDT was used in messaging or PDF template.
- WEL-5934 – Secure emails change status only after page reload. With the release, secure emails sent in Comm Center will be reflected on the page automatically without a need to refresh the page.
- WEL-5871 – It’s required to click Next button twice, if the form in PFA have more than one section. Fixed the issue when it was required to click Next button twice to open the next section. 
- WEL-5870 (WS-1563) – Unable to Add Care Team Members When Manually Creating Patients. Fixed the issue when it was not possible to create a patient with assigned care team member and who does not have defined territories and regions 
- WEL-5755 (WS-1529, WS-1576) – 'New' button is not clickable when adding profiles in assessment. Fixed the issue when it was not possible to add a new profile in assessments. 
- WEL-5737 (WS-1456) – From time to time, an unknown error with status code 500 occurs on deleting CDTs. Fixed floating issue when system throws an unknown error with status code 500 occurs if deleting objects of the CDTs.
- WEL-5711 (WS-1238) – Disable possibility to enter a new value into question with predefined dictionary. With the release, the save button will be inactive in assessment if the user entered a new value into a question with predefined dictionary. 
- WEL-5705 (WS-1453, WS-1436) – Sometimes conditional questions are shown regardless of condition. Fixed the issue when conditional questions within an assessment were shown to a user regardless of false condition. 
 
## International (WhatsApp)
- WEL-5632 – Ability to resend a message. A resend option will be displayed on click on a message that failed to be sent to a patient. 
- WEL-5581 – Ability to send attachment without text message. It’s now possible to upload and send an attachment without entering a caption for it.
- WEL-5820 – WhatsApp phone number cannot be used for phone calls. With the release, it’s possible to make calls and send messages using the phone number that is conferred for WhatsApp.
- WEL-5549 – Add permission "WHATSAPP_NONE_CARE_TEAM". Added a new permission that allows users that are members of Care Team to read messages from patients.
- WEL-5657 – Choosing WhatsApp capability on secondary phone, message sent on primary. Fixed an issue where messages were sent to the primary phone, when WhatsApp capabilities were set to secondary phone.



# Upcoming Release notes: Version 2022.7.3.4

### Release Date : Sep 23, 2022

### Please note that the list is not final and is subject to change.

## New Functionality
- WEL-5514, WEL-5776, WEL-5638 – Support of auto-update for emails and SMS in Comms Center. All inbound and outbound notifications sent via email and SMS will be displayed in Comm Center in real-time without a need to reload the page. Also, Email and SMS notification statuses were updated and unified. 
- WEL-5680 (WS-1322) – Adjustable session timeouts. With the new release, user session configuration was added on the Security tab in Admin Portal. It’s now possible to adjust duration when users need to re-authenticate (default value is 30 days) and when a user’s session must be terminated because of inactivity in Care portal (default value is 30 days).
- WEL-5706 (WS-1323) – Rework of Welkin Login Screen for SSO customers. Users with SSO configured for their organization will now see an updated Welkin login screen with sign in SSO as a primary action and login with email and password as secondary.


## Improvements and bug fixes
- WEL-5724 – Images are not displayed for completed assessments. Improved functionality that was introduced in Release 2022.7.3.1 and allows uploading images for questions and texts for assessments. Now, it will be possible to view uploaded images for completed assessments.
- WEL-5836 – Comm center stops receiving real-time notifications in one hour. Addressed a problem when Comm center stops receiving notifications (Email, SMS, and WhatsApp in real-time after expiration of refresh token (in one hour). 
- WEL-5164 (WS-1334, WS-1178) – Issue with rendering of patient profile fields in PDF. Fix in place to address unwanted characters being displayed for patient profiles fields when converted to PDF format.
- WEL-5753 (WS-1397) – Single-record CDT is disappearing from the UI. Fixed a problem with a specific CDT not saving data after editing on UI when it was created more than one time.
- WEL-5738 (WS-1448) – All day events might not have start and end time spanning the whole day. Fixed issue when All Day event shows incorrect time in attribute, e.g. 9am-10am instead of 12am-11:59pm.
- WEL-5821 (WS-1524) – PFA link redirects to login screen instead of assessment. Fixed an issue when a patient was redirected to Welkin login screen instead of an assessment when following the PFA link. The issue was reproduced when PFA folder name contains words 'Welcome’ or ‘Conclusion’.


## International
- WEL-5757 – WhatsApp. Failed messages will be displayed as delivered to other users in a group chat. Fixed an issue when notification sent by a user and failed to be delivered will be displayed as delivered for the rest users in a group chat.


# Hotfix Release notes: Version 2022.7.3.3

### Release Date : Sep 8, 2022

## Improvements and bug fixes
- WEL-5746 (WS-1449, WS-1427) – Migration for calendar events created in an unreadable color scheme. Fix covers all calendar events that are created via API and appear in an unreadable color scheme (light gray events with white text).


# Hotfix Release notes: Version 2022.7.3.1

### Release Date : Sep 1, 2022

## New Functionality
- WEL-5577 (Beta) – Ability to upload images into assessments. Added a new feature that allows upload of images for questions and texts in the Assessment Builder module. Both patients and staff will see uploaded images like instructions or map, as an example, while working with assessments. The feature is in beta state and your feedback about it is highly appreciated via JSM.


## Improvements and bug fixes
- WEL-5704 (WS-1449) – Calendar events appear in an unreadable color scheme. Fixed a problem for calendar events that appear in an unreadable color scheme (light gray events with white text) when created via API.
- WEL-5713 (WS-1442 & WS-WS-1431) – Assessments are unlinked from an encounter after completion. Fixed an issue when assessments were “disappearing” from the encounters in which they were created, and it was only possible to find those assessments in the Assessments view.
- WEL-5402 (WS-1097) – Encounter’s “Updated At” was incorrect. Issue was fixed for the specific encounter displaying incorrect “Updated At” date. 
-WEL-5667 (WS-1388) – Unable to modify encounter details after status change. Fixed the issue when “Calendar event isn’t modifiable” error was displayed while editing an encounter in either  ‘Planned’ or ‘In progress’ statuses after being ‘Canceled’.

## International
- WEL-5687 (WS-1419) – Users didn’t get new messages in WhatsApp module if they don’t share region/territory with a patient. Addressed the issue where users were not getting new messages until the page is refreshed if their region/territory were different from a patient.




# Release notes: Version 2022.7.3

### __Release Date__ : Aug 24th, 2022

#### _Please note that the list is not final and is subject to change._

## New Functionality
- WEL-4849 – Customizable Patients table for Care Portal. With the new release, it’s now possible to customize the layout of the Patients table according to the needs of your organization by adding, removing and renaming columns in Designer.
- WEL-4849 – Calendar week view for multiple users. In the release, we enhanced the week view in Welkin Calendar by adding support for a view of multiple users, similar to a single day view. The calendar will automatically assign a unique color for every added user to easier distinguish their events in the UI.
- WELL-5572 – Configure zip code format. We added the possibility to configure zip code format in Designer, such as setting length, and whether it should be numeric or string. If numeric format is chosen, it’s expected to receive integer value through API.
- WEL-5510 – Add “Assessment created” trigger to Automations. It’s now possible to trigger an automation based on the creation of an Assessment.  For example, you can generate a task N days after creation, or any of the other automation actions.

## Improvements and bug fixes
- WEL-5498 (WS-1137) – Unnecessary questions were displayed for an assessment. Fix in place to address an issue when some unnecessary questions were displayed in the assessment and disappeared only after page reload.
- WEL-5538 (WS-1201) – “Configuration with this name was not found” error when viewing patients. Fixed an issue when there was no configuration created for the Communication tab on Integrations page in the Admin Portal, and a configuration error was displayed on the Care Portal when viewing a patient.
- WEL-4507 – Encounters: "My Only" naming convention is not grammatically correct. We changed “My Only” filtering option for encounters to “My Encounters” and “Care Team to “All Team Encounters”.
- WEL-5301 – Changes of phone/email are not saved for drafts. Fixed an issue where a change of primary phone number or email address was not saved for draft messages. 
- WEL-5368 (WS-1047) – Unable to search for Care Team Member users when editing a patient. New release addressed an issue when a “no results” message was returned for a Care Team Member search while editing a patient.  The bug was only observed for Care Team Members who didn’t have any territory assigned to them. 
- WEL-5430 (WS-949) – Not possible to search for assessments which have more than one word in their name. Fixed a problem where it was not possible to search for an assessment / note which had more than one word in its name.
- WEL-5438 – Prevent concurrent requests of Data Export. In the new release, we limited the possibility for multiple users to create concurrent requests of Data Export on the Insights page as it could cause degradation of overall system performance. Now, users will see a message that someone has already requested a data export, and it's either being generated or already available for download.
Please note that the engineering team is still working on improving export stability and export functionality is not available for use yet.
- WEL-5588 – Remove patient ID filter from admin Sisense reports. We removed the patient ID filter from the Sisense admin report so that it should show data from all patients and not filter to a specific patient ID.
- WEL-5253 – No indication that message failed to be delivered in WhatsApp. We added a UI indication for messages that were sent through WhatsApp and failed to be delivered, e.g., because of invalid phone number.
- WEL-4878  – UI improvements for Email Communication Center. Added a number of minor UI improvements for the Email tab in the Communication Center page, including pagination, column sorting, and renamed some statuses. Also updated an interface of Scheduler Drawer, where you have to schedule an item to draft to edit it.


# Release notes: Version 2022.7.2.3 

### Date : Aug 4th, 2022

## This is hotfix

## Care Portal.
- WEL-5584 (WS-1243) - Assessment ID not accessible. We put a fix in place to address an issue that was reported by a customer that a specific Assessment ID could not be opened in the Care Portal.
- WEL-5569 (WS-1244) - Editing of past encounters causes endless page loading error. We fixed an issue that caused an endless page loading error when a user was trying to edit an encounter that has its date in the past.
- WEL-5402 (WS-1097) - WhatsApp’s comms module not syncing in real time. We fixed a problem, when multiple care team members were chatting with the same patient at the same time, messages from care team members were not getting reflected in the WhatsApp’s comms module in real time. Prior to the release, a page refresh was needed to see it.
- WEL-5338 (WS-1080). Encounters created during outage can’t be accessed via UI or API. We released a fix for several encounters that were created during a system outage and couldn't be accessed via UI or API.  
- WEL-5557 (WS-1250) - Unable to move encounter into "Planned" status, despite enabled "Move to Planned" permissions. We fixed an issue that did not allow moving an encounter into “Planned” status despite having “Move to Planned” permission enabled. 
- WEL-5478 (WS-1131) - "DT not found" error was displayed while completing an assessment. With the release, we fixed an error that prevented completing an assessment when the configuration had been changed in the Designer Portal after its start.
- WEL-5504 (WS-1170) - "DT not found" error is displayed while searching a patient on the Encounters tab of another patient. In the release, we fixed the “DT not found error” that was displayed in case of using global search to find a patient on the Encounters tab of another patient profile. 
- WEL-5512 (WS-1193) - "Save as Draft" button on Dialog tab is leading to sending of text messages. We fixed a problem where a text message was sent to a recipient immediately, instead of just saved as a draft, after clicking the corresponding button on the Dialog tab in the Care Portal. 


## API
- WEL-5595 - Performance improvements for internal API calls. With the release, we improved the performance of internal API calls related to getting information about users and environments for the Admin Portal and getting information about logged-in user’s environments for Care and Designer Portals.


# Release notes: Version 2022.7.2.2

### Date : July 29th, 2022

## This is a hotfix release and it addresses critical bugs in encounters, policies & assessments.


## Care
- WEL-5558	Unable to restrict date changes to Encounters. Removing the "update" permission in Designer still allowed a user to click on an Encounter link and edit. This has been resolved, so the update permission is now required to make any changes to date/time of encounter.
- WEL-5536 	Changing the primary team contact throws a 500 error. Primary contact can now be changed without issue. 
- WEL-5555	Unable to delete patients.  Errors were generated when attempting to delete patients, preventing patient deletion.  Resolved.
- WEL-5559	User license field does not reliably persist data.  Accessing the user license field sometimes did not display the information.  Resolved.
- WEL-5535	Encounter disposition pre-defined fields throws a 500 error. The error is no longer displayed when working with Encounter Depositions with pre-filled fields.
- WEL-5562	Disable 'Add' button for assessments if the ‘’Update’’ policy is not set.  Update is required to be enabled for a user to add an assessment.


## Designer
- WEL-5534	Create encounter permissions required to add a note to an existing encounter. 
We have moved the ability to add a new assessment to an encounter from 'Create' to 'Update' policy. If the 'Update' policy is not selected - a user will see disabled '+' button for adding new assessments. If the 'Update' policy is selected - a user will have the ability to add a new assessment to an encounter.
- WEL-5557	Toggling encounters into planned status tied to create settings. 
We have separated the 'Create' policy to two policies: 'Create encounter' and 'Move to Planned'. It allows the ability to create encounters, but blocks an ability to move an encounter from any status to 'Planned' back and vice versa.

With this change, we will make a migration to keep policies which have been set previously. If encounter permissions had the 'Create' policy, we have migrated it to 'Create encounter' and 'Move to Planned’ policy. If encounter had no 'Create' policy we have not selected 'Create encounter' or 'Move to Planned' policies.  Please update your permissions post release as appropriate.


## APIs
- WEL-5545	Encounters - Unable to restrict date changes to EncountersAPI
Separated CREATE permissions into two permissions: create encounter and change encounter status to PLANNED.  Please update your API permissions in Designer post release as appropriate.

# Release notes - Version 2022.7.1

### Date: July 8th, 2022

## Care
- WEL-5384 Fixed: Instances of 500 Error in Encounters, home page
- WEL-5350 Fixed: Assessments Status Filter shows status name starting from capital letter.
- WEL-5342 Care -> Communication Center -> change field "attachments: [ ]" to "attachment: "string""
- WEL-5330 Unknown errors in Calendar
- WEL-5316 Fixed: Frontend -> Care -> Patients -> New\Edit -> Remove spaces at the end of fields when saving a patient (to prevent problems with search)
- WEL-5198 Care: DOB filter
- WEL-5171 Encounter times shown in UTC on Encounters index page
- WEL-5384 Care -> Encounters -> View encounters, home page -> Error 500. 
- WEL-5350 Care Portal -> Assessments -> Filter by Status: The name of status should starts from capital letter
- WEL-5342 Care -> Communication Center -> change field "attachments: [ ]" to "attachment: "string""
- WEL-5330 Unknown errors message in Calendar
- WEL-5316 Frontend -> Care -> Patients -> New\Edit -> Remove spaces at the end of fields when saving a patient (to prevent problems with search)
- WEL-5198 DOB filter in patient search
- WEL-5171 Encounter times shown in UTC on Encounters index page
 
 
## Admin
- WEL-5348 Admin Portal -> Integrations -  Incorrect settings validation


# Release notes - Version 2022.6.6

### Date: June 24, 2022

## New Features Callout

**Patient Facing Assessments (PFA), Folders and Branding - WEL-4452**

This feature was based on customer feedback, and we encourage you to provide more feedback on how can we improve it

In the new release, Welkin upgraded its PFA capabilities. 
Assessments can now be organized into PFA Folders. Each folder can be sent to a patient using message template and 
allows the patient to fill multiple assessments within the folder.

Each Assessment within the folder, can support multiple statuses, to reflect better patient interactions. Statuses are visible in Care 
on the patient assessment layout:

1. New - indicates that assessment has been sent but the patient hasn't answered any questions yet
2. In Progress - indicates that patient has started working on assessment but hasn't completed it yet (same state as previously existed)
3. Submitted - indicates that patient has completed working on assessment
4. Expired - this is a special status, indicating that assessment link has expired and cannot be worked on by the patient anymore
5. Completed - this is the final state, no more changes are possible at this point (same state as previously existed)

What is the difference between Submitted and Completed?

When assessment is in status Submitted, it allows one that has enough permissions to review and Complete it. It is useful to do so
when a patient doesn't answer questions, or wants to change the answers while talking to a Welkin user.

Completed on the other hand, is a final state that triggers copy to custom data types associated with the assessment

Branding:

PFA folder now supports branding. In the Designer, our users can customize color scheme, logo, and favicon. The goal is to 
allow our customers to modify PFA to look and feel in native colors vs welkin color scheme

In addition, customers can use Welcome and Conclusion pages (optionally) for providing patients with additional instructions and
thank you notes, or extra customization for other needs

In the subsequent releases, we will include several UI/UX improvements, updates to Security Policies on Assessments and automation improvements

**Custom Patient Profile WEL-5032**

This release contains a fundamental improvement for Patient Profile. Our customers can now add fields directly to patients
in addition to existing methods of adding fields to the CDT. 

In addition, Top Info section has more configuration options and changed behavior, by allowing you to specify number of visible fields 
vs showing everything

The benefits of choosing this modeling tactics, will allow customers to define their Patient Create / Edit screens in addition to 
defining Patient List columns (to be released soon).

Of course, similarly to our previous recommendations, we suggest discussing modeling with Welkin Implementation team, since its typically
affecting how your API and Data will work and will look like



**International DateTime - WEL-5051**

In order to better support datetime across time zones (and in support of our international customers) the team developed datetime component that operates
based on the user locale. Locale can be set up in Admin or Care, and will dictate how date and time are displayed

**International Phone Number - WEL-5052**

In this release, Welkin has started adding support for international phone numbers. Customers can start adding phone numbers for patients outside the US

This is an opportunistic feature, meaning that we add support to a new country by requests and as of today, only the USA and Singapore were added to the support list. 
Please let us know if more countries are needed


**Designer JSON Viewer - WEL-5205**

To improve performance and memory footprint of designer, we had to make some modifications to JSON viewerL

1. The viewer is hidden by default and presents itself on a button click (CDT View, top right)
2. Viewer is read only and does not refresh automatically - a button is added for that

We resolved the limitation of List field (changing order of values in a list field, that previously was only possible to do in the JSON viewer)
and it's now possible to do that in our UI

Note: The future of JSON viewer depends on our customers, if that feature is something that you like, please let us know.

**Notification UX - WEL-4332**

We implemented changes to Notification UX (drawer) in Care, to support archiving of one notification at a time (vs bulk).
This means that single archive button will only archive one notification and archive all will act on all
The option of "archive all older than current" that previously existed, was now removed

**International - WhatsApp support - WEL-4814**

To support our International customers, we have added support to whatsapp. Customers can start WhatsApp conversations, send 
and receive messages, attachments and use templates 


Note: This feature requires configuration on Welkin side and not available out of the box to anyone, due to nature of such chat integration
If you are interested in trying it out and eligible from compliance perspective, please reach out to your CSM

**Phone Capabilities - WEL-5071**

Each phone number in Welkin, has a list of associated capabilities. Using that list, customers can tag a phone number (Voice, SMS, MMS). Once tagged,
Comm Center will help users understand that SMS cannot be sent to a number that does not have such capability for example, and will help our customers
to increase success rate of different communication channels

Note: Some UX changes and improvements to Comm Center, are going to be released in next releases

**Automation - WEL-5134**

Two improvements in this release:
1. Encounter creation action now includes ability to specify Care team (Point of Contact or Role) to better target correct audience
2. New Condition on Patient to test for Care Team (or Point of Contact) - to help identify situations when patients have no active care team members
or point of contact


## Care
- WEL-5210 Fixed: Unrecognized calls show up in notification bell but not in unrecognized comms section
- WEL-5199 Fixed: Calls are going unrecognized that shouldn't be
- WEL-5165 Fixed: Assessments - Radio buttons selections do not save in Safari
- WEL-5151 Fixed: Care -> Commcenter -> Emails -> There is a behavior where you can add more files than allowed by validation
- WEL-5145 Fixed: Received a notification for "Team Missed Call" Despite the call being answered.
- WEL-5139 Fixed: Date of Birth search is not functional in global search
- WEL-5133 Fixed: Searching for numbers returns all clients, regardless of permissions
- WEL-5128 Fixed: Trouble Generating PDF Documents from Assessments under certain conditions when DateTime are not populated and N/A is used
- WEL-4676 Fixed: Assessment's pre-populated template variable field always showing TRUE, even when FALSE
- WEL-5323 Fixed: API - Unable to update Assessment status using the API
- WEL-5322 Fixed: Primary Contact can't be changed
- WEL-5319 Fixed Cannot select/unselect call recording
- WEL-5130 Updated: Care: Add refresh buttons to update content of email / sms / calls pages



## Designer
- WEL-5149 Fixed: Message Templates: Incorrect view of the validation message
- WEL-5148 Updated: Inconsistency in notifying that the size of attached files in the Designer in message templates is limited to 50 mb, and on the Care portal to 25 mb


## Admin
- WEL-5156 Fixed: Admin -> Postponed tasks -> Select 100 elements to display -> CORS error
- WEL-5152 Fixed: Copy a user with Allowed To Receive Calls = false flag is ignored
- WEL-5132 Fixed: Admin -> Security Settings -> Deactivate SSO -> "Login with ..." button is still visible
- WEL-5036 Fixed: Data Audit: Trigger an automation that creates an encounter → Data Audit -> The record doesn’t have Actor value
- WEL-5092 Updated Security Audit: When changing root user, no visible security audit event is generated
- WEL-5091 Updated: New text for change user email


## Known Issues:
- WEL-5093 After user activation, updating user custom attributes does not work for hidden and read only attributes
- There are few issues on the home page, that more information included in the widget than what expected (completed encounters, unrecognized calls). we are actively working on this issue
- There is an issue with calendar, throwing random errors. The team is working on that

# Release notes - Version 2022.5.6

### Date: May 28, 2022

## New Features Callout

**Attachments in Message Templates - WEL-4449**

With this release, customers can add attachments to messages in the Designer.
Once attachment is added, it will appear during message composition, and can be removed if needed

## Care
- WEL-5013 Fixed: Opening email drafts does not display attachments 
- WEL-5121 Fixed: Export API shows `hasNext` as `false` even when more records exist
- WEL-5120 Fixed: Transient error on send SMS, throws 500
- WEL-5099 Fixed: Clicking on in progress Assessment in the Encounters bring a "start assessment" drawer instead of actual assessment under certain conditions
- WEL-5043 Fixed: Physician profile became not searchable after being updated
- WEL-5077 Updated: Call not registering in Comms Center, if patient hangup prior to phone tree execution completed
- WEL-5072 Updated: Filter for patients that have completed programs is not working correctly, by displaying inactive programs

## Designer

N/A

## Admin

- WEL-5138 Fixed: Inviting users didn't properly honor Allowed to Receive Phone Calls flag


## Known Issues:
- WEL-4878 Minor UI issues with email drafts
- WEL-5093 After user activation, updating user custom attributes does not work for hidden and read only attributes


# Release notes - Version 2022.5.4

### Date: May 17, 2022


## Care

- WEL-5098 Fixed: Unable to select secondary number from drop down in comm center
- WEL-5078 Fixed: Patients -> Filter 'Care Team' -> Only 20-40 results displayed at a time


## Designer

N/A

## Admin
- WEL-5088 Fixed: Issues with bulk activating users created using api
- WEL-5102 Updated: Added more information about webhooks in the Data Audit section

## Known Issues:
- WEL-5008 Saved draft does not display email attachments
- WEL-4878 Minor UI issues with email drafts
- WEL-5093 After user activation, updating user custom attributes does not work for hidden and read only attributes


# Release notes - Version 2022.5.3

### Date: May 15, 2022

## New Features Callout

**Delete Patient - Right to be forgotten - WEL-4871**

Starting with this release, Welkin allows patient deletion. This feature is meant to support compliance use cases of right to be forgotten.
In order to enable it, please enable "delete" permission on a patient in Designer.
The option is only available from the patient list menu (not available in patient profile view nor by API)


**Comm Center - Email Draft Improvements - WEL-4077**

Several changes are coming out with the release of this feature. 

- New Folder: Drafts - allows users to see all the draft emails, schedule them or discard them
- New Folder: Starred - allows users to see all starred emails across Inbox, Sent, Scheduled and Drafts
Note: Starred functionality also exists in Messages and Calls separately

Scheduling drafts can be based on chosen date/time or based on cadence that is set with the patient

**User Provisioning - WEL-4944**

In order to help our customers onboard users programatically, we are making user provision api available to api clients.
There are certain limitations to the feature, due to the sensitive nature of user provisioning using api.

- Users are onboarded in an inactive state. Activation and License assignment will need to happen manually from Admin
- Password reset emails will go out to the users once they are activated
- Certain setting required to be set on API clients in order to support that level of access (in Admin)
  - User Provision - this flag enables user provisioning using api client
  - User Regions - this flag enables regions and territories management using api client
  - User Attributes - this flag enables api client to manipulate values of user attributes

**Profiles: New Data Views - WEL-4083**

This release adds more flexibility to the profiles configuration. 
- Profile data views are now capable of showing profile fields as either separate columns or concatenated into one column
- Hyperlink navigation to the profile from the dataview is now available as well
- Setting up profile field values as referenceable or copied to CDT is now available (by Reference vs by Value options)

**Patient List Improvements - WEL-4978**

Further improvements to Patient List is adding to usability of the widget
- Majority of the columns (except of Program, Phase and Care Members) are now enabled for click to sort
- New filter to find patients without Program is added
- New filter to find patients without Region or Territory is added

**Encounters Delivery Method - WEL-4386**

In this release, encounter delivery method can be set in the Designer on encounter template. Once set, it would be 
shown in Care and will be utilized in Automation. Delivery method can be updated at any time in Care, if set incorrectly


**Phone Tree Log improvements - WEL-4968 and WEL-4834**

Few improvements to phone tree feature in this release
- Notifications for missed calls. It is now possible to enable missed call notification in the designer, that will let 
user know if they missed a specific call from a recognized patient
- Improvements to Phone Audit log in Admin. With this release, there is a brand new dedicated UI for call log, to indicate
the route that the call has taken and steps performed, to help understand why phone calls arrive to certain users instead of other users
- New setting on User Profile in Admin, that controls if User can take a part in a phone tree. Using this setting allows some customers to 
opt in/out users from participating in a phone tree for any reason

**Autocomplete Program - WEL-4913**

Minor but useful feature was added to programs, allowing customers to indicate "Autocomplete" on a Final Phase in a program.
If that flag is set, moving patient to final phase will also complete the program and set it to Finish

**Error and Info messages UX- WEL-4758**

Improved UX of error and info messages across Care, Admin and Designer applications


## Care
- WEL-4953 Fixed: Errors when submitting a form from patient facing link
- WEL-4932 Fixed: Removing phone from user profile reflects only after clear cache
- WEL-4980 Fixed: Unable to update patient/client's care team, under certain conditions the field value is not set correctly
- WEL-4029 Fixed: 'Add' button is inactive on Create CDT Drawer, when default value was preconfigured in Designer
- WEL-5058 Fixed: Changing filter from Care Team to My Only on encounters breaks pagination
- WEL-5026 Fixed: Added more space to display large amount of Territories in User Profile 
- WEL-4950 Fixed: Encounter Patch API throws 500 Error when eventStatus is not set
- WEL-4351 Fixed: Planned and In Progress encounters are not always appearing at the top of a client's encounters page
- WEL-4215 Fixed: Improved performance of the request GET /users/\{userId\}/encounters; withCareTeam=false
- WEL-4993 Fixed: Care Member search bar does not show up in Patients page

- WEL-4895 Updated: Increased column size for assessment name to accommodate long names

- WEL-4998 Updated: Comm Center -> New Call -> The placeholder of the 'To' field has [object Object] value
- WEL-4963 Updated: Encounters -> Design -> Canceled encounters don't have the red background
- WEL-3685 Updated: Enable bulk remove Care Team members
- WEL-4448 Updated: Care: See image preview before sending email


## Designer

- WEL-4991 Fixed: When a field is modified or deleted and had a previous condition associated with it, form cannot be saved unless condition is removed
- WEL-4981 Fixed: Hyperlinking with system variables is broken in Designer, last curly bracket is removed
- WEL-4911 Updated: Remove disabled fields from Webhook Designer



## Admin
- WEL-5028 Fixed: Data Audit - it doesn't show a patients in Object Type=Calendar, Event Subtype=CALENDAR\_EVENT\_DELETED
- WEL-4498 Fixed: Error on copying an existing user's profile errors if there are territories/permission that no longer exist in Designer.
- WEL-4943 Updated: Email style for changing root user


## Known Issues:
- WEL-5008 Saved draft does not display email attachments
- WEL-4878 Minor UI issues with email drafts
- WEL-5088 Issues bulk activating users created using api
- WEL-5093 After user activation, updating user custom attributes does not work for hidden and read only attributes


# Release notes - Version 2022.4.5.2

### Date: April 20, 2022

## Minor Improvements Callout

- WEL-4907 Login experience will accept tenant name in any case sensitivity (upper or lower) to reduce friction that some users experience while typing the tenant name

- WEL-4054 New Patient level variables were added to Assessment Template to support more functionality on generating PDF based of assessment results

- WEL-4901 Three new values were added to Patient Languages (Vietnamese, Japanese, Other)
Customers can now use them to match better with users. Reminder, that user languages is a configurable attribute in Admin -> User Attributes section

- WEL-4856 New field for Recurring Automation - Customers can now use a different algorithm to schedule recurring automation, either from the “deploy” time or using cdt level attribute on a patient to control start time


## Care
- WEL-4886 Fixed: Read only fields are duplicating in Assessment view on CDT entry
- WEL-4855 Fixed: Navigating to other layouts when an Assessment is open removes all recorded answers from view
- WEL-4902 Fixed: Patient search doesn't work within profile
- WEL-4870 Fixed: Unexpected format in cdt fields (array vs single values) on list type fields
- WEL-4633 Fixed: Comm Center: Email Reply with attachments hides the original email
- WEL-4874 Fixed: Comm Center -> Emails -> Reply to the secondary email -> Reply opens for the primary email
- WEL-4940 Fixed: Comm Center -> Emails ->Incoming emails do not shown attached files
- WEL-4768 Updated: Allow API client to update care teams that contain inactive users
- WEL-4844 Updated: Encounters: API Client is now allowed to update encounter host
```
{
  "currentScheduledAppointment": {
         "hostId": "User UUID"
  }
}
```


## Designer
- WEL-4898 Fixed: Encounter disposition -> Change the display type -> Save changes -> Changes are not displayed, but saved
- WEL-4747 Fixed: Designer changes to CDT removes answers from assessment


## Admin
- WEL-4908 Fixed: Copy a user -> Enter an email -> Invite button is not active
- WEL-4896 Fixed: Unable to remove User phone number in Admin
- WEL-4861 Fixed: Changing user email removes 2FA setting for the same user
- WEL-4803 Updated: Some styling and UI issues on Change Email address functionality
- WEL-4811 Updated:Webhooks UI improvements


## Known Issues:
N/A


# Release notes - Version 2022.4.2

### Date: April 08, 2022

## New Features Callout

**New User interface for file upload in Comm center - WEL-3707**

Upload attachments user interface in comm center was replaced with a new UI.
The new UI is easier to use, including detailed preview and ability to select documents and upload attachments
within same seamless interaction



## Care
- WEL-4868 Fixed: Enable replying to received email that does not have a subject field in it
- WEL-4860 Fixed: Under some conditions, assessment not loading until clicked on for 2nd time.
- WEL-4811 Fixed: UI Updates to Admin Webhooks to match our design style better
- WEL-4845 Fixed: Under purple color on Home Screen widgets, calendar event does not display patient name in a readable form
- WEL-4831 Fixed: Unable to listen to call recordings on iPad
- WEL-4762 Fixed: Updating encounter without eventStatus fields, breaks it and does not allow further status updates
- WEL-4792 Fixed: Automaton: Condition to test for null email field is not working 
- WEL-4767 Updated: List of patients -> User is not displayed as inactive
- WEL-3685 Updated: Allow removal of care team in bulk update patients in the Patient List


## Designer
N/A

## Admin
- WEL-4852 Fixed: Spelling mistake in User Profile
- WEL-4819 Fixed: success message on webhooks throws confusing message
- WEL-4703 Fixed: copying users with invalid territories makes the user corrupt and not work as expected
- WEL-4863 Updated: notification email text on user's email change event
- WEL-4805 Updated: Edit user's email drawer


## Known Issues:
- WEL-4803: Some styling and UI issues on Change Email address functionality


# Release notes - Version 2022.4.1

### Date: April 01, 2022


## Care
- WEL-4807 Fixed: Tasks counter is not updated when a new task is created
- WEL-4824 Fixed: SMS to secondary number is sent to primary number
- WEL-4778 Fixed: Tasks created by automation do not display accurate icon and name
- WEL-4808 Updated: Refresh button was added to Patient List 
- WEL-4781 Updated: Clear filters button was added to Patient List for fast filter reset
- WEL-4808 Updated: Refresh button was added to Tasks List 

## Designer
N/A

## Admin
- WEL-4818 Fixed: Cannot create custom header in webhook setup
- WEL-4846 Fixed: Clicking on Test Webhook - Success message does not show up
- WEL-4811 Updated: Admin Webhooks UI updates
- WEL-4804 Updated: Improved email text for change user address notification
- WEL-4827 Updated: Phone tree log now has a dedicated page in Admin. Customers can find phone tree execution 
in that log and understand the path that call has taken until reached final destination

## Known Issues:
- WEL-4803: Some styling and UI issues on Change Email address functionality
- WEL-4811: UI Updates to Admin Webhooks to match our design style better

# Release notes - Version 2022.3.7

### Date: March 28, 2022

## Care
- WEL-4812: Home Page tasks widget displays all tasks without filter taking any effect
- WEL-4802: Creating new tasks from Patient task layout does not persist the patient

## Designer
N/A

## Admin
N/A

## Known Issues:
- WEL-4778: Tasks created by automation do not display accurate icon and name
- WEL-4803: Some styling and UI issues on Change Email address functionality
- WEL-4811: UI Updates to Admin Webhooks to match our design style better

# Release notes - Version 2022.3.6

### Date: March 25, 2022

## New Features Callout

**New Tasks Layout and Updates to Task List - WEL-4579**

In this release, we upgraded Tasks functionality to support new use cases and new UI. 
1. A new default Task layout is now available in Designer. Customers can add Tasks to patient view, 
similar to other default layouts. This layout will offer a filtered version to all tasks for this patient and filter capabilities, by Assignee, Dates and other fields
2. New filters are introduced, including ability to filter tasks by certain template (or by Custom Task)
3. User tasks view will now offer a view to see tasks of any users, with a preset default to the current logged in User. It will allow one 
to locate tasks for assignees that may no longer be with the company or need help reassigning the tasks
4. Convenient "Clear All" button removes all filters
5. Sorting by clicking on column name in the Task List is now available. The sort will perform a sort within each section (Todo, In Progress and Completed),
and will allow users to see each section independently without intermixing different statuses

Updates to Task drawer

6. UI changes - added Updated by field and moved both Created and Updated fields to the top of the drawer
7. When a new task is created without a patient, updating it from the drawer will allow one to assign 
the patient. Similar to the past behavior, once patient is assigned, they cannot be changed
8. "Save & Clone" button has been added to replace the checkbox. Convenient for customers who create many tasks for different patient at the same time.
The behavior was updated as well, clicking on Save & Clone will preserve all data in the tasks, besides a Patient and Comments, allow fast creation of 
similar tasks for all the patients


**Automation - New Triggers, Conditions - WEL-4579**

This release contains a new batch of different automation triggers and conditions, allowing our customers to automate even more use cases

New Triggers
1. Task is completed (new set of all triggers for tasks is available, to represent each state)
2. Point of contact changed
3. Care Team updated
4. Encounter Updated 

New Conditions:

5. On SMS receive, perform a text match (case sensitive and insensitive options are available)
6. Condition to check if patient is in Territory or Region
7. Condition to check for Text and Text Area fields being Null or NotNull

Couple of sample use cases that can be used by our customers:
1. On sms receive, look up for keyword and generate task, notification or email to the user to take some action
2. On task complete (of certain template) generate a new task (of a different template) - allows one to chain tasks, one after another
3. When executing some action, customers can check if a patient is in a certain Territory or in certain Program, allowing applying a different types of automation 
from the same trigger based on different location of program assignment


**Change User's Email - WEL-4710**

This is to address one of the customer's requests to change the user's email address. Once email address is updated, the system will send notification to
the old email address (informing of update), trigger password reset to the new address and inform tenant owner of such a change

**Terminology Panel - WEL-4417**

With this release, we start allowing our customers to modify some core concepts in Welkin UI, to match customers own terminology.
The most popular use case, about 50% or our customers do not actually use the word Patient, but something else.
With the release, the word patient can be replaced with a different term.
To use that feature, override default terminology in Designer (or create a brand new one) and have users use it, from their Profile page by choosing display language

Note: This is an experimental feature, completely based on our customers requests, currently in Alpha. 
Please reach out with any feedback or wish list about this feature. We will only know how well it fits your need based on the feedback

**Webhook Management**

In order to improve Webhook management a bit, we are splitting webhook functionality into two different areas.
1. Webhooks are still created in the designer, however one can only provide name and title
2. Once deployed, webhooks can be found in Admin under Integrations -> Webhooks.

The webhooks in Admin would be Inactive by default, and would have to be supplied with URL (other parameters can be added as well) before activation

Note: Designer UI has been disabled and to provide these values, is now read only, and all current values have been migrated. 
In the next releases, we will clean up the designer UI as well


**Granular Email Status - WEL-4424**

In this release, we added a new feature that will propagate detail email status back to Care

New email statuses will support, Opened, Clicked and Failed.

There are some restrictions on how Opened and Clicked can work, depending on the end user(patient) email server (can be fully blocked), specific user setup
and the sender domain,but in general, if the email was Opened by the patient the status will become Open, if the email contains a link and the link was clicked, 
the status will be Clicked, and Failure will be presented if we cannot deliver the email.
Combined, under reasonable circumstances, should provide our customers with enough visibility into each and every email that is being sent from Welkin


**Profiles - New Data View structures - WEL-4357**

With the Profiles features being heavily used in Welkin, we have updated Data Views in the designer, to support profiles but also offer more reach 
functionality.
Generally speaking, fields can be placed in different layouts in in different rows, they can be combined to show one or more profile fields and will allow
profiles to be hyperlinked from the CDT view.
The UX in designer was completely updated not only to support this functionality but also to comply with our latest styling guide


## Care
- WEL-4772 Fixed: Care: Encounter ->  Error: User doesn't exist
- WEL-4766 Fixed: Comm Center: view of emails is cut off - cannot see full email content.
- WEL-4733 Fixed: Comm Center On the pages Communication Center and Unrecognized communications the system shows the browser timezone not user's one
- WEL-4698 Fixed: Assessments page showing "No data" for clients after adding a new assessment to an encounter
- WEL-4608 Fixed: Phone Number is not displayed in short SMS view
- WEL-3864 Fixed: Totals on Calendar Utilization insights do not add up
- WEL-4722 Fixed: Data layouts are hard to access, and aren't shown - scrolling is needed for lower resolution machines
- WEL-4680 Fixed: Not all notifications are being listed - Add lazy load to the list of notifications
- WEL-4546 Fixed: Unrecognized comms show up in notification bell but not in inbox \(Home or Comms\)
- WEL-4570 Fixed: Unable to set working hours from 11:30pm-12am
- WEL-4569 Fixed: Prepopulated Assessment data not saving on Finalize
- WEL-4503 Fixed: New Calendar Event: Participants not showing in search results
- WEL-4708 Fixed: Unable to save encounter disposition containing pre populated data
- WEL-4629 Fixed: Patients cannot be sorted into alphabetical order
- WEL-4684 Fixed: Missing Updated Date and Created Date in the Encounters UI
- WEL-4610 Fixed: Phone Calls: Secondary phone is not available for selection in a drop down for a new call
- WEL-4607 Fixed: Patient short info: Order of the address fields is incorrect
- WEL-4549 Fixed: Filter for programs does not work correctly, includes Finished programs
- WEL-4478 Updated: Comm Center: Add possibility to choose primary/secondary phone email for email/sms drafts
- WEL-4775 Updated: Updating assessment answer via API - Send an error in response if request fields sent in upper case
- WEL-4626 Updated: Improvement UI to Patient List


## Designer
- WEL-4631 Designer: Automation: When navigating the table, title of Action Group does not refresh
- WEL-4721 Update rich text editor attachment styles
- WEL-4639 Designer: Add export policy for Tasks

## Admin
- WEL-4630 Admin: Updating user does not update "Last Updated At" without page refresh


Known Issues:
- WEL-4812: Home Page tasks widget displays all tasks without filter taking any effect
- WEL-4778: Tasks created by automation do not display accurate icon and name
- WEL-4802: Creating new tasks from Patient task layout does not persist the patient
- WEL-4803: Some styling and UI issues on Change Email address functionality
- WEL-4811: UI Updates to Admin Webhooks to match our design style better


# Release notes - Version 2022.3.2

### Date: March 5, 2022

## New Features Callout


**Export API: WEL-4440**
This release introduces additions to Export API for Assessment Records, Encounters, Encounter dispositions and comments.
It also adds to Export policies in Designer
Please review updated api docs at https://developers.welkinhealth.com/#export

**Automation Targets: WEL-4562**
With this release, customers can disable automation in Designer, without deleting it. Its useful in cases of debugging your Welkin
configuration, also when you want to temporarily stop automation during data loads or similar activity

## Care
- WEL-4612 Fixed: Patient Short Info: Minor UX updates for Gender and Marital status fields
- WEL-4606 Fixed: Patient Short Info: PoC is not reflected correctly on update
- WEL-4565 Fixed: Patient Short Info: UI issues:More Info vs Less Info and invisible label on full configuration
- WEL-4482 Fixed: utomation: When using Task or Notification as an action, and selecting a specific Role, the first user in that role in a care team is being chosen for assignment,
contrary to the original intent, of selecting a random user in that role
- WEL-4595 Fixed: Automation is not firing for patient without care team with SMS/Email as trigger 
- WEL-4547 Fixed: Automation Target: Triggering an event on a patient without a care team is failing
- WEL-4594 Fixed: Comm Center: Sent email/sms does not display the email address
- WEL-4561 Fixed: SMS Dialog: second sms cannot be send
- WEL-4589 Fixed: Encounter: Changing the time of an Encounter from Encounter view is not changing time
- WEL-4588 Fixed: Encounter History Count does not match the number of history items displayed
- WEL-4587 Fixed: Navigating to Comms Center when an Encounter-Assessment is open removes all recorded answers from view
- WEL-4553 Fixed: Wrong date format in messages
- WEL-4550 Fixed: Phone Number is not formatted correctly
- WEL-4526 Fixed: Notifications keep being delivered to disabled users
- WEL-4384 Fixed: Calendar Automation: Encounter which is created by automation has green color in the calendar, it should have template color
- WEL-4593 Updated: Email drop down takes separate line to support multiple email addresses
- WEL-4497 Updated: Search Bar UX. Clicking outside of search dropdown closes it
- WEL-4473 Updated: Patients -> Filters -> Select current user as a care member by default; add alphabetical sorting to the filters
- WEL-4432 Updated: Region and Territory: system name is used instead of the title
- WEL-4366 Updated: SMS Dialog markup for Care Team Member
- WEL-4316 Updated: Use of scroll across the application

## Designer
- WEL-4472 Version History -> Compare -> Select previous version -> Something went wrong 404 - Failed loading under certain conditions


## Admin
- WEL-4396 Data Audit is taking a long time to load
- WEL-4393 API: Automation Audit Log Improvement: add condition check results and vars values at the time of postponed automation checks conditions.


# Release notes - Version 2022.2.5

### Date: February 23, 2022

## New Features Callout

**Patient List: WEL-3630**

Patients view has been updated to better UX experience. Filters, columns are now aligned to the new mockups and new structure of UX
Search, filters have new UX control, defaults to current logged in member
This is a first update to patients list, in the next releases we will be introducing a new My Patients view, that is tailored for Care team members
with a predefined filter set

**Configurable Patient View: WEL-4344**

With this release, Patient View (on a patient profile, above Action Bar) is now a configurable feature.

Navigate to the Top Info menu in the Designer, pick and choose what fields are visible. Note: All the fields would be available in the profile
however non visible fields would be hidden under "More Info"

**Automation Targets: WEL-4221**

Two new features
1. In this release, we allow automation to go beyond the care team, to "All users with role". This automation, allows for cross functional workflow, that can
unlock new organizational processes.
For example, one can create automation with a trigger on Assessment Completed and route notification to a role "Scheduling Assistant" that is not necessarily
present on the care team
2. Automation triggers now offer more details, by allowing one to use Phase Started and Phase Ended events. This offers more granularity in configuring 
different use cases that need to happen when a patient enters a phase and a patient exists a phase.
Good example is to send a Welcome email when a patient entered the Eligible phase in a program, or Congratulations SMS when a Patient has completed Graduated phase.


## Care
- WEL-4545 Fixed: Comm Center: Send a draft: After sending an email, 5xx error would be presented and email remains in draft, despite being sent
- WEL-4522 Fixed: Patient facing assessment on a mobile device is not optimal for scrollers
- WEL-4521 Fixed: Assessment input error on mobile with Date CDT types
- WEL-4217 Fixed: Relationship therapy throws 5xx error under specific load type
- WEL-4481 Fixed: Encounters -> Create an encounter :Search does not bring a full list of patients, despite them being in the right territory
- WEL-3829 Fixed: Removing attachments and resaving drafts strips out HTML format
- WEL-4230 Fixed: In some cases, assessment API would store phone and date in invalid format (as formatted text vs spec). That is now fixed
- WEL-4388 Fixed: Comm Center -> If the patient primary email/phone is missing and only secondary email/phone is configured, emails/sms are not sent
- WEL-4377 Fixed: My Calendar: View an encounter: Incorrect event icon is used for different delivery types
- WEL-4319 Fixed: Outdated cache is causing issues viewing clients' Assessments tabs
- WEL-4379 Updated: Comm Center: UX and layout issues to improve the experience
- WEL-4150 Updated: Patient facing assessments now support profile links
- WEL-4433 Updated: Task List: Created By column will now display a name of automation disposition group, if task is created by one
- WEL-4434 Updated: When Automation Task is created, the "initials icon" is misleading
- WEL-4207 Updated: Display of Encounter date date/time in message templates. Previously used ISO format is now updated to human readable. More improvements to be done in that area in the future, to support both formats as variables
- WEL-4080 Updated: Better error handling of Docusign errors. Propagating Docusign error codes to Welkin to produce more meaningful indication of what went wrong


## Designer
- WEL-4401 Fixed: Labels on Program Phases on the relations are not deletable
- WEL-4400 Fixed: Numbers in change summary are not aligned correctly, for any 3 digit revision
- WEL-3962 Fixed: Version history : Diff : Improved performance of a diff element 
- WEL-4385 Fixed: Custom Notifications: Title of the action group is now used as title of notification and automation. Appropriate tool tip has been added
- WEL-4219 Fixed: Email templates do match what is created in Designer. When rich text is being copied to designer rich text editor, it is now stripped 
of custom fonts, and needs to be styled in place. That removes a friction of custom font that is not installed on recipient machine and changes the 
look and feel of an email
- WEL-4519 Updated: Terminology and labels in Automation were updated, new UI hints are added to improve readability of different actions and targets
- WEL-4431 Updated: UI tooltip on using form fields vs external to the form cdt fields with instructions

## Admin
- WEL-4288 New: Filter Inactive Users: allow filtering based of User Status (Active, Inactive)

## Known Issues
1. Automation: When using Task or Notification as an action, and selecting a specific Role, the first user in that role in a care team is being chosen for assignment,
contrary to the original intent, of selecting a random user in that role
2. Automation Target: Triggering an event on a patient without a care team is failing. It going to be fixed in a next release
3. Patient List: minor UX issues 
4. Patient Top Info: minor UX issues

## Deprecation Notice
To simplify automation, we removed "Encounter Deposition Created Event" as a trigger in Automation, since its a single record CDT and that event is managed by the system

## Special Note
With the upcoming release, we are making a non-impactful change to use a dedicated webhook per tenant/environment, for the comm center.
The change will make it easier for us to monitor failures and introducing a prep infra to consume new events (clicked and delivered) for email messages



# Release notes - Version 2022.2.1

### Date: February 4, 2022

## New Features Callout

**Unrecognized Communications: WEL-4175**

In this release, unrecognized communication will show if the call has an associated call recording. Welkin users would be able
to listen to the recording before deciding to attach a call

**Patient Model: WEL-4175**

With the latest updates to patient model, MRN is now displayed in global search (if not empty)
and the secondary email field is now available to our customers. 
Customers can now use secondary email to communicate to a patient and it's also included in matching unrecognized communications

**Automation: WEL-4137**

New events are now supported by automation. Our customers can now configure automation on incoming SMS and Email.
That opens a new set of use cases such as generating custom notification, invoking webhooks or sending users sms or email when patient email arrives.

We thank our customers that worked with us in defining such use cases!

**Assessments: WEL-4273**

New functionality is added to conditions on assessments. Our customers can now set visibility on forms using values from arbitrary CDT.
With the release, customers can capture information in a CDT and build a dependency in subsequent forms as a result

## Care
- WEL-4339 Fixed: Display encounters in chronological order for "All Time" view
- WEL-4328 Fixed: SMS Dialog: Incoming JPG does not render
- WEL-4327 Fixed: SMS Dialog: Display correct initials for multi care team users 
- WEL-4325 Fixed: SMS Dialog: Refresh button does not work
- WEL-4323 Fixed: Display tooltip for email with attachment that has a long names
- WEL-4321 Fixed: Email reply now supports adding attachments in reply mode
- WEL-3491 Fixed: Message template to resolved datetime variables in patients timezone
- WEL-4349 Fixed: Calendar display to present correctly 12pm vs 12am
- WEL-4354 Updated: content of "Created By' column in My Tasks view will show logical name of automation instead of technical name
- WEL-4276 Updated: Calendar Encounter view with UI styles to match the styling theme
- WEL-4356 Update: menu text "My Patients" to "Patients"


## Designer
- WEL-4343 Designer: Update UI label and icon when publishing configuration clearly indicate success of published screen

## Admin
N/A

## Known issues
N/A


# Release notes - Version 2022.1.8

### Date: January 28, 2022

## New Features Callout

**Patient Edit: New Fields - WEL-4186**

In this release, several new features were added to patient edit and patient summary fields
1. Secondary Phone
2. Secondary Email
3. Patient Summary enhanced view

Welkin customers can now add secondary phone and secondary email to each patient profile
In addition, Comm center will allow sending messages, emails and performing phone calls to both primary
and secondary fields. Welkin will also consider secondary fields when performing a match on incoming communications

**Calendar Suggestions: WEL-3833**

Several improvements were made to the calendar, to help scheduling meetings/encounters
1. Ability to create multiple meetings at once 
2. Indicate when a meeting is being scheduled on a conflict
3. Indicate when a meeting is being scheduled outside of work hours
4. Show timezones for scheduling an event
5. Updated styling to match general guidelines

**Automation: WEL-4209**

Few additions to Welkin automation. We continue investing into reducing notification fatigue. Customers can now tailor notifications by different methods
to execution of important automation, and reduce overall notifications in Welkin to reduce stress on providers
With this release, customers can add new actions to automation:
1. SMS to Users - Allows Welkin users to be notified when important automation has been executed using SMS
2. Email to Users - Allows Welkin users to be notified when important automation has been executed using Email
Both features support free text or Email/SMS templates
3. Support multiple Roles notification 
4. Custom notification - Notification with custom text on important events 
5. Create Email draft - the draft can now be created without priority and will allow users to customize it in Care and send manually
6. Create SMS draft --the draft can now be created without priority and will allow users to customize it in Care and send manually

**Analytics:**

Customers that use Sisense analytics, can now launch Sisense using out of the box Action Button.
Note: Sisense setup and reports must be done prior and separately. Talk to your CSM about a demo

**Encounters:**

Few improvements to Encounters in this release:
1. Color picker - is now part of the Encounter template. Allows Welkin customers to select color coding by default. Can be changed in Care later by the Users
2. Instructions field - is not located more conveniently on the page
3. Encounters view on Patient profile now support "All Time" filter, that is also a default and will show all Patients encounters
4. Encounters can be created from Patient profile using new Action Bar button, with prepopulated patient - makes it easier create on the fly encounter without extra navigation

**Communication Center:**
1. New file types are now supported by the communication center. Customer can send/receive emails with DOC and DOCX files as attachments
2. SMS Dialog mode is introduced. In addition to table view, customers can now see SMS conversation in a traditional conversation mode, similar to chat

## Care
- WEL-4263 Fixed bulk update Tasks
- WEL-4233 Fixed bug in Global search to reduce irrelevant records
- WEL-4227 Fixed bug in Unrecognized Communication -> SMS throwing back to Root Page
- WEL-4167 Fixed issue with creating multiple new assessments at the same time
- WEL-4028 Updated a text for JWT token error to user friendly
- WEL-4231 Fixed bug on assessment API returning phone in a wrong format
- WEL-4285 Fixed Data Exports - under certain conditions data export as CSV failed
- WEL-3864 Insights: Fixed Totals on Calendar Utilization 
- WEL-3491 Fixed: Date variables in a message template now resolve to Patients timezone
- WEL-4192 Fixed: Unable to update encounter records via API since CDT can no longer be found


## Designer
- WEL-4201 Improved performance of publishing a draft in Designer
- WEL-4292 Newly added: Message templates now support encounter disposition fields


## Admin
- WEL-4171 Admin: Data Audit - added new types for Communication and Calendar


## Known issues
There are several known issues, that would be fixed in next releases:
1. Custom  Notifications: Text is not displayed correctly in Care
2. SMS Dialog: issue with rendering attachments, inaccurate initials of the sender are present, refresh button does not function correctly

# Release notes - Version 2022.1.1

### Date: January 14, 2021

## Care
- WEL-4166 Unrecognized calls were set to 'false' when for recordings
- WEL-4162 No notifications to Care team about missed calls if patient hangs up after dial tone (recognized\unrecognized)
- WEL-4127 Resolved 400 error triggered on Assessment completion
- WEL-4106 Error in how events appear when viewing a team member's calendar
- WEL-4095 Unrecognized Communications -> Email\SMS -> Display presence of attached files in the table and on the Assign SMS drawer
- WEL-3853 Search bar does not allow pasting phone numbers and does not allow using area code + phone number
- WEL-3727 Encounters Report: Some fields were missing data
- WEL-4164 PFA link after its expiration date -> hide "#1 Aws Jwt Token has expired" error
- WEL-3847 Custom date encounter views is not working for dates prior to November 1
- WEL-3732 Clicking the phone number in Encounter takes user to Call Screen
- WEL-3665 Working Hours is now represented in calendar for Sunday for different view types
- WEL-4134 Encounter: Changed comments field type from text field to text area for longer comments
- WEL-4183 Tasks -> Change some info -> Save button is inactive; Change status -> error is displayed

## Designer
- WEL-4131 Resolved getting blank screen when updating a role
- WEL-4098 Assessment: "readOnly" field names are duplicated

## Admin
- WEL-4156 Logs -> Add more info: tenant and instance name
- WEL-4138 Exclude welkinhealth.com email domain from seat/license count
- WEL-4149 Automation -> If action group is deleted in the automation then automation event in logs should have correct status 'automation not found'
- WEL-4058 Admin: Display username user name field as read only. Backend doesn't allow user to edit it.

## API
- WEL-3826 Add info about user activity to API responses

## Known issues
- WEL-4216 Encounters Filters 'Today', 'This week' and 'This month' show all encounters


# Release notes - Version 2021.12.11

### Date: December 23, 2021

## New Features Callout
**Expiration dates configurable on PFA: WEL-3981**

With this feature release, customers can configure expiration dates for Patient Facing Assessments.
1. Navigate to Admin -> Security Settings -> General 
2. Select any number of days between 2 and 30 for PFA link to be valid

**Configurable User Navigation Menu: WEL-4023**

With this release, Welkin is enhancing role level customization. For each role, customers will now 
be able to configure User Navigation Menu (left green bar in Care) by assigning menu items for 
specific roles and removing items for roles that they are not relevant for. 
For example, customers can completely hide Tasks or Home page, if their implementation does 
not need such items for certain or all roles

**New Roles UI in Designer: WEL-4022**

New User Interface for Roles in the designer. With that release, each role will display in a read 
only mode all the security policies that are attached to it and will display what User Navigation 
Menu items are available for each role

**New Security Policy UI in Designer: WEL-3825**

New User Interface for Security Policies in the designer.To further simplify working with security 
policies, new user interface is introduced. 
At this point, its UX improvement without any fundamental functional changes. 
New user interface is part of a new pattern of interfaces that our team continues to work on,
to make Designer as intuitive as possible.

**New layouts UI in Designer: WEL-4081**

New User Interface for Layouts in the designer, will make it easier for customers to visualize 
how components will be placed on the layouts.

## Everything Else

## Care
- WEL-4061 Email/SMS templates should be organized by Alphabet order
- WEL-4032 Comm Center emails: Accurately display all addresses from 'TO' field
- WEL-4056 Incoming phone numbers are not being identified as belonging to recognized patients
- WEL-3847 Custom date encounter views is not working for dates prior to November 1
- WEL-4053 Encounters: Viewing encounters on calendar will display original users calendar + 
encounter assignee calendar
- WEL-4113 User Notifications for Voice Call Missed Call operational
- WEL-4003 Notifications for assessment completion should go to care team only
- WEL-4096 Communication Center ->Unrecognized Communications: Message text is right justified
- WEL-4094 Ability to delete old drafts in communication center
- WEL-4093 Communications Center: ''Select Files to Attach'' UI improvements 

## Designer
- WEL-4057 User Notifications. Disable email / sms template dropdowns if not checked
- WEL-4118 "Not Equal To" Conditional logic option is not operational under certain conditions

## Admin
- WEL-4073 Data Audit/Security Audit -> Search doesn't work by part of name, only Full name
- WEL-3978 Security Audit -> Improve functional filters work

## Known issues
N/A


# Release notes - Version 2021.12.5

### Date: December 10, 2021

## Care
- WEL-4049 Profiles added through an Assessment do not appear on the profile detail or in the patient CDT
- WEL-4048 Improve error message when trying to send Docusign using SMS/Email for a patient that is missing SMS or Email in their profile
- WEL-4047 Care -> Unrecognized Communications -> Home page -> the area with the patient info in the line is not clickable
- WEL-4046 Care -> Insights -> Export Data : fixed 500 error that appears in certain cases
- WEL-4037 Patients associated with a profile do not appear on the profile detail
- WEL-4035 Error on export Voice calls - Fixed errors on exporting voice calls for missing enum
- WEL-4026 Care -> Communications Center -> ''Select Files to Attach'' pop up : fixed UI to include scroll for smaller resolutions
- WEL-3964 Assessments: Template created for an assessment but getting an error when trying to view.
- WEL-3934 Care - Programs: Finished programs move to the down of list, latest added - display on the top
- WEL-3755 Care - Encounters: Add assessment and click on it to open -> Endless loading
- WEL-3955 Care: Improve "Add Assessment to Encounter" UI according to the new mockups

## Designer
- WEL-4005 Designer -> CDT -> Min length and Max length must not be negative

## Admin
N/A

## Known issues
N/A


# Release notes - Version 2021.12.4

### Date: December 8, 2021

## New Features Callout
Designer: Add default button for "New Encounter" to the action bar.
New action bar button allows instant creation of encounter from any patient layout as a convenience method
- WEL-3924 

Docusign Integration: Send documents for signature using SMS.
In this release, customers that enabled SMS delivery on their docusign account, can now send from welkin documents for signature using SMS.
The sms will be delivered directly from docusign and can be opened and signed on mobile device.
New SMS configuration option is now available in the designer for docusign templates
- WEL-3883 
- WEL-3882 
- WEL-3878 

API Client: with Other Team Member Events permission, api client can modify the host of the event to a different user
- WEL-3697


## Everything Else

## Care
- WEL-4025 Commcenter: Receiving emails don't work when patient send email to several users at the same time. Displays TO/CC list of all emails that patient used for sending email to welkin, including multiple users support
- WEL-4019 Care: Assessments - validation errors disappear when you make changes to another field
- WEL-3899 API: add search and pagination to request for getting patients in all tenants
- WEL-4036 Saved data in Profiles does not appear in edit pane from list view page
- WEL-4031 Care: move ids to body in the request /\{\{tenant\}\}/\{\{instance\}\}/reports/patients - Fix to support reports dataset being too large
- WEL-4021 Care: Export Data -> Update programs export with new columns
- WEL-4018 Care: View Encounter -> Edit encounter disposition -> Incorrect displaying of calendar
- WEL-4000 Notification for Unrecognized communications does not work in the All view in the notification area
- WEL-3997 Filters for Unrecognized communications do not work by computing values in correctly
- WEL-3993 Unable to finalize assessment if required boolean field is present
- WEL-3984 Formulas in fields not displaying correctly
- WEL-3949 Error when loading list of patients for program phase in insights - fixed report too large
- WEL-3785 Care: Tasks drawer: update to the UI to conform to new UI specs
- WEL-3611 Encounters and Calendar Insights pages are not loading any data - fixed the report
- WEL-4011 BUG: Care: Spelling, encounter status "CANCELED" -> "CANCELLED"


## Designer
- WEL-4024 Designer: Remove the ability to make boolean fields required in assessments


## Admin
- WEL-3845 Admin Performance improvement: Slow performance on request admin/audit-data and admin/patients for over 50,000 patient typeahead


## Known issues

N/A



# Release notes - Version 2021.12.2
### Date: December 3, 2021

## New Features Callout
- WEL-3952 Display, Edit, Search by patient's MRN field
- WEL-3711 MMS - Ability to add SMS attachment similar to email.
- WEL-3371 New User Menu for Unrecognized Communications with notifications
- WEL-3624 Recurring triggers in Automation 

## Everything Else

## Care
- WEL-3966 Encounters: Show the 'Updated' date for Planned encounters if created date is not equal to updated date
- WEL-3954 Notifications: Counter for unread notifications is not changed for 'Task updated' action
- WEL-3953 Pagination overflows the dropdown-menu
- WEL-3592 Task: Patient name is not displayed in the notification for the Task
- WEL-3814 Align content title and "Create" button
- WEL-3799 Disable regions not related to user region when creating a patient
- WEL-3936 Profiles: The height of Menu should be static
- WEL-3934 Programs: Finished programs move down the list, latest added, display on top
- WEL-3932 Programs: Add Program name to the alert for Updating program and Add alert at the same style for Program adding
- WEL-3931 Programs: If phase has no description - show 'No Description' at popover
- WEL-3844 Validate phone numbers after resaving a patient
- WEL-3980 Reply to email from inbox: Sent status of email is displayed at Inbox
- WEL-3905 Body of incoming emails in html format
- WEL-3898 Text of message for what user has been replied is not formatted
- WEL-3827 Welkin Export to include Programs
- WEL-2954 Communication Center: Formatting of HTML in email signatures is removed from threads
- WEL-3807 Profiles: Order in Designer for preview can dictate order in Care preview 
- WEL-4007 Implement pagination in calendar insights
- WEL-3940 Tasks are currently not allowing users to select an "Assignee name" that is not themselves
- WEL-3925 Care: Notifications -> Time of email is incorrect at list of emails
- WEL-3863 UI doesn't allow user to view entire dropdown for certain Program phases dropdowns
- WEL-3841 Data audit doesn't show target name for changes to the PATIENT_PROGRAM object
- WEL-3216 Graphs not graphing the data points
- WEL-3843 Assessments: Take an assessment with text area fields type -> Text is displayed with a delay
- WEL-3759 Calendar picker -> Select time range and not apply changes -> Open calendar -> Selected value is highlighted
- WEL-3704 Calendar -> Day view shows incorrect Working Hours
- WEL-3660 Date is not showing on Homepage for Encounters
- WEL-3513 Click on unread email notification going to "Sent" box instead of "Inbox"
- WEL-3960 PFA : CDTs are not populating in Assessment Read-only fields.
- WEL-3876 Notification: Red Icon on notification bell is not showing for missed recognized calls
- WEL-3976 Assessment is throwing a 500 error when finalizing
- WEL-3963 CDT permissions disappeared from policy
- WEL-3979 Issues with formula fields in profiles
- WEL-2783 Template variable for pre-populated values is not working

## Designer
- WEL-3938 Conditions in Forms: If CDT has Value Type = Integer or Float then condition doesn't display the value

## Admin
- WEL-3950 Filter by license seat does not work for unassigned
- WEL-3744 Search in Security Audit does not work
- WEL-3872 Show phone ID for using it in API
- WEL-4017 Automation Audit -> Add sorting by date : newest on the top

## Known issues
N/A



# Release notes - Version 2021.11.10

### Date: November 17, 2021 

## New Features Callout
- WEL-3804 Add rich text editor when selecting template without HTML
- WEL-2939 Admin: Manage deleted users


## Everything Else

## Care
- WEL-3901 Encounter dates are inconsistent
- WEL-3896 "Add Field" button not accessible after adding a few fields
- WEL-3874 Error when trying to complete the assessment
- WEL-3870 DocuSign document error when uploading to Welkin 
- WEL-3846 Communication Center (SMS) Templates with many symbols (that exceeds the allowed SMS limit) -> Impossible to edit the sms
- WEL-3812 Encounters and Events: Cannot create any event that ends at 12am
- WEL-3783 Task Creation: Inactive users should not be displayed at list of Assignee
- WEL-3747 Cannot edit encounters on other user's calendar from Calendar
- WEL-3735 Notifications: Red icon goes away after opening Notifications drawer
- WEL-3547 Calendar(Working hours) Schedule of days is saved with an offset of one day
- WEL-3218 Patients Side section is not highlighted when navigating to a specific patient


## Designer
N/A

## Admin
N/A






# Release notes - Version 2021.11.8

### Date: November 10, 2021

## New Features Callout
Home Page: Missed recognized calls, will now appear in New and Unread Communications widget on the home page
- WEL-3858 
- WEL-3740

## Everything Else

## Care
- WEL-3861 Assessment completing 500 error - The error manifested in assessment with pre-populated values from the variables
- WEL-3800 Care: Cannot fill the assessment with CDT field - Profiles reference
- WEL-3831 Profiles, updating CDT record throws 400
- WEL-3483 Care: Patient Edit: Territories need to be displayed in alphabetical order
- WEL-3836 Cannot finalize assessment - the issue appeared for assessments with read only fields
- WEL-3840 Unable to send DocuSign docs via email - default configuration is missing 
- WEL-3839 Recognized SMS not routing to patient profiles; arriving in "unrecognized" - for incorrectly loaded phone numbers
- WEL-3837 Care: Bug: Encounter details section - Overflow of visual components
- WEL-3857 Care -> Encounters: The page does not fit on the screen regardless of the screen size
- WEL-3855 Unable to archive notifications
- WEL-3848 Encounter button is not showing words when resolution not 100%
- WEL-3805 Change the type of input for Rich Text editor for Spellcheck working
- WEL-3635 Email replies don't maintain their formatting

## Designer
- WEL-3818 Designer -> Message Templates -> Copy a message template instead of starting from scratch

## Admin
N/A

## Known issues
Some customers may experience an issue with docusign integration. Two known issues right now:
1. Signed document is not visible in Welkin
2. Document cannot be sent out

Both are being investigated at this point

# Release notes - Version 2021.11.5

### Date: November 05, 2021

## New Features Callout

### New Encounters and Calendars UI

This feature is a result of customer feedback that we recieved over last quarter. It features a redesigned Encounters UI, Events UI, API, filters and other 
capabilities.

Some of the new capabilities include:
- Synchronization of calendar events and encounters, allowing seemless integration between the two
- Different types of events for leave and team meetings vs encounters, including all day events
- Redesigned and improved UI
- Ability to schedule events and encounters for other users
- Improved filters and search
- Persisted history of all the changes to ensure accurate data representation with improved audit log
- Improved navigation between calendar and encounter


### Profiles
In the new release, Welkin supports a concept of Profile. Profile is a new core entity, that can be defined and configured in the designer and can be used
to relate to patients. Typical use cases of profiles include representation of Family Members, Hospitals, Physicians that provide support to the patients but 
not necessarily have direct access to Welkin platform.

With this powerfull features, customers can manage multiple lists of profiles, associate profile records with patients (using our flexieble CDT model) and fully customize the experience

Profile records can participate in the Assessments as well, as a response to a question. 
As usual, profiles will require a security policy configuration

This is the first release of Profiles and there would be subsequent releases with enhaced functionalities in the near future

### Assessments: Using conditions to hide and show required questions 

Welkin Platform offers two levels of required fields. CDT level will ensure data consistency and is enforced through the API. Another level
is an assessment level. With that feature release, required questions can be validated in the UI on the assessment level, and as a result can participate in 
conditional show/hide functionality. In order for the feature to function properly, the underlying CDT cannot have required fields and the validation will only work in
the assessments user interface
- WEL-3693 
- WEL-3516 
- WEL-3514 

### Assessments: Using CDT variables in the assessments questions.

This feature allows one to use values from a CDT in order to form questions in the Assessments. 
Using Welkin variable builder, one can refer to values previously
collected in order to present dynamically created question. 
Welkin will also persist the questions with resolved values (values to the moment of finalized questions) in order
to maintain integrity for presentation of the values over time
- WEL-3362 
- WEL-3359 
- WEL-3358 
- WEL-3357 
- WEL-3360 

### Assessments: Addition of Contains operator 

This feature enhances Welkin's list of supported operators, and allows one to use Contains for multi select lists for condition evaluation in the assessments
- WEL-3505 
- WEL-3257 
- WEL-3486 
- WEL-3259 
- WEL-3258 
- WEL-3256 

### Assessments: Scoring of fractions

Another improvement in Assessments mechanism, we allow scoring of fractions within our built in it scoring mechanisms
- WEL-3594 
- WEL-1742 

### New Automation

This release includes a new user interface in Automation UI in Designer. It offers a simpler and more 
intuitive way to configure automation.
This feature was based of customer feedback and was built in collaboration with many of our customers. Feel free to reach out for more suggestions on improvements
- WEL-3677 
- WEL-3675 
- WEL-3534 
- WEL-3490 
- WEL-3689 
- WEL-3449 

### Message Templates improvements
Now, you can use Encounter Variables within the message template (sms/email/chat) messages.
The variables, will resolve in runtime, similar to the currently available variables
- WEL-3427 
- WEL-3209 


### Phone Tree
Phone tree capabilities now include Users language (Primary and Secondary languages in the User Attributes), honoring the working hours system and a signal while the call is being connected

- WEL-3498 
- WEL-3493 
- WEL-3615 
- WEL-3620 
- WEL-3666 


### Care UX Updates
Clicking on Tasks and Programs will open a drawer (similar to assessments and CDT) and will offer similar UX interaction for consistency
- WEL-3597 
- WEL-3595 


## Everything Else
## Care
- WEL-3586 Export API: Patient - matched JSON response to include care team
- WEL-3496 Fixed: Clicking on new email notifications doesn't open the new email
- WEL-3452 Draft Emails - Set up communication and automation to send email but no draft in comm center
- WEL-3451 Care -> Communication Center -> Emails: Reassignment emails with attachments causes and error
- WEL-3555 Remove wifi symbol next to patient name in My Patients
- WEL-3529 Can't attach files to emails sent from Welkin
- WEL-3700 Care -> Calendar: View an event with a lot of info on a monitor with small resolution -> No scroll, impossible to manage an event
- WEL-3687 Care -> Comm Center: Filtering email templates by label is case sensitive
- WEL-3637 Care: Tasks -> Bulk Edit -> Something went wrong
- WEL-3612 Care - Calendar: Select Month view ->Montly calendar selector to show a correct month
- WEL-3540 Fixed: Use local time instead of "Started Date" for Notes & Assessments in encounters is in UTC
- WEL-3517 Care -> Communication Canter -> New SMS -> Correct counter view and highlight the counter and the text of the note in red
- WEL-3453 Updated usability for Forms/Assessments Links that are formed using variables in read only text
- WEL-3333 Calendar is moving appts to one day prior to the date requested
- WEL-3691 Care -> Assessments: Impossible to Finalize a form if it has required fields with types boolean, integer and float
- WEL-3539 Fixed UI components on the insights page if there's overflow of data
- WEL-3518 Members no longer receiving push notifications with in app messaging
- WEL-3776 Assessment: Multi-select list is not showing the conditional question in a multi list scenario
- WEL-3278 PFA: Frame Notification mechanism when PFA completed - allows one to catch an event of PFA completed

## Designer
- WEL-3681 Errors in Form with OR conditions using Equals operator



## Admin
- WEL-3568 SSO settings: Resolved issue with Google SSO login flow and updated the instructions
- WEL-3544 Admin: Cannot assign env to api client
- WEL-3523 UI: Label is now being shown instead of the value
- WEL-3511 Admin: Click on "Plus sign" in Automation Audit does not work
- WEL-3455 Admin - Users / Care - Patients -> Lists must be sorted by Full Name
- WEL-3435 Admin: Include custom user fields in bulk update
- WEL-3686 Admin: Postponed Tasks - fixed and issue with opening the page under certain conditions
- WEL-3743 Admin: Fixed sort order of users after bulk update


## Important Callout

Designer will start enforcing Regions/Territories consistency checks. It will prevent one from deleting territories if there are patients assigned to them
- WEL-3448 
- WEL-3166 

# Release notes - Version 2021.10.1

### Date: October 03, 2021

## New Features Callout
Designer: Webhook: Add a list of standard headers to support webhook integration
- WEL-3393 

Care: Comm Center: Rich text editor is now supported on New Email. Similar to HTML Template in designer
the email created in rich text format will be converted to html (in a closest possible style) and sent out to the patients
- WEL-3442 

## Everything Else
## Care
- WEL-3495 Email user notification doesn't use subject specified in the template
- WEL-3484 Display of date date/time in message templates
- WEL-3399 Users can't access our programs page
- WEL-3501 Care -> Communication center -> SMS -> Correct information message and character limitation - UX improvement
- WEL-3458 API: Phone Tree: Add action for call redirection
- WEL-3426 API: Phone Tree: Add condition for coach's working hours checking
- WEL-3472 Care Portal Tasks UI - Added a scroller for large list of tasks templates
- WEL-3414 Patient Program is not correctly loading
- WEL-3400 Care: Programs: Start a program 'Not in Phase' -> 500 error
- WEL-3395 Care: Assessments: Incorrect number of assessments is displayed
- WEL-3316 Care - Comm Center: -> SMS -> Add as starred Scheduled SMS -> Date and time is changed to current
- WEL-3237 Security: Prevent HTML injection @ comment section
- WEL-3305 Care: Comm Center: Mark sms as 'failed' if we get error from SMS provider
- WEL-3291 Comm Center: Manually created draft emails should default to "No Priority"


## Designer
- WEL-3402 Designer: Older configuration is causing issues within program and phases - cannot create draft in certain conditions
- WEL-3403 Designer: The custom field setting for value type is not being inherited when used on the data type field
- WEL-3384 \[Designer- Automation\] Set 'Condition Check type' as default ' After Trigger'
- WEL-3005 Designer - Create Layout - Added indicator that Layout components are required - UX Improvement
- WEL-2996 Designer: Create Data View - Required fields to be indicated - UX improvement


## Admin
- WEL-3410 Admin -> Security Settings -> Turn on Two-Factor Authentication -> 500 error

## Important Callout
- WEL-3430 Care: Calendar -> Working Hours: fix order of days of week 
We recently discovered that in some cases there is a disparity of working hours. Some users experienced 1 day shift in working hours
This was recently fixed in the release but may cause some disruption

**We ask all our users that use Work Hours feature to review their work hours for correctness and update if necessary**

# Release notes - Version 2021.9.4

### Date: September 22, 2021


## New Features Callout
Editing HTML templates: When editing HTML template in Care, Rich text editor is now supported.
The editor, will convert the message to HTML and will send it to the patient. At this point, only editing HTML 
templates is available, composition will be released in subsequent releases
- WEL-3068

Timezones: Welkin reduced the list of timezones to a smaller and more manageable list of timezones.
The goal is to simplify the lists and make it easier for our customers to use.
```
{ label: 'Atlantic', value: 'Atlantic/Bermuda' },
{ label: 'Eastern', value: 'US/Eastern' },
{ label: 'Central', value: 'US/Central' },
{ label: 'Mountain', value: 'US/Mountain' },
{ label: 'Pacific', value: 'US/Pacific' },
{ label: 'Alaska', value: 'US/Alaska' },
{ label: 'Aleutian', value: 'US/Aleutian' },
{ label: 'Hawaii', value: 'US/Hawaii' },
{ label: 'Western European', value: 'WET' },
{ label: 'Central European', value: 'CET' },
{ label: 'Eastern European', value: 'EET' }
```
- WEL-3309 
- WEL-3048 

Admin: New UX for Custom attributes, to make it user friendly
- WEL-3212 


## Everything Else 
## Care
- WEL-3389 When creating a task with a comment, the server returns an error
- WEL-3377 Unable to trigger automations with conditions
- WEL-3354 Forms -> Creating a form with a condition to show next question, it is not displayed after answer on first one
- WEL-3353 Improve emails sent via automation - using sender name instead of automation name, leaving empty subject when needed
- WEL-3330 Inactive users can be assigned to care teams
- WEL-3319 Care - Data Views: Formulas will not display the calculated value if all fields in calculation are not in the view
- WEL-3317 Care - Live Chat Search for a message -> Open it -> Some messages are duplicated
- WEL-3308 Care -> Insights -> User doesn't exist, Request Method: GET Code: 404
- WEL-3296 Care: Program History: when more than 10 steps are in, the padding is off
- WEL-3283 New Email/New SMS/New Phone Call/New Chat drawer can be opened, even if no config is enabled
- WEL-3214 Care -> Insights -> Communication -> Unrecognized Emails\\Unrecognized SMS\\Unrecognized Calls -> Display new ones at the beginning of the list, not at the end
- WEL-3211 Email automation isn't sending if there's an action delay
- WEL-3165 Care -> My Profile -> Save profile with readonly attributes -> Error 400
- WEL-3129 Comms center phone section does not display any information on the number that was called by the coach
- WEL-3064 Care: Home screen showing unread communication user name as root
- WEL-2894 Client email addresses are encoded with extra information
- WEL-3227 API: Endpoint for formula validation

## Designer
- WEL-3288 rename Erx to eRx in designer and care UI
- WEL-3252 Designer -> Layouts -> Select UI components with long names -> They are displayed not correctly
- WEL-3302 Designer: Add deleting program/phase cascading consistency consistency check \(delete / update\)
- WEL-3254 Designer: Draw digit \(or non-binary\) condition
- WEL-3207 Designer: use formula values in charts
- WEL-2948 API: Add possibility to use condition with digit gathering for phone tree

## Admin
- WEL-3351 userAttributes field renamed to customUserAttributes: restored backward compatibility in addition to new service
- WEL-3304 API Clients -> Incorrect view of the page with long text fields and after minimizing a page
- WEL-3293 Bulk Error message breaks off in a middle of a word, when bulk assigning seats and licenses
- WEL-3128 Admin: API Client: Bulk update screen jumps
- WEL-3314 Add User Attributes query params - to support new UI capabilities for Users View
- WEL-3295 Data Audit: Programs and Phases are not part of Data Audit
- WEL-3294 Admin: Update help text for Seats and Licenses
- WEL-3093 API: Only API client should have access to data export API

# Release notes - Version 2021.9.3

### Date: September 10, 2021


## New Features Callout
New Automation: New Triggers and Actions for Encounters
- WEL-1783 

Programs and Phases: In this release, new UX and new Features for Programs, including:
1. Transition History
2. Order of Phases 
3. New User interfaces in Designer and Care
4. Support for multiple finishing phases in each program
- WEL-3191 
- WEL-3190 
- WEL-3189 
- WEL-3187 
- WEL-3186 
- WEL-3184 
- WEL-3195 
- WEL-2890 

User Attributes: Support for Dictionaries on User Attributes
- WEL-2924 
- WEL-2923 

eRx Integration: Enhancement to eRx integration: Out of the box Action Bar button and redirect improvement
- WEL-3077 
- WEL-3076 
- WEL-2900 

## Everything Else
## Care
- WEL-3287 Care: -> Create notification for Assessment Completes and Phase Changed -> User doesn't receive email, sms and sometimes notifications
- WEL-3286 Care -> Notifications -> emails\\sms\\notifications come in an amount of 10
- WEL-2672 Care: Data View - Not showing sort order correctly
- WEL-3311 API Assessment Migration. Script to remove none existent phases in assessments.
- WEL-3301 API: Add deleting program/phase cascading consistency consistency check \(delete / update\)
- WEL-3242 Care: Automation Notifications for User and PoC do not work as expected
- WEL-3213 Care -> Click on the profile icon -> Email is displayed incorrectly
- WEL-3233 Tasks not showing up in "My Tasks" or "Home"
- WEL-3231 Zoom action bar button doesn't work
- WEL-3210 Care -> Text Reply - No "Send Button" is visible under low resolution
- WEL-3198 Care -> Communication Center -> Emails -> View a letter with pdf -> It is not visible where to set the checkbox for selecting a document
- WEL-3194 When a member profile is clicked in the appointment on Calendar, it takes you to the members eRx page in their profile, not their Summary.
- WEL-3084 Data Type default values are not working for previous record
- WEL-2984 Care: CommCenter - Sms description bottom text wrong
- WEL-3169 Care: If comm center is not setup, updated UX page for better clarity
- WEL-2877 Care: move cadence to another drawer
- WEL-2729 Automation: Task not getting created on automation when assignee is not POC
- WEL-3159 \[Care -> Communication Center\] -> Edit draft with html template -> Save -> Send -> Email comes with tags
- WEL-2931 Care: variable to generate link to task in notification template

## Designer
- WEL-3274 Able to publish changes that actually broke the configuration
- WEL-3249 Change action bar default button icon names
- WEL-3168 Designer: New Icons for "New Email", "New SMS" and "New Phone" 
- WEL-3276 Add types Automation Notifications for User
- WEL-3037 Add consistency check for assessments
- WEL-2770 Cannot add goals with shared/same task templates
- WEL-3155 Designer: security policy to allow API clients access export APIs



## Admin
- WEL-3280 Admin shows a message that license exceeded without a reason
- WEL-3105 Add domain validation for tenats
- WEL-2974 Admin: Postponed Tasks show archived instances
- WEL-3125 Error message on creating instances
- WEL-3150 Admin: Security Settings Page: One menu out of context and title is off


# Release notes - Version 2021.8.5

### Date: August 20, 2021


## New Features Callout

Custom User Attributes: Our customers are now empowered to define custom user attributes
The feature, configurable from Admin, allows customers to define custom user fields (similar to patient CDT)
that would be shown on User Profile in Care. With that, customers are able to tailor user information to their 
business needs and processes.
- WEL-3164 
- WEL-3163 
- WEL-3161 
- WEL-2903 
- WEL-2852 
- WEL-2904 
- WEL-2863 


New Automation: Automation Triggers for Calendar events is now available. Allows our customers to use Welkin 
powerful automation to be triggered of Calendar events (create, updated, deleted)
- WEL-3103
- WEL-3095
- WEL-3041

New Data Export formats: Allows our customer to export data in JSON format (API Clients only) for easy consumption 
by different external systems
- WEL-3094 
- WEL-2914 
- WEL-2913 
- WEL-2910

New Security Settings: Customers are now able to configure password requirements (in Admin).
In addition, OneLogin and PingIdentity SSO providers were added to our supported list
- WEL-2562 
- WEL-2943

Seats and Licenses: Welkin has introduced a seat model. This model will simplify understanding 
how many seats are used by customers and will avoid uneccessary charges for invited but not active users
The feature will require every active user or api client that is using the system to have a seat associated with them
it will also indicate number of agreed environments and other integreations

**Important**: To avoid any service disruptions,Welkin currently does not enforce 
the feature. Please reach out to your CSM for further setup and timelines to enablement
- WEL-3111 
- WEL-3072 
- WEL-3071 
- WEL-2892 
- WEL-2859 
- WEL-2839 

## Everything Else
## Care
- WEL-3158 Care\\Designer -> Automation -> during the mailing of a letter during automation html template is sent in an incorrect form
- WEL-3149 Care: Communication Center -> Page overflow \(impossible to scroll down the page\), for long email and attachments
- WEL-3115 Care: Insights -> Territories -> Patients Distribution -> Select None in the drop down lists -> "Something went wrong" page is shown
- WEL-3089 Care: Encounters are off by -12 hours
- WEL-3066 Care: Calendar -> View an event -> Event has incorrect time in the drawer
- WEL-3065 Care: Calendar -> Unknown participant appears after event editing
- WEL-3014 Care: Communication Center - Starring received email throws error
- WEL-3010 Care: Communication Center - Display Users and Patients number before placing a call
- WEL-2982 Care: Homepage: Clicking on a task on Homepage brings the user to the task list but does not open the task in question
- WEL-2899 Care:  Calendar -> Some users are not able to create an event in the calendar
- WEL-3092 Care: SMS notification should open SMS list
- WEL-3080 Care: API: Send WEB Hook with object that triggered notification, e.g. appointment..
- WEL-3026 Care: Mark drafts as failed when exception during sending
- WEL-3063 Care: Calendar -> Create event -> Participants -> Users have access to the environment, but they are labeled "no access"
- WEL-2980 Care: Homepage: Only able to click on Time and Event names to open in Calendar.  Not on name field
- WEL-2951 Care: Reassigning unrecognized emails patients throws errors


## Designer
- WEL-3104 Designer: add webhook config in user notification
- WEL-3004 Designer - Edit Security Policy - Patient Info Selection
- WEL-2989 Designer: Disable bulk edit if edit operation is disabled on Data View
- WEL-2930 Designer: New Variable to gen link to a task in notification template


## Admin
- WEL-3025 Show http response code when fire webhook in audit log.
- WEL-3030 Automation Audit -> Add info about webhook call result


# Release notes - Version 2021.8.1

### Date: August 09, 2021


## New Features Callout

Labs Integration with Health Gorilla. As announced earlier today, Welkin now has 
support for Labs integration with our partnership with Health Gorilla. This 
integration allows our customers to order labs and see the results from a patient 
profile in Welkin
- WEL-2876
- WEL-2875 
- WEL-2823

New and Improved User interface for Communication Center. Based on customer feedback 
we made several improvments on Communication Center setup in Admin and in Care. 
It includes usability issues and prettier UI
- WEL-2804 
- WEL-2803 
- WEL-2885
- WEL-2902
- WEL-2877
- WEL-2826 
- WEL-2825 
- WEL-2824 
- WEL-2815

Formula Fields in CDT allows customers to created formulas based on other fields in CDT
It can offer an alternative to scoring without using assessment, and enables other 
computations as needed
- WEL-2108 
- WEL-2749 

New Notifications User Interface Design. Based on customers feedback, we made it better
- WEL-2807

New Action Buttons and Layout for Communication Center offers new
ways to configure access to communication center, by enabling prepacked layout (assign it to role) 
or using new action bar button for quick "New Email", "New SMS", "New Chat" and "New Phone" features
- WEL-2853
- WEL-2851
- WEL-2837

## Everything Else
## Care

- WEL-3029 Care -> Calendar -> Get events not assigned to encounters
- WEL-2881 Care -> Live Chat -> Search a message -> Invalid format for chat token Request Method: GET Code: 400
- WEL-2880 Care -> Live Chat -> Send a message -> Unknown error, Method: POST Code: 500
- WEL-2866 Care -> Home -> The "New & Unread Communications" block does not immediately display incoming emails
- WEL-2684 Home page shows yesterday's encounters in the "Events Scheduled for Today" section
- WEL-2830 Zoom link needs to be updated with /s/ instead of /j/
- WEL-2576 API: Encounters - Cancelled calendar event details show remain as reference in Encounter
- WEL-2544 Care: Encounters - Cancelled calendar event details show remain as reference in Encounter
- WEL-2540 Care: Encounter: jump to encounter from calendar and home page
- WEL-2956 BU: webhook inconsistent structure 'source name' field between user attribute and assessments web hooks
- WEL-2918 Care -> Calendar -> Select Day View -> Create an event -> You need to refresh the page to see the created event
- WEL-2862 Care -> Insights -> Territories -> Click on the territories chart to view detailed info -> Error 600, site doesn't response
- WEL-2934 Care: Unable to view calendar event if user was deleted or admin removes user's access
- WEL-2988 Care: My Calendar: Month view displays event at incorrect time
- WEL-2978 Care: Data View - Hover over on long text is not readable
- WEL-2976 Care -> Encounters -> Remove an encounter from the calendar -> Select Existing Event -> The selection of events should display only those events to which the action is applicable
- WEL-2968 \[Care -> Calendar\] -> Click settings icon -> The site doesn't response
- WEL-2958 Care: Assessment: Boolean and List with Radio buttons are not represented correctly
- WEL-2796 GET users/\{ID\}/encounters endpoint missing encounter
- WEL-2743 Insights: Task summary csv should include the completed tasks

## Designer
- WEL-2850 Designer: Version 2 user notification configuration
- WEL-2779 API: add config condition for user notifications
- WEL-2777 Designer: update UI to support improved automation version.
- WEL-2776 API: Automation: new structure: triggers, action groups
- WEL-2722 API: Automation: trigger on upcoming encounters
- WEL-2932 Unable to build a chart based on Scored Form 
- WEL-2915 API: Add "Complete date" variable for assessments
- WEL-2993 Designer: Errors on creating a filter
- WEL-2888 Designer: new permission to see unrecognized communications


## Admin
- WEL-2883 Admin -> Users -> View a user -> User Information block -> The fields Username, Email, Phone number are duplicated
- WEL-2882 Admin: can't assign admin/auditSecurity accessess when invite User on copy
- WEL-2874 UI -> Admin -> API clients -> View a client -> the datatime \+ user should be on the same card where instance access is
- WEL-2482 Unable to clone users in Admin when adding new user
- WEL-2841 On set password page need add hint rules for password
- WEL-2810 User attributes: Request to add custom user attributes



# Release notes - Version 2021.7.10

### Date: July 22, 2021

## New Features Callout
Enable configuration in designer to hide and show read-only questions on assessments in Care
- WEL-2758 
- WEL-2780 

Ability to create HTML templates in Designer and render in Care, allowing 
to send html styled emails to patients and support read only fields in html mode
- WEL-2735 
- WEL-2558 
- WEL-2715

Enable seemless integration for eRX with DrFirst
- WEL-2458 

Add new widget to Insights Communications to support Unrecognized Phone calls
- WEL-2720 

Ability to send notifications to Welkin users via SMS and Email
- WEL-2645 
- WEL-2732

Extending Automation to support trigger based of different conditions
Enabling Automation to trigger of Encounters create/open/finalized
- WEL-2774 
- WEL-2635 
- WEL-2687

Menu search in Designer
- WEL-2827 

Better UI in Admin to support different configurations and phone calls
- WEL-2629 
- WEL-2571 

## Everything Else
## Care
- WEL-2781 Calendar: When changing the event date, can't see whole calendar
- WEL-2854 Care -> Assessments: Direct links to assessments don't always work
- WEL-2689 Terminate a running call to care team member if patient hangs up
- WEL-2737 \[Care -> Home page\] Users cannot remove emails from "New & Unread Communications" section of home page
- WEL-2699 Care: Home Page shows Loading... only if no In Progress Encounters are found
- WEL-2849 Lorem Ipsum on production error page
- WEL-2740 Care: Document Info isn't shown
- WEL-2738 Care: Can't view attached PDFs in emails from clients/patients
- WEL-2724 Document can't be deleted if document type record wasn't created
- WEL-2712 Care: Encounters: Missing encounters. With Care team on/off doesn't display user's encounters where user is not on care team
- WEL-2709 Notification: Phase change is not visualizing a notification
- WEL-2696 Bug: Encounters, open encounter in user perspective
- WEL-2695 Care: Fix secondary diagnosis display on Encounter Reports
- WEL-2686 Care: Fix Calendar multiple user sidebar search to return queried users
- WEL-2685 DOB is off by 1 day if it's after 2/29 in a leap year
- WEL-2680 Care: Create and Save button enabled even though mandatory fields are blank
- WEL-2679 Care: Field validation shows error but still allows user to save
- WEL-2644 Data is mysteriously hidden if it's not included in the UI component's view form
- WEL-2681 Care: Required questions in assessments are not noted
- WEL-2678 Care: Open Calendar day from encounter

## Designer
- WEL-2751 Unable to trigger multiple automations from the same trigger
- WEL-2733 Designer: add user notification configuration tab
- WEL-2700 Designer: Change summary. Sidebar changes indicator
- WEL-2745 Designer: unable to add phase
- WEL-2584 Designer: Long names make the goal template unmanageable
- WEL-2736 Designer: Messaging templates disable SMS and chat if template is html.

## Admin
- WEL-2806 Admin: fix Security UI issues
- WEL-2884 Unknown error when update instance phones
- WEL-2832 Admin: Release notes icon is using the wrong URL
- WEL-2819 Admin: eRx 'enable button' enabled for all instances
- WEL-2792 Admin: Data Audit doesn't include care team or primary team contact changes
- WEL-2667 Admin: Security Audit: Turning MFA on/off does not register in the audit trail

# Release notes - Version 2021.6.6.2

### Date: July 1, 2021

## Care

- WEL-2607 Automation fails send SMS and email with error User doesn't exist
- WEL-2539 Care: Encounters show the encounter owner instead of Care Team member
- WEL-2512 \[Care -> Communication Center\] -> If any communication options is turned off in the Admin side then disable buttons like "New Email", "New SMS" etc in the Care side
- WEL-2603 API: Implement Insights Permission model
- WEL-2574 Care: Encounters - Disposition details can be unique per template
- WEL-2557 Care: consolidate messaging template with search by lables
- WEL-2650 Emails are not sent with attachments
- WEL-2636 Home Screen: In Progress encounters are not showing the correct data
- WEL-2627 Emails incorrectly categorized as unrecognized - relax restriction for email sensitivity upper/lower case
- WEL-1969 Care: Insight icon replacement
- WEL-2479 Care: Add Insight button if user has permissions - based of security policy
- WEL-2478 Care: Add no permission screen for Insights - new screen will appear when navigation is made to url

## Designer

- WEL-2605 Designer: Creating new draft automatically marks some objects as changed
- WEL-2575 Designer: Encounters - Disposition details can be unique per template
- WEL-2561 Designer: automation postpone action
- WEL-2550 Designer: configure template for the external communication
- WEL-2462 Designer: Implement Insights Permission model - new model enabled care portal to have the right access to the right users
- WEL-2604 Designer: Automation trigger: Encounter Disposition

## Admin

- WEL-2567 When a role for user is selected, the first role should be primary, if nothing is selected
- WEL-2552 Admin: Security UI redesign - introduce a new section Security with enabled configuration for SSO and MFA and password strength
- WEL-2581 Admin: postponed automation action viewer (in admin, find all future task, and optionally delete some/all)


## General:
Welkin released SSO and MFA support. SSO supported providers are Okta, Auth0, Azure and Google. MFA supported method is SMS.
Navigate to Admin->Security section for further instructions.


# Release notes - Version 2021.6.5.2

### Date: June 25, 2021

## Care

- WEL-2586 Can't edit required disposition fields - Allows customers to use disposition in dataviews, regardless of required or not required fields
- WEL-2522 Cannot create instant encounter: Insufficient priviledges for calendar
- WEL-2564 Care: Relation therapy, add create/edit drawer - Transitioned Modal window to a standard drawer
- WEL-2521 Assignment of duplicate SMS to a patient does not work
- WEL-2480 Care: Layout title changes are reflected in the navigation but not in Layout header - Layout name is not reflected on layout header
- WEL-2402 Care: If there is no action on the tab for a long time, a socket connection error occurs.
- WEL-2297 Home Screen: Calendar event should take me to the encounter on the patient's profile - Calendar events widget allows one to navigate to either calendar event or to the encounter associated with it (based on care team membership)
- WEL-2524 UX Calendar event colors on the home screen are hard to read with the black font
- WEL-2486 Care: Marital Status drop down to Patient Profile - new optional field is introduced, to track marital status
- WEL-2471 Care: Percent Field Type - field type percent will have a percent sign next to a number
- WEL-2439 Encounter: Download CSV should download all records and not only what is on the page - allows one to download all encounters as one CSV file, no pagination is needed
- WEL-2154 Care: If help page is not set - show a standard image for not configured

## Designer

- WEL-2515 Designer: trigger automation on create user, assign access to instance, role, permissions - new automation setup, allows webhook notifications on user changes
- WEL-2492 Designer: Automation action: send SMS / email now
- WEL-2556 Designer: message template labels - allows tagging messages with labels. Would be utilized for better organization and search in the care portal
- WEL-2513 Designer: add pfa variable field in message template - part of the work to unify PFA and Regular templates into one
- WEL-2485 Designer, Care: Unify PFA and Templates - unification of PFA and Message template into one solution. Will trigger UX changes on Comm Center
- WEL-2532 Disable button 'Single Record' when we create Document Type
- WEL-584 Designer: Percent Field Type \(special case of float\)

## Admin

- WEL-2569 Admin: User Field: "Acuity Scheduling Id" is validating as UUID \(and it shouldnt\)
- WEL-2464 Admin: Integration: Comm center does not show phone numbers
- WEL-2516 Admin: Auth Configurations - add ability to remove config (allows one to delete 2FA and SSO config)

## System
- WEL-2553 API: at least one authentication should be on.


# Release notes - Version 2021.6.4.2

### Date: June 18, 2021

## Care

### Calendar
- WEL-2415 Calendar: Day view and Week view show different events for the same day
- WEL-2379 Calendar: Improve Calendar event readability when more than one event present at the same time
- WEL-2338 Calendar: Improve UI for More than one event at the time at the same day
- WEL-2329 Calendar: When creating a new event, end time is not set by default, hence throwing an error
- WEL-2171 Calendar: No easy way to remove other calendars, have to click one by one
- WEL-1659 Calendar: Multi-user view and actions


### Encounters
- WEL-2414 Care: Encounter page overflow
- WEL-2337 Encounters: Improve UI of Error Message in case assessment is not completed for encounter
- WEL-2292 Text box improperly displays text.  Breaks the word "tasks" into "t asks"
- WEL-2276 Encounters: Saving a comments causes error
- WEL-2316 Encounters: Cannot see completed assessment from encounters page
- WEL-2084 Encounters: Encounter should show who the encounter is with
- WEL-2083 Encounters: Usability improvements for labelling within encounters
- WEL-2080 Encounters: Ability to set default values in Data Views
- WEL-2453 Care: In the encounter report, added a hyperlink to take the user from a specific line in the report to the actual encounter
- WEL-2386 API: Calendar: Delete event from encounter when user delete it in the calendar
- WEL-2336 Care: Encounter: deleting calendar event in calendar, makes encounter disappear from UI
- WEL-1704 Encounters: Rename "Active" encounters to "Open"
- WEL-2324 Care: Encounter - broken assessment refrence - error case in discarded assessment use case
- WEL-2424 Care: Cannot Cancel Encounter without getting error message

### Comms Center
- WEL-2381 Comm Center: Inbound Unreconginzed SMS - Cannot assign SMS to a patient
- WEL-2363 UI: Check API call for resolving message templates
- WEL-2360 Care: Email Templates cannot be used, if the user has no Designer Access
- WEL-2347 Care: Email drafts improvements
- WEL-2327 API: Sms drafts
- WEL-2325 API: Automation: action send SMS
- WEL-2346 Care: Secure button on email draft is visible
- WEL-2301 Care: unrecognized calls / voicemail
- WEL-2417 UI: Sms drafts
- WEL-2456 PFA links have a 404 error
- WEL-221 Add scheduler for sending/receiving messages
- WEL-2483 Care: Email reply in conversation view is cut off
- WEL-2318 Welkonnect: Move call and voicemail recordings to S3 for secured storage
- WEL-2382 Care: Chat eventSubType notification comes back without patient information 
- WEL-2497 Care: Long email displays incorrectly, including emails with Attachments
- WEL-2461 Care: User cannot modify draft email



### Insights
- WEL-2330 Care: Task Distribution Report 
- WEL-2196 API: Task Distribution Report
- WEL-2197 Insights Permissions: Create Permission Model for insights - infra preparation
- WEL-2441 Encounters Report: Patient birthdate should be presented as Date, and not datetime
- WEL-2511 Encounters Report: Handle null calendar fields on encounters report
- WEL-2455 Encounters Report: Error blocks Encounters Insights from returning
- WEL-2443 Encounters Report: Regions and Territories are not added correctly
- WEL-2442 Encounters Report: Missing values from the User Profile
- WEL-2440 Encounters Report: Download encounters report as CSV with all records

### Home Page

- WEL-2048 eRx: Notification Counts: Care Portal Home Page Widget
- WEL-2045 eRx: Notifications in Home screen
- WEL-2245 Home Screen: Urgent/High Tasks Widget
- WEL-2202 Care: Homepage: Scheduled for today calendar does not show all the events
- WEL-2498 Care: Improve home page events colors

### Other Issues
- WEL-2279 Care: Read only text cannot be formatted
- WEL-2358 Care: Notifications: 5xx on digest api in PROD
- WEL-2357 Care: UX Errors in PROD - cannot read 'data' property of undefined
- WEL-2339 Care: Login screen for organization shows red error message
- WEL-2332 Care: Events Scheduled Widget
- WEL-2314 Care:API: Patient that is in a different region \(other than the user\) is not shown in UI but API still fetches relationship info
- WEL-2298 Wording on not configured data view should be more user friendly
- WEL-1940 Tasks: Values in columns are running off the page
- WEL-1876 Care Plan: Comments has a "Send" button, should be "Save"
- WEL-1839 Drop down lists: Can we have the list direction go up when you are at the bottom of a control
- WEL-1808 Document upload screen info lines run out of container
- WEL-2420 Care: Show help text in call drawer if no number is set
- WEL-2391 Care: Integrate with scheduler
- WEL-2384 Chat notifications are missing in live
- WEL-2380 Care: Implement Work Week View
- WEL-2335 Care: Add unread communications to Home Page
- WEL-2260 Assessments: When more than 6 scoring groups, we run into UI issues
- WEL-2187 Tasks: Show the user's primary role in the Assignee list for task and watcher assignment
- WEL-2023 Tasks: Clear filters
- WEL-1729 Tasks: Remove Completed/Cancelled Tasks to a different view/list
- WEL-2466 API: user unable to update and save email draft
- WEL-2287 Remove Document filters do not work in STG
- WEL-2296 Tasks: Sorting for Priority is not working as expected and intended
- WEL-2288 Remove Search bar has no functionality in the document center
- WEL-1905 Care: Display URL fields as hyperlinks in CDT objects
- WEL-2510 API: Triggered event should use direct reference URL with ID to find an object.
- WEL-2484 Automation: Improve Webhook Action
- WEL-2514 API: trigger automation on create user, assign access to instance, role, permissions
- WEL-2444 API: Calendar: Allow api client to fetch events that are cancelled
- WEL-1013 Designer: Allow lists CDT to be displayed as radio button or check box lists


We continue executing on 2FA and SSO, following items as preparation for rollout are released
- WEL-2350 API: SSO integration with Azure AD and Google
- WEL-2303 Fronted: SSO Auth Flow
- WEL-2217 API: SSO integration

## Designer

- WEL-2378 Designer: Dataview name is reseting after selecting datafield
- WEL-2359 Designer: Filter out unavailable instance and use new standard image for no access page
- WEL-2331 Designer: Fix space character to work as a delimiter in DataType/DataField/DataView components
- WEL-2368 Designer: Automation: action send SMS
- WEL-2348 Designer: Version History list page - Show list and audit of all who deployed the versions
- WEL-2308 Designer: Version History page \(json diff\) - Enable JSON diff of two versions
- WEL-2370 Designer: Change Summary list - allows one to see and inspect changes made to configurations
- WEL-1762 Designer: Show configured phone tree in read-only mode 
- WEL-1754 Designer: Renaming labels on the charts and graphs to improve usability
- WEL-1616 Error Message on accessing Designer - use standard no access image
- WEL-1586 Designer: Formatting for read only text area
- WEL-585 Designer: URL Field Type: add support for new field type URL across CDT
- WEL-1150 CDT variables in assessments for reference: Use CDT values as a pre-populated field values for assessments
- WEL-2494 Designer: Webhook payload config
- WEL-2474 Designer: Add unrecognized welkonnect security policy
- WEL-2352 Designer: automation: add trigger on patient create / update
- WEL-1614 Designer: Automation to be triggered from CDT Update
- WEL-1013 Designer: Allow lists CDT to be displayed as radio button or check box lists



## Admin

### API Clients 
API clients section went through User Interface changes to adopt look and feel of Users section. In addition,
the following issues were addressed:

- WEL-2410 Admin: API Client list - updated time does not change, requires page refresh
- WEL-2409 Admin: API Client page - adding more system fields to the user interface
- WEL-2408 Admin: API client - change the page title
- WEL-2407 Admin: Integrations Page: Rename Instances to Environments
- WEL-2365 Admin: First name and Last name are not populated after the invite
- WEL-2204 Admin: When editing a user, the spinner appears on the "Reset Password" button
- WEL-2413 Admin: API Client page - enable editing of Description field
- WEL-2362 Admin: Data Audit changes: cosmetic changes to look and feel
- WEL-2361 Admin: Security Audit changes: cosmetic changes to look and feel
- WEL-2341 Admin: Add a refresh button to Data Audit/Security Audit
- WEL-2319 User Invite/Login: Update wording in Welcome email

In addition, several other features/bug fixes were completed
- WEL-2383 Admin: Cannot create API Client - Reported by some customers in production, as inability to create api clients
- WEL-2431 Admin: Add default communication configs - allows one to add a default configuration settings
- WEL-2416 Admin: Data Audit - filter by patientID - enables one to filter data audit stream by patientID
- WEL-1342 Admin: Add release notes page
- WEL-1797 Admin: Text on Delete Instance
- WEL-2450 Add phone tree result to audit
- WEL-2433 Admin: add custom user attributes
- WEL-2429 Admin: add checkbox on api client for read user atribute

We continue executing on 2FA and SSO, following items as preparation for rollout are released
- WEL-2369 Admin: Auth SSO settings
- WEL-2367 Admin: Auth MFA settings

