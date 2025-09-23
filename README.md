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
The footer contains two buttons "Go To Entities Page" and "Go To Collections Page", when clicked this navigates the user to the respective pages

#### View
<img width="1913" height="871" alt="image" src="https://github.com/user-attachments/assets/e9dff287-bf90-40a7-879f-928e067e43e4" />

## Entities Page
### Left Pane
#### Home Button
When clicked the user is navigated to the landing page

<img width="49" height="49" alt="image" src="https://github.com/user-attachments/assets/ce18cc3e-f2d3-4478-840b-b29e3163d984" />

#### Filtering
There is a filter with four selections(**all**/**abstract**/**element**/**object**) for its content, based on the entity's metadata type. The **all** selection means no filter for the entity list.

<img width="575" height="253" alt="Screenshot 2025-09-24 093201" src="https://github.com/user-attachments/assets/da35eab9-f08a-4f04-a521-7d8b65382d67" />

#### Entity Table
This table contains all of the entities and their types. The table is scrollable. When you click a row in the table the data for that entry is fetched and displayed in the right pane

<img width="564" height="754" alt="image" src="https://github.com/user-attachments/assets/0b3b1aff-b9dc-4bd5-8b8f-2a60ceb553d9" />



