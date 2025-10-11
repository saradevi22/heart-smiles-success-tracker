**Technical Description** 

Project Proposal   

I’m developing an app to allow a nonprofit, HeartSmiles, to track youth participation and history in their programs. The goal is for them to keep a database of all their participants across their programs, and then for administrators at the University of Maryland – who are interested in seeing the impact of their programs – to view that data. HeartSmiles staff should be able to export participant data in the form of a .CSV in order to upload to Qualtrics, University of Maryland’s data collection platform. Also, HeartSmiles already has data in the form of Excel and .CSV files, so the app should be able to convert these Excel files into new participant profiles and determine which programs these participants are in. 

Proposed Technical Stack 

* Firebase & Node: Let me know if this is not best for backend development. Firebase aims to store all participant and program data, as well as store logins and authentication for staff (HeartSmiles Staff, University of Maryland Staff)   
* Vercel: Both the backend and frontend will be deployed on Vercel (in different deployments of course).   
* Up to you: Some software package that allows HeartSmiles staff to export the program participant data in a .CSV file (excluding images).   
* Up to you: Some software package that allows HeartSmiles staff to import program participant data as an Excel or .CSV file, and uses ChatGPT 4.1 to extract that data into the app database and display it on the UI.   
* React: The frontend will all be in React. The app has been created using npx create-react-app to begin with. 

Data Models 

* HeartSmiles Staff Model:   
  * Username (String)  
  * Name (String)  
  * Phone\_Number (String)  
  * Email (String)   
  * Profile\_Picture\_URL (String)   
* University of Maryland Staff Model:   
  * Username (String)  
  * Name (String)  
  * Phone\_Number (String)  
  * Email (String)   
  * Profile\_Picture\_URL (String)   
* Participant Model:   
  * Name (String)   
  * Date\_of\_Birth (String)   
  * Address (String)   
  * Referral\_Date (String)   
  * Programs \[\]  
  * School (String)  
  * Identification\_Number (String)  
  * Headshot\_Picture\_URL (String)   
  * Uploaded\_Photos \[\]  
  * Notes \[\]  
* Program Model:   
  * Name (String)   
  * Description (String)   
  * Participants \[\] 


  
Backend Development Steps

1) Set up the file directory and all necessary introductory files for the project. Install any necessary components.   
2) Create and define different file models   
3) Build out authentication/login framework that would allow HeartSmiles Staff and University of Maryland Staff to login. Authentication should rely on email.   
4) Build the controllers and routes needed to add and remove each of our models. Then, create routes to query the lists of them.   
5) Build out the framework and middleware necessary for adding participant names to programs, and programs that a participant is enrolled in to their page.   
6) Build out framework and middleware necessary for uploading pictures to Cloudinary and then receiving back the link.   
7) Build out the framework and middleware necessary for exporting participant and program model data into a .CSV file, as well as importing .CSV and Excel files and converting those into participant models. 

Frontend Development Steps 

1) Create a file directory with images, components, data and pages. Create a global API variable that is set and can be edited for where the server is hosted.   
2) Develop a landing page with a header that says “HeartSmiles Youth Success App” and text that briefly explains what this project is. I should be able to edit this text afterward (tell me how) and also give you images to include here (tell me how).   
3) From the landing page, have a link to a sign-up/log-in page. This page should follow the authentication guidelines laid out above.   
4) Develop a dashboard that allows HeartSmiles Staff to view a directory of all participants (one tab) and a directory of programs (a second tab). There should also be a tab that says “ADD NEW PARTICIPANT” (goes to a new page) where HeartSmiles Staff can create a new participant and enter the data required for the participant model. There should be another tab that says "ADD NEW PROGRAM” where HeartSmiles Staff can create a new program and enter the data required for the program model. There should be another tab for HeartSmiles Staff that says “IMPORT DATA,” that allows them to import participant and program data stored in  a .CSV or Excel file (though this would exclude images). If the viewer is a UMD Staff, they should be able to view the directory of all participants and the directory of programs, but the “ADD NEW PARTICIPANT” and “ADD NEW PARTICIPANT” Finally, for both HeartSmiles Staff and UMD Staff, there should be a tab that says “EXPORT DATA,” that allows them to export all the participant and program data into a CSV file (excluding images) that could then be submitted to Qualtrics. 

Special Considerations 

1) The UI should be as clean and modern as possible, considering that the audience are using this app as a way of entering and keeping track of data.   
2) The frontend should feel responsive and provide microfeedback.   
3) The web-app will primarily be used on a laptop or tablet, so should fit a variety of screen sizes. 

