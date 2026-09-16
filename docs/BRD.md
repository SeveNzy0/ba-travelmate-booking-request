
# **Business Requirements Document(BRD) Template**

## *Project/Initiative*

## *Month 20YY*

## *Version X.XX*

*Company Information*

1. # **Document Revisions**

| Date | Version Number | Document Changes |
| ----- | ----- | ----- |
| 05/02/20xx | 0.1 | Initial Draft |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |

2. # **Approvals**

| Role | Name | Title | Signature | Date |
| ----- | ----- | ----- | ----- | ----- |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |

3. # **Introduction**

   1. ## **Project Summary**

      1. ### **Objectives**

Increasing the number of search queries for hotel bookings by implementing a new filtering method in the system—from selecting a date and city to choosing a specific hotel from a list—from 45% to 70%, as well as adding more informative hotel descriptions; this will allow us to retain users who have difficulty finding a hotel using the search function

2. ### **Background**

TravelMate only uses a list of hotels without any filters, so users can't find a hotel that suits their specific needs.

* Implementation of a new hotel filtering system  
* Hotel Card Upgrade  
* system upgrade for real-time operation  
* Integrate APIs from other websites into the system

  1. #### ***Business Drivers***

*The development of this feature is driven by several business needs:*

* *The user interface will make it easier to search for hotels*  
* *Save users time*  
* *Provide additional filters based on user preferences*  
* *user-friendliness of additional hotel features*

2. ## **Project Scope**

   

   1. ### **In Scope Functionality**

- Added the “Price per Night” filter option  
- Added the “Free Booking” filter option  
- Updated hotel listing information  
- Implemented a feature in the system to suggest recommended options  
- Implemented new APIs in the system

  2. ### **Out of Scope Functionality**

- A calendar that clearly displays days off  
- The ability to specify children's ages  
- “Rating based on reviews” filter  
- Tracking click data from users who don't find a result

  3. ## **System Perspective**

*This feature will be implemented as part of the TravelMate hotel filter used by the platform’s users.*

*The system must interact with:*

*• The hotel database*

*• APIs*

*The goal is to help users find hotels faster, which will save them time and keep them on the TravelMate platform.*

*This feature allows users to filter hotels based on their own criteria, enabling more users to find a hotel that suits their needs.*

1. ### **Assumptions**

* Users should be able to clearly see the filter section from any device, and it should not be too large  
* Specific filters should be applied to each hotel to make them easier to find  
* The hotel card should display the main room  
* The hotel card should feature clear icons for specific features

  2. ### **Constraints**

* The feature must align with the existing TravelMate platform architecture  
* Filtering will only apply to hotels that have entered card and filter information for their property

  3. ### **Risks**

* Users may not understand certain filtering features  
* Users may filter incorrectly and complain about it  
* Users may misunderstand the icons on the hotel card.

  4. ### **Issues**

* For some users, the main rooms of a hotel may not be displayed on the hotel card  
* Hotels partnering with TravelMate need to add filters for their hotels themselves

4. # **Business Process Overview**

   *\[Describe how the current process(es) work, including the interactions between systems and various business units. Include visual process flow diagrams to further illustrate the processes the new product will replace or enhance.*

   *Use case documentation and accompanying activity or process flow diagrams can be used to create the description(s) of the proposed or “To-Be” processes.\]*

   1. ## **Current Business Process (As-Is)**

At any point during or after deployment of web apps or web sites (internal or external) to support business activities, development/support teams may create and deploy widgets. 

1. CMS / database administrators for the employee portal use the CMS tool to create widgets. They can test widgets in the designated staging environment, then register them and deploy to production.  
2. Development teams may deploy widgets to development and testing environments set up for their development projects. They must check widget code into and out of the source code repository according to their projects’ development schedule.  
   ![][image1]

   2. ## **Proposed Business Process (To-Be)**

1. Technical Lead searches repository   
2. If widget is not found, user creates a new widget name record.  
3. WINS validates that all fields have been completed.  
4. WINS confirms that no similar widgets exist  
5. User confirms record to be created.  
   ![][image1]  
1. User searches repository to locate existing widget description.  
2. WINS displays record  
3. User selects Edit to open and modify record  
4. WINS validates all fields completed correctly  
5. User confirms changes.  
6. WINS confirms changes and updates Audit table.

   ![][image1]

