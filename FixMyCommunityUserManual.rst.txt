FixMyCommunity 

Administrator's Manual




  



While using your FixMyCommunity DemTools site can be very simple, administering a site and customizing it to your specific needs can sometimes be complicated. If you’ve decided to undertake this task on your own, here is the documentation to help you along the way.


  


This document seeks to address some of the most common needs for customizing and operating your FixMyCommunity site.






Table of Contents


Introduction
Getting Started
        Organizing your Data
        Installing the Software
        Customizing FixMyCommunity
                Assigning Reports to Bodies
                Integration of FixMyCommunity
                Defining Your Administrative Boundaries
Using FixMyCommunity
                Adding a Body
        Adding a Category
                Viewing and Editing Reports
                Survey Results
                Managing Users
                Stats
                Configuration
        Updating Your Installation
        Handling Abuse of FixMyCommunity
________________
1. Introduction


FixMyCommunity is a service delivery reporting tool launched as part of DemTools, NDI’s Democracy Toolkit. DemTools provides basic and easy-to-use solutions for common tech problems in the democracy and human rights space that are accessible to programs that lack funding for sophisticated software development. Of course, the right political and program factors still need to be in place, along with adequate funding for implementation and partner training. The FixMyCommunity platform was designed to enable citizens to report problems and send service requests quickly and simply to the proper authority and to enable an entity, such as a town council, political party, or citizen group, to gauge the demands on their services, report progress, and make their processes more transparent. With FixMyCommunity, you can:


* Report problems in the community, such as potholes or broken streetlamps
* Use photography to illustrate the scope of the problem
* Identify the exact location using a map interface and dropping a pin
* Send reports to the corresponding authority
* Create user accounts to make future reports more expeditiously
* Receive alerts for submitted reports via email or RSS feed based on a specified area
* View breakdowns of issues by category, status, and chronology
* Flag users for closer observation
* Block users by email address to prevent improper content submission
* Create bodies to represent entities administering local services
* Create categories to represent the responding organization
* Update statuses of reports to indicate progress made on issue
* Automatically send feedback surveys to users four weeks after initial report submission
* View survey feedback submitted by users
* Make the service provision process more transparent as submitted reports and their status are public by default
* View all reports in your community
* Limit the geographic scope of report submissions to accurately reflect your jurisdiction
* Create user accounts for internal staff to update report statuses
* Foster civic participation and trust as citizens can help solve community problems and see feedback publicly


FixMyCommunity is built from FixMyStreet, an award-winning tool created by UK-based mySociety, a charity organization that makes websites and tools that empower citizens
In the UK and around the world. FixMyCommunity is customizable and extensible, which makes the tool available for groups to use in variety of use cases in their community. The tool focuses giving citizens a method for raising issues with their governments and tracking their progress.
This user manual provides an overview of the FixMyCommunity application and instructions for 
institutions to manage their reporting infrastructure and database.
2. Getting Started


When beginning to work with FixMyCommunity, it’s important to think about your goals for using the tool and what outcomes you would like to see happen.. What sorts of public services or community problems do you want FixMyCommunity to address? Is improving citizen participation or the transparency of public service delivery important?  What is your geographic jurisdiction?


Answering these questions is essential for deploying and customizing FixMyCommunity so you can tailor the site’s functions and your communication around the tool and to meet your objectives and your community’s needs. Building clear metrics for your goals is key and will inform your customization, deployment, and communication regarding the platform. Identify the exact geography you want to cover and clearly define what your goal is for using FixMyCommunity (providing services, tracking faults, etc.), as well as those of subsidiary bodies (i.e., public works, sanitation, crime prevention). In order to maximize public satisfaction, this information must be explicitly defined and communicated.


2.1 Organizing your Data


Using FixMyCommunity to streamline service reporting is easy. The first step of building your site is understanding the basic terms and concepts of the platform. These terms will be explained in larger detail further in the manual, but here is an informative glimpse into the organizational structure.


