# retool-data-dictionary-documentation-assets
Documentation assets for the Retool front end to the National Education Data Dictionary

## Landing Page
### National Education Data Dictionary
#### Background
The **online data dictionary service for Australian education data** is a prototype, jointly funded through the State, Territory and Federal Departments for Education as part of the National Schools Interoperability Program (NSIP), a business unit of Education Services Australia (ESA). The national data dictionary is intended to make it easier to mobilise data between different agencies and vendors. The data dictionary will:

* make data collection more efficient for schools and vendors
* coordinate the enterprise data modelling efforts of different school authorities
* help agencies to plan data collection activities more effectively.

The data dictionary captures the **definitions** of entities that occur across different national data collections, how the entities are **related** to each other (superclass/subclass, object/attribute), and how the entities are represented in different **data standards**. While the entity definitions reflect a broad, national consensus, the data dictionary also tracks differences in understanding about entities in different **school authorities** and different **data collections**, which have long been a concern for data mobility in the sector. The data dictionary definition of entities links to different contexts that they appear in, including different data collections, and to the different definitions and **business rules** applied in those contexts. It also links to the range of state and federal **legislation** determining how the entities are understood in different jurisdictions.

For example,
* The data dictionary defines School as an entity, and provides information about it (such as the overall definition, and the level of sensitivity that various jurisdictions apply to it in privacy compliance.)
* It further provides the relation of School as an entity to subclass and superclass entities (Organisation, Campus), and to attributes (ACARA ID, School Name, School Level).
* The dictionary entity links to various pieces of legislation, at a state and federal level, determining how schools are understood in different jurisdictions.
* It links to different data standards that represent schools, and the definitions they give.
* It also links to several data collections which gather information about schools, so that the varying definitions and business rules applying to them can be looked up in one place.

#### How to Use the App
 * **Entities Page** — Browse and explore all entities (objects and attributes).
 * **Collections Page** — Browse and explore collections and the entities they contain.
 * **Navigation** — Use double-click to follow links between related entities and collections.
 * **Junction Modal** — Pop-up when navigating between entities and collections. View collection-specific definitions, business rules, and value restrictions for entities.

#### Entity Hierarchy
Elements and Objects are organised hierarchically in the Data Dictionary; for example:
  * Organisation > School > Campus (objects)
  * Person > Staff, Student (objects)
  * Identifier > Organisation Identifier > School Identifier (abstract elements)

The Entity hierarchy can be navigated through the Linked Tables section of the Entity page. In this section there are two tables Superclass and Subclass which list the selected entities Parents and Children respectively. Users can navigate to view these entities by double clicking the row.

#### Key Features
 * Browse national-level data definitions.
 * Compare how entities are used across collections.
 * Navigate relationships between objects, attributes, and collections.=
 * Access collection-specific metadata via the Junction Modal.
 * Support privacy compliance by flagging sensitive elements.

#### Business Motivation
A PDF with more information about the business case for the data dictionary, and what problems it is seeking to solve, can be viewed by clicking the download icon.

#### Footer
The footer contains five buttons: “Go To Technical Info,” “Go To Entities,” “Go To Collections,” “Go To Submissions,” and “Download JSON.”
Clicking any of the first four buttons navigates the user to the corresponding page.
Selecting “Download JSON” downloads a ZIP file containing twelve individual JSON files — one for each table in the database — providing a complete export of all data.