5. # **Stakeholder Requirements**

- *SR-001: User can apply filters regardless of their account’s login status*  
- *SR-002: Hotel owner must add up-to-date information about their hotels*  
- *SR-003: User must be able to review photos to verify that the hotel’s additional amenities are available*  
- *SR-004: Users can check whether a hotel is booked on other websites by integrating an API into the system*


The requirements in this document are prioritized as follows:

| Value | Rating | Description |
| ----- | ----- | ----- |
| 1 | Critical | Filter hotels by additional features (price, comfort, free cancellation, etc.) |
| 2 | High | Create detailed hotel profiles that display information and amenities for each hotel |
| 3 | Medium | The system should offer recommended options and guide the user toward a choice using marketing tags |
| 4 | Low | The system should retrieve data from other platforms via APIs and update it on TravelMate so that users don't accidentally book a hotel they've already booked. |
| 5 | Future | Hotel rate cards should include the price for the entire stay, not per night |

1. ## **Functional Requirements**

| Req\# | Priority | Description | Rationale | Use Case Reference | Impacted Stakeholders |
| ----- | :---: | ----- | ----- | ----- | ----- |
| **General / Base Functionality** |  |  |  |  |  |
| FR-G-001 | 1 | The system should filter hotels by the categories selected by the user | Proper filtering will not require the user to verify the accuracy |  | Users |
| FR-G-002 | 1 | The system should add tags to hotels such as “Air conditioning, free breakfast, parking” | Users will be able to choose what they need for their vacation more quickly |  | Users |
| FR-G-003 | 1 |  The system must interact with other services via APIs    | This will allow us to notify users that the hotel is booked if it has already been reserved on another platform |  | User |
| FR-G-004 | 1 | The system should search for hotels based on specific metrics that would be recommended for a guest's stay and list them as the top priority. | The system will help businesses attract more customers using marketing tags |  | Business |
| FR-G-005 | 2 | The system should retrieve the user's geolocation and change the interface language based on the user's location. | It will help users search for hotels more easily using an interface in their native language |  | User |
| **Security Requirements** |  |  |  |  |  |
| FR-S-001 | 1 | While on the website, users can decline to grant access to their geolocation | This feature will help ensure user safety, but if geolocation is confirmed, hotels will be searched for based on the user's current location |  | User |
| **Reporting Requirements** |  |  |  |  |  |
| FR-R-001 | 2 | The system should track which filters users use most often and log this information. | This feature will help us understand in the future what filtering priorities are needed for most users |  | Business |
| **Usability Requirements** |  |  |  |  |  |
| FR-U-001 | 1 | The system should include standard Apple or Android icons for filters and hotel listings | Users will be able to recognize the familiar icons more easily, and it won't cause any confusion |  | Users |
| **Audit Requirements** |  |  |  |  |  |
| FR-A-001 | 1 | Project administrators must verify that the features added by hotels contain accurate data. | This will prevent users from being confused |  | Admin |

   2. ## **Non-Functional Requirements**

   *\[Include technical and operational requirements that are not specific to a function. This typically includes requirements such as processing time, concurrent users, availability, etc.\]*

| ID | Requirement |
| ----- | ----- |
| NFR-001 | The system must update the filtering no later than 2 seconds |
| NFR-002 | The filtering interface should match the style of the project itself and be easy to use |
| NFR-003 | Hotel cards must contain accurate information |
| NFR-004 | When viewing a specific hotel, the listing should be more detailed and include information about the hotel's additional features, the dates for which the hotel can be booked, the price for that period, the rating, and a photo of the main room. |
| NFR-005 | The system must be able to handle 1,000 concurrent users on the website |

6. # **Appendices**

   1. ## **List of Acronyms**

   *\[If needed, create a list of acronyms used throughout the BRD document to aid in comprehension.\]*

   2. ## **Glossary of Terms**

   *\[If needed, identify and define any terms that may be unfamiliar to readers, including terms that are unique to the organization, the technology to be employed, or the standards in use.\]*

   3. ## **Related Documents**

   *\[Provide a list of documents or web pages, including links, which are referenced in the BRD.\]*

[image1]: <data:image/png;base64,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>