* Bodies - Bodies are the authorities that receive the reports submitted by the public to FixMyCommunity. These can be government entities, private corporations, public works departments, or whomever is supposed to receive the information.
* Categories - These are subsets of bodies that specifically handle the issues and are typically labeled as what they address (i.e., “Potholes” or “Litter”). Email addresses are assigned to categories, creating the channel of communication, and are used with the area to identify the specific point of contact.
* Reports - These are the individual logs of problems submitted by the end users, the public. Once confirmed by the user, these are published to the public site, unless marked hidden by the administrator directly or via the category’s setup. Reports can contain a photograph and always contain a user’s name and email, which may remain unpublished at the user’s choice, but will still be received by FixMyCommunity.
* Surveys - After users submit reports, they’ll receive surveys requesting feedback four weeks after they submit a report. The surveys collect data on performance of the bodies, which will be summarized on the surveys page.
* Users - There are two kinds of users: public and internal. Public accounts are created whenever a user submits a report, are denoted by the given email address, and may have an associated password. Administrators may alter the details of public accounts. Internal accounts are assigned to the bodies and are created for their staff.


For a further description of each of these concepts, please see the corresponding sections of the 
FixMyStreet Administrator Manual.
2.2 Installing the Software


There are three options for installing the software to run FixMyCommunity: installing on your own server or have NDItech host it for you. NDItech can host your customed version of FixMyCommunity via a Docker image, which is a repository for your source code and makes installation and maintenance easier to manage. It is recommended to employ one developer and one administrator to prepare the site for deployment.
2.2. Customizing FixMyCommunity


There are five keys domains for customization with FixMyCommunity: the site’s configuration, design elements, language, behavior patterns, and information like the FAQ and privacy statement. To begin customizing, the most likely first step is establishing a cobrand, the mechanism that allows you to change FixMyCommunity from its default configurations. For simplicity’s sake, it is strongly recommended to maintain continuity between the name of your site and the cobrand’s directory name. NDItech can build your cobrand for you, if desired.


Some basic customization options of FixMyCommunity are below. Please note that none of these require knowledge or use of FixyMyCommunity’s programming language Perl, but do require the some systems administration expertise and code editing.


* how to translate or change FixMyStreet’s language
* how FixMyStreet assigns reports to bodies
* how to customise the geocoder
* how to change the design
* how to customise templates
* how reports are sent by FixMyStreet
* all the config settings


mySociety, the originators of this platform, suggest the following 13 steps for basic customization:
* Pick a name
* Register a domain name
* Translate into needed languages
* Install software on host server
* Lock access to the admin portal
* Change color scheme as desired
* Change logo as desired
* Write and post the FAQ, privacy statement, and about page
* Confine geocoder lookups to your area of coverage
* Configure the administrative boundaries for each body
* Configure non-default settings (email domain, example names, etc.)
* Create the bodies
* Add categories with email addresses


Further customization of your cobrand will require writing custom Perl code for your site.
2.2.1 Assigning reports to bodies


When a user places a pin on the map, FixMyCommunity will send the geocoded latitude and longitude of the pin to MapIt to identify the areas that contain the pin. FixMyCommunity will then identify the bodies attached to the geographic area that you’ve defined, as well as the corresponding categories and contacts. This process will require your FixMyCommunity platform to connect to MapIt to identify the correct administrative boundaries.
2.2.2 Integration of FixMyCommunity


Integrating your platform with your service delivery system’s database is highly recommended. While no integration will still allow the platform to send emails as normally, the experience and usability for staff notably improve with integration. The process is, of course, dependent on the nature of your local system and its cooperation with FixMyCommunity.


There are four levels of integration, with increasing levels of benefit for your administration of the platform.
        0. No integration (default) - reports are sent via email
        1. Reports are directly injected into the back end
        2. Status changes on the back end are published on FixMyCommunity
        3. Problems created on the back end are public on FixMyCommunity


More details on integration and its levels are available here.
2.2.3 Defining your administrative boundaries


To enable problem reporting, the geographic area you are covering for reports must be created in the site. . When reporting an issue, users provide an exact location which is mapped and allows FixMyCommunity to check the boundaries and determine the correct reporting body. FixMyCommunity uses MapIt to define the area and will determine the corresponding body and available categories for the report based on the given location.


If you’re sending reports to a local government department, the administrative boundary data may already exist thanks to OpenStreetMap, a company that collects geospatial data and makes it freely available. With OSM, simply identify the areas you need covered, tell FixMyCommunity to ignore the rest, and your information should populate. If your area doesn’t have OSM data 7available, you’ll need to create your own boundary data for the platform.