Underneath an Acknowledgment of Country is displayed, along with links to the [Copyright](https://creativecommons.org/publicdomain/zero/1.0/) and [Privacy](https://www.esa.edu.au/privacy) policies

#### View
<img width="1917" height="873" alt="image" src="https://github.com/user-attachments/assets/8b1aec09-e56d-453e-a0f3-98fda125ba50" />

## Technical Information Page
### Technical Info
#### Modelling
The data dictionary uses a hierarchical model of *entities* belonging to *collections*, where entities are *objects* with *attributes*. For example:
 
* _School_ is an object, with attributes such as _ACARA ID_ and _School name_
* _School_ is captured in several collections, such as the _National School Census_ and _NAPLAN Registration_.


The Entity and Collection list panel is located at the left side of their respective dictionary pages, as the basic distinction that the data dictionary makes. 

The information model behind entities is derived from [ISO 11179](https://en.wikipedia.org/wiki/ISO/IEC_11179), which is widely used in data dictionaries (such as [Aristotle](https://aristotlemetadata.com/)). The ISO 11179 model ([source](https://www.sciencedirect.com/science/article/pii/S1532046412001827)) defines the following elements:

 * **object_class**: set of ideas, abstractions or things in the real world that are identified with explicit boundaries and meaning and whose properties and behavior follow the same rules,
 * **characteristic**: abstraction of a property of an object or of a set of objects,
 * **data_element_concept**: concept that can be expressed in the form of a data element, described independently of any particular representation,
 * **data_element**: unit of data that is considered in context to be indivisible,
 * **conceptual_domain**: concept that expresses its valid instance meanings or description.

![Diagram](https://ars.els-cdn.com/content/image/1-s2.0-S1532046412001827-gr1.jpg)

A data dictionary track attributes of objects: data element concepts. So it needs a notion of objects (_schools, students, staff_), a notion of properties (_name, gender, identifier_), and a notion of a property specific to an object (_school name, student gender, staff identifier_).

In the language used in this data dictionary,

* **Elements** (ISO 11179: _Data element concepts_) are attributes of **Objects** (ISO 11179: _Object classes_)
* **Elements** are concrete instances of **Abstract Elements** (ISO 11179: _Characteristics_)

For the entity list only, there is an additional filter with four selections (**all**/**abstract**/**element**/**object**) for its content, based on the entity's metadata type. The **all** selection means no filter for the entity list.

There are three components of the ISO 11179 model that the data dictionary captures only in descriptive text, but not in navigation as distinct entities:

* Data dictionaries track how a Data element component is represented in a data standard (_Data element_). That includes for example the SIF-AU representation of School as the `SchoolInfo` object. The data dictionary tracks this information in its representation of data standards, and its discussion of data collections.
* Data dictionaries track the possible values of a Data element (_Value domain_), and the conceptual foundation for those possible values (_Conceptual domain_). So the conceptual domain for gender includes  Male, Female, Non-Binary, Intersex; the value domain for a specific data element, how values are coded, could be "1", "2", "3", "4", or "M", "F", "Other", or indeed the strings "Male", "Female", "Non-Binary", "Intersex". The conceptual domain for school identifiers is strings; the value domain for ACARA IDs is five-digit numbers.
  * Because the data dictionary is meant to range across multiple data representations, it does not cover value domains, and it gives only high-level description of value domains, particularly as they relate to collections.

The data dictionary adds a further layer of hierarchical modelling:

* Entities can be subclasses of other entities; e.g. _Student_ is a subclass of _Person_, _Campus_ is a subclass of _School_, _Student Name_ is a subclass of _Name_
* Subclasses inherit the attributes of their superclasses; e.g. if _Person_ has the attribute _Person Address_, and _Staff_ is a subclass of _Person_, then _Staff_ also has the attribute _Person Address_. These inherited attributes are shown separately in the data dictionary 
* Subclasses can override inherited attributes; e.g. _Organization_ has a default _Organization Identifier_, but _School_ has _ACARA ID_, which overrides _Organization Identifier_

The following illustrates the overall conceptual model of the data dictionary, with subclasses, related entities, and collections:

<img width="800" height="650" alt="image" src="https://github.com/user-attachments/assets/1cc9526c-c2d4-4663-8d30-90d813bffffc" />

#### Footer
The footer includes three buttons: Go To Home Page, Go To Entities Page, and Go To Collections Page, which navigate the user to their respective pages.

#### View
<img width="1917" height="873" alt="image" src="https://github.com/user-attachments/assets/bd8e30ca-f7e7-454d-bd62-6e2632398a49" />

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

## Submissions Page
### Submissions
Use this page to propose new data definitions or updates to existing ones in the National Education Data Dictionary. You can submit either a new Entity or a new Collection using the Excel templates below. Download the template you need, complete it, and email it to nick.nicholas@nsip.edu.au

#### How It Works
1. Download the relevant template
2. Complete the fields (follow the notes on each tab)
3. Save your file
4. Email it to nick.nicholas@nsip.edu.au
5. Once submitted, your proposal will be reviewed by the NSIP team. You’ll be contacted if any clarification is required.

#### Templates
* **Collections Submission (Excel)** – propose a new collection.
  * Includes: definition, URLs, linked entities.
* **Entity Submission (Excel)** – propose a new entity.
  * Includes: definitions, standards (SIF/other), legal definitions, sensitivity, relationships, linked collections.
  * One entity per workbook.

#### Notes
* Leave sections blank if they don’t apply.
* Don’t rename tabs or change the structure.
* Accepted format: .xlsx
* Submissions are reviewed before being added to the data dictionary.

#### Questions
Email nick.nicholas@nsip.edu.au

#### Download Forms
This section includes two icon text boxes that allow users to download the submission templates. Selecting an icon downloads either the New Entity Form or the New Collection Form.

#### Footer
The footer has one: Go To Home Page, which navigates the user to the home pages.

#### View
<img width="1912" height="868" alt="image" src="https://github.com/user-attachments/assets/f3567904-5b04-420b-8b6c-0b27f83171f5" />
