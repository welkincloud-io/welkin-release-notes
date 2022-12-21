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

