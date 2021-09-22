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

