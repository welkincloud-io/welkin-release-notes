# Release notes - Version 2021.6.4

### Date: June 17, 2021

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
- WEL-2441 Encounters: Patient birthdate should be presented as Date \(and not datetime\)


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



### Insights
- WEL-2330 Care: Task Distribution Report 
- WEL-2196 API: Task Distribution Report
- WEL-2197 Insights Permissions: Create Permission Model for insights - infra preparation

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

We continue executing on 2FA and SSO, following items as preparation for rollout are released
- WEL-2369 Admin: Auth SSO settings
- WEL-2367 Admin: Auth MFA settings