Every body you create must have an assigned area and you must submit the corresponding bodies to FixMyCommunity for the tool to function. With this complete, bodies can be assigned to the areas in their creation or editing with a simple drop-down selection.


By default, the administrative boundaries are not visible on the map, but this may be adjusted with some customization.
3. Using FixMyCommunity


Using and administering FixMyCommunity is a cinch. It is recommended that you use one administrator to operate the site, who’ll spend fifteen minutes to an hour per day on user support. 
3.1.1 Adding a body


Now, you must create the body that will receive the submitted reports. This can be a town council, a sanitation department, or even a contractor. Name the body appropriately, select a parent organization if it applies, select the area covered and send method, then add the body.
3.1.2 Adding a category


Categories provide the actual channel for the report to follow and are typically marked by the problem they address. They can be “Potholes” or “Graffiti” and must have an email address and note attached. The email address given will be the contact address for the responding authority and the note is for the admin’s use and convenience. Different categories may have the same email address. Note that these categories can be marked private, which means all reports submitted in this category will not be published to the site but will still be received by the site administrator.
3.1.3 Viewing and editing reports


From this screen, you can view all submitted reports, search for specific ones, and edit them accordingly. When editing a report, you can view all of the relevant information, including the location, submitter, and its status. The ticket can be edited for content, flagged for observation, set to private, which will remove it from public viewing, and have its status updated via a dropdown menu. Additionally, the user can be flagged or banned via this screen.


When editing a report, you’ll see that it has several statuses that you can select from to provide updates. There are four categories of reports (Open, Closed, Fixed, and Hidden), each with corresponding statuses. Below is an explanation of the individual statuses:




Open
* Open - the report has been submitted and published
* Investigating - the body acknowledges the problem and is investigating it
* Planned - the body has created a course of action for addressing the problem
* In progress - the problem is being actively resolved by the body
* Action scheduled - the body has determined a future time/date for resolving the problem
Closed
* Unable to fix - the problem cannot be resolved
* Not responsible - the body doesn’t bear responsibility for resolving the problem
* Duplicate - the report already exists in the system
* Closed - the report has been closed by the admin
* Internal referral - 
Fixed
* Fixed - the problem has been fixed
* Fixed - User - a citizen-user identified the problem as fixed
* Fixed - Council - the body has identified the problem as fixed
Hidden
* Hidden - the report has been hidden from public viewing
* Partial - the report submitted is incomplete
* Unconfirmed - the report has been submitted, but not confirmed
3.1.4 Survey results


On this screen, you can view the output from surveys sent to people submitting reports. Keep in mind these surveys are sent four weeks after the report’s initial submission. This information can be used for media or accountability purposes.
3.1.5 Managing users


User accounts are identified by their email addresses and names, but only the name is published on the site. Users not conforming to content standards may be flagged for closer observation and blocked by their email addresses if deemed necessary. Users can only mark reports as fixed.


Some bodies will want to assign their own staff to facilitate their use of FixMyCommunity. The site administrator can do this my searching for the user by name and email address and assigning them to the body. Staff users can hide abusive reports, for body-specific summary statistics, and edit the status of reports to more than fixed or open, such as investigating or in progress.
3.1.6 Stats


This page enables the administrator to view a compilation of the reports by status and the body to which they were submitted, all within a specified date range.


3.1.7 Configuration


The configuration page shows you the live configuration feeding your site. Here, you’ll find information about your cobrand and particular settings that affect your site and its functionality. For more information on this page, click here.
3.2 Updating your installation


Keeping your installation current means you’ll get new features and bug fixes created by other users of FixMyCommunity. Here’s some information on feeding back your changes for other users of FixMyCommunity. To view directions on updating your code, please view this page.
3.3 Handling abuse of FixMyCommunity


There are three primary forms of reports that abuse the platform: obscene/illegal, spam, and nonsense. The best method for handling the abuse should be established during the platform’s development and subsequently published to maintain consistency and develop legitimacy with the community you’re serving. Please be sure to check the content liability laws in your community to identify the best practice for moderating the content of your website.