API Keys and Configuration 

1) Let me know what keys I would need, depending on what software you tell me to install. 

KEY PRINCIPLES

* User-friendly and intuitive interface for staff and participants  
* Desktop optimized (with mobile accessibility as a future goal)  
* Tracks participant history, milestones, sessions, and connections  
* Filtering by program, location, age, graduation status, etc.  
* Expandable for new programs, locations, or participant types  
* Privacy, security, auditability, and exportability  
* Compatible exports for UMD/Qualtrics  
* Supports photo and document uploads (potential Google Drive storage)

USER ROLES

* Staff/Administrators: Add/edit/view/export/annotate/filter/manage profiles and events  
* Participants/Young People: View own profile, timeline, uploads, notes, history  
* (Optional) Probation Officer/UMD Reviewer: Read-only access for complete participant histories

MAIN APP SECTIONS AND PAGES

* LOGIN / DASHBOARD  
  * Secure login for different user roles (staff/admin, participant, UMD/reviewer)  
  * Welcome message, navigation links (Add New, Recent Activity, Upcoming Sessions)  
  * Notifications for staff (pending referrals, missed sessions, new notes, reports due)  
* PARTICIPANT DIRECTORY  
  * List or card view of all participants, profile photo, name, key details  
  * Filters by age group, county/location, program, graduation status, referral status  
  * Search by name, school, program, case number, or probation officer  
  * Export filtered or full participant lists (.CSV, under Export Tools)  
  * Map view option – pins show participants by home or program site  
* ADD NEW ENROLLEE  
  * Entry form for new participants:  
    * Profile photo upload  
    * Name, age, birthday, school, address, county, contact info  
    * Referral date and source (court, probation officer, program), case number  
    * Probation officer info, assigned program  
    * Private internal notes  
  * Saves automatically to participant directory and timeline as "Referral Added"  
* ADD NEW PROGRAM  
  * Entry form that asks for name and description, able to add certain participants to it and it updates on their page   
* PARTICIPANT PROFILE PAGE  
  * Header: Profile photo, name, age, school, status (active/inactive/graduated)  
  * Referral and probation info: date, source, assigned staff, mandates  
  * Timeline of milestones (events, connections, sessions, notes)  
  * Attendance record  
  * Volunteer/community service activity log  
  * Job application/activity log  
  * Outcome and growth notes (staff observations, achievements)  
  * Graduation date and alumni status  
  * Uploaded photos, certificates, and documents  
* TIMELINE FEATURE (secondary for now)   
  * Chronologically ordered events:  
    * Referral activity/pickup  
    * Contacts (participant, probation officer)  
    * Session attendance and details (topic, outcome, notes)  
    * Volunteer work — date, organization, hours  
    * Job application — date, employer, status  
    * Graduation  
    * Staff notes, photos, documents  
* SESSION AND EVENT TRACKING  
  * Track each session: date, type (workshop, group, 1-on-1)  
  * Name/topic, attendance, result/impact, growth notes  
  * Filter by program or session type  
* NOTES AND OUTCOME TRACKING  
  * Structured and free-form notes after events  
  * Staff record growth, challenges, milestones  
  * Custom data: job applications, awards, skill development  
* VOLUNTEER, JOB, AND COMMUNITY SERVICE TRACKING  
  * Record dates, organizations, hours, supervisor contact, role  
  * Can export for program stats and reporting – numbers oriented   
* UPLOADS AND MEDIA  
  * Profile photos  
  * Event/session/activity documents or images  
  * Secure, permissioned access  
* FILTERS, MAP, AND EXPORT TOOLS  
  * Filter by program, county, location, age, status  
  * Map view: participants shown by geography  
  * Filter and download by date range, program, location, graduation, etc.  
  * Export .CSV file for Qualtrics upload and UMD reporting  
* PROGRAM MANAGER SECTION  
  * Add/edit programs (name, description)  
  * Assign staff to programs, view stats, customize session types  
* ADMIN SETTINGS  
  * Manage user accounts and roles  
  * Set permissions for adding, editing, viewing, exporting  
  * Manage lists of programs and locations  
  * Set Google Drive/Qualtrics export integration

ADDITIONAL FEATURES AND EXPANSION

* Add new programs, counties, and users easily  
* Alumni dashboard for post-graduation engagement  
* Profiles are continuously updated—not locked after initial entry  
* In-app help and user guides

