# retool-data-dictionary-documentation-assets
Documentation assets for the Retool front end to the National Education Data Dictionary

## Landing Page
### National Education Data Dictionary
#### Background
The NSIP Team at ESA has developed a prototype online data dictionary service intended to make it easier to mobilise data between different agencies and vendors, in order to:

* make data collection more efficient for schools and vendors
* coordinate the enterprise data modelling efforts of different school authorities
* help agencies to plan data collection activities more effectively.

The definitions in the data dictionary will reflect a broad, national consensus, but individual standards and collections may involve different granularities or understandings of data, having been devised for different purposes. In order to reconcile the differences in definitions and usage between school authorities, the data dictionary definition will link to the different contexts that its elements turn up in, particularly in different data collections, and the different definitions and business rules applied in those contexts. For example, it should capture the different ways that authorities define schools and sub-school entities, as a caveat for people working across authorities.

The data dictionary can also be used to enable privacy compliance, by identifying sensitive data elements transacted between agencies, without restriction to a single data standard. Facilitating data privacy compliance is a downstream benefit of the data dictionary, and its use to that end will be piloted. However, privacy classifications of data are specific to agencies, and the data dictionary will not impose a single privacy classification over its
data definitions.

#### How to Use the App
 * **Entities Page** — Browse and explore all entities (objects and attributes).

 * **Collections Page** — Browse and explore collections and the entities they contain.

 * **Navigation** — Use double-click to follow links between related entities and collections.

 * **Junction Modal** — View collection-specific definitions, business rules, and values for linked items.

#### Key Features
 * Browse national-level data definitions.

 * Compare how entities are used across collections.

 * Navigate relationships between objects, attributes, and collections.

 * Access collection-specific metadata via the Junction Modal.

 * Support privacy compliance by flagging sensitive elements.

#### Footer
The footer contains three buttons "Go To Technical Info", "Go To Entities Page" and "Go To Collections Page", when clicked this navigates the user to the respective pages.

#### View
<img width="1911" height="871" alt="image" src="https://github.com/user-attachments/assets/bbf89b36-eec7-4c6b-97c5-45ee57fe34dd" />

## Technical Information Page
### Technical Info
#### Modelling
The Entity and Collection list panel is located at the left side of their respective dictionary pages. They can be filtered to separate all items based on their metadata type:
* **Elements** are attributes of **Objects**
* **Elements** are concrete instances of **Abstract Elements**
* Different **Elements** are collected in different Data **Collections**
  
In terms of ISO 11179 (used e.g. in Aristotle),
* Abstract Elements correspond to **Properties**
* Elements correspond to **Data Element Concepts**
* **Data Elements** are not currently modelled in the Data Dictionary:
the interface provides information on values, but it does not currently model data domains

#### Entity Hierarchy
Elements and Objects are organised hierarchically in the Data Dictionary; for example:
  * Organisation > School > Campus (objects)
  * Person > Staff, Student (objects)
  * Identifier > Organisation Identifier > School Identifier (abstract elements)

The Entity hierarchy can be navigated through the Linked Tables section of the Entity page. In this section there is two tables Superclass and Subclass which list the selected entities Parents and Children respectively. Users can navigate to view these entities by double clicking the row.

#### Footer
The footer contains three buttons "Go To Home Page", "Go To Entities Page" and "Go To Collections Page", when clicked this navigates the user to the respective pages

#### View
<img width="1915" height="866" alt="image" src="https://github.com/user-attachments/assets/109513ef-5f66-4317-8a95-082f0710af28" />

## Entities Page
### Left Pane
#### Home Button
Navigates the user back to the landing page.

<img width="49" height="49" alt="image" src="https://github.com/user-attachments/assets/ce18cc3e-f2d3-4478-840b-b29e3163d984" />

#### Filtering
There is a filter with four selections(**all**/**abstract**/**element**/**object**) for its content, based on the entity's metadata type. The **all** selection means no filter for the entity list.

<img width="575" height="253" alt="Screenshot 2025-09-24 093201" src="https://github.com/user-attachments/assets/da35eab9-f08a-4f04-a521-7d8b65382d67" />

#### Entity Table
This table lists all entities along with their types. It is scrollable, and selecting a row retrieves the corresponding data and displays it in the Right pane.

<img width="564" height="754" alt="image" src="https://github.com/user-attachments/assets/0b3b1aff-b9dc-4bd5-8b8f-2a60ceb553d9" />

### Right Pane
The Right Pane is divided into two views: the Details view (top) and the Links view (bottom).

#### Details
The Details view has five tabs:
 * Definition
 * SIF
 * Other Standards
 * Legal Definitions
 * Sensitivity
Upon selecting a tab the data related to that area displayed in the space under the tabs bar.

<img width="1328" height="49" alt="image" src="https://github.com/user-attachments/assets/5ef2752c-9292-4463-b4ef-e166be1254ab" />

##### Info Button
This button is displayed at the end of the tabs view and when seleced opens an info dialog explaining what each of the tabs means

// WILL NEED TO PUT THE TEXT HERE

#### Links
The Links view has six tabs:
 * Superclass
 * Subclass
 * Has Attribute
 * Is Attribute Of
 * Related
 * Linked Collections

Selecting a tab displays the corresponding data in the area below the tab bar.
 * For most tabs, this data consists of Entities linked to the Entity selected in the Left Pane.
 * For Linked Collections, the data consists of Collections instead of Entities.

Double-click behavior:
 * Entities → The Entities page resets with the linked Entity in the Left Pane, and the Right Pane updates with its values.
 * Linked Collections → A modal opens with details for the selected collection.

<img width="1330" height="92" alt="image" src="https://github.com/user-attachments/assets/d0665506-e50a-441e-9bb4-e99458fcfba6" />


##### Info Button
This button is displayed at the end of the tabs view and when seleced opens an info dialog explaining what each of the tabs means

// WILL NEED TO PUT THE TEXT HERE

### Junction Modal
The Junction Modal appears in two cases:
 * When a linked collection is selected on the Entities page.
 * When a linked entity is selected on the Collections page.

This modal displays all data related to the junction between those entities and collections. The information may include:
 * Description
 * Standard
 * Element Name
 * Commentary
 * Business Rules
 * Values
 * Definition Modification
 * Elements
If no data exists for a given section, that section is omitted.

Controls:
 * Close and Cancel — Return the user to the previous screen.
 * Progress — Opens the linked elements screen, showing the element in the Left Pane and its data in the Right Pane.

<img width="962" height="690" alt="image" src="https://github.com/user-attachments/assets/efd52693-c5a7-4a82-9028-16f833509ffa" />


## Collections Page
### Left Pane
#### Home Button
Navigates the user back to the landing page.

<img width="49" height="49" alt="image" src="https://github.com/user-attachments/assets/ce18cc3e-f2d3-4478-840b-b29e3163d984" />

#### Collections Table
This table lists all collections, It is scrollable, and selecting a row retrieves the corresponding data and displays it in the Right pane.

<img width="572" height="868" alt="image" src="https://github.com/user-attachments/assets/22cbee31-ff62-4345-97d7-6cba6d66ffae" />

### Right Pane
The Right Pane is divided into two views: the Details view (top) and the Links view (bottom).

#### Details
The Details view contains two sections:
 * Definition
 * URL
The relevant data for each section is displayed under its heading.

#### Links
Displays just one table thats lists all the entities connected to the selected Collection
Double clicking opens the Junction Modal
