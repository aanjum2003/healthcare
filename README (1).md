
# MIST 4610 Group Project 1

## Team Name
39217 Group 7
## Team Members
Dylan McMorrow [paste link to Github Repository here]
Aafreen Anjum [paste link to Github Repository here]
Jack Drummond [paste link to Github Repository here]
Ishi Gupta [paste link to Github Repository here]
Miral Lakhani [paste link to Github Repository here]

## Problem Description
Our primary goal is to create a relational database that significantly improves the efficiency and quality of a medical center's operations. The central entity in our database model is the "Visit Entity," representing each medical patient's visit. This "Visit Entity" is intricately linked with other key components, including the "Patient," "Visit Record," "Physician," "Room," and "Billing" entities. Our focus is on accurately modeling these relationships, generating realistic sample data, and populating these entities with relevant attributes.

Moreover, we aim to implement fully functional query capabilities on this data. These queries will not only facilitate day-to-day operations but also yield valuable business insights into the medical center's functioning. This enhanced database will provide us with a comprehensive and detailed view of patient visits, medical records, physician-patient interactions, room allocation, and billing processes. By effectively leveraging this database, we can drive informed decision-making, streamline operations, and ultimately enhance the overall performance and quality of care within the medical center.

We have attached screenshots from the initial conversation with our client. As evident in our data model below, we adjusted some of the entities originally proposed by our client to better suit their needs and boost efficiency.

<img width="646" alt="Screen Shot 2023-11-03 at 5 57 14 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/b9fde6b8-4890-4da1-b16f-d67d68aafb53">
<img width="696" alt="Screen Shot 2023-11-03 at 5 57 25 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/8e59306e-cc6d-4ff8-a405-7b01c92d45ef">

## Data Model Explanation
Our model is designed to represent the structure of a small to medium sized emergency healthcare clinic. The Patient entity stores information about all patients who come to the clinic to seek medical care, such as their name, contact information, and any relevant allergies to medications. Each patient will have one or more emergency contacts listed, which is represented by the 1 to many relationship between the Patient and Contact entities. The Contact table stores information about each emergency contact such as their name, address, phone number, email, and the relationship to the patient (e.g. mother, aunt, etc.).

We then have the Visit entity, which is central to the entire model. The Visit table is updated each time a patient comes to the front desk and fills out paperwork, regardless if any tests were performed. Each patient can have as many visits as needed, which is represented by the 1 to many relationship between the Patient and Visit entities. A visit is also associated with a particular physician, whose information is stored in the Physician table. Every visit is associated with one patient and one primary physician. A physician will have many visits over the course of their career, but each visit only has one physician, which can be seen by the one to many relationship between Physician and Visit.

Each visit also takes place in a particular room. Information about each room such as its number, name, and the wing it is located in (North, South, East, or West) is stored in the Room entity. Each visit is associated with one room, but a particular room will be associated with many visits, which can be seen in the one to many relationship between Room and Visit. It is important to note that while a patient may have tests done in multiple rooms on the same visit (X-ray in one room, MRI in another), each visit is assigned a primary room number where the Physician meets with them privately. 

The clinic also owns a lot of different pieces of medical equipment. Information about this equipment is stored in the Equipment table. The table stores the name of the equipment (e.g. an X-Ray machine), the date the equipment was purchased, and also the price. Additionally every piece of equipment is associated with a particular room. One room can have multiple pieces of equipment, but a particular piece of equipment can only belong to one room. This is shown by the one to many relationship between Room and Equipment. 

Additionally, the clinic can perform many different tests. The Test entity stores information about the different types of medical tests done on a patient. Examples include blood tests, MRIs, etc., and the visitRecord entity stores information about each visit and any potential tests performed. There is a one to many relationship between visitRecord and Test because a particular test can be done multiple times on the same patient, and therefore be found in multiple different visit records. There is also a one to many relationship between Visit and visitRecord because during each visit a patient can have multiple tests performed on them, which will each go into a separate visit record.

Each Visit is associated with one bill (also known as an invoice). This is represented by the one to one relationship between the Visit and Billing tables. While each visit can be associated with multiple visit records, it is important to note that a visit can only have one bill in total, regardless of the number of visit records associated with one visit. 

Each visitRecord then has the potential to generate a Prescription for the patient. One visitRecord can generate multiple prescriptions (E.g. a test revealing a broken bone may lead to multiple pain relief medications prescribed), and each prescription is only tied to one visitRecord. This is evident by the one to many relationship between visitRecord and Prescription. 

This clinic also stores many different medications, which we have organized in the Medications table. The clinic also maintains a list of approved suppliers for which they get their medications from. At this particular clinic, each medication is provided by only one supplier. This is represented by the one to many relationship between the Supplier and Medication tables, as one supplier can provide different medications, but each medication is tied to a particular supplier. Each prescription can only have one medication listed on it. That being said, a particular medication can be listed in multiple different prescriptions. This is evident in the one to many relationship between Medications and Prescriptions.

## Data Model Screenshot
<img width="683" alt="Screen Shot 2023-11-03 at 5 38 33 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/4908112c-e851-4d9d-aef8-22aa579bf928">


## Data Dictionary Screenshots 
<img width="702" alt="Screen Shot 2023-11-03 at 5 39 05 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/14f246e8-86a4-4068-bd7e-70f04786f450">
<img width="709" alt="Screen Shot 2023-11-03 at 5 39 20 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/0156c036-57ab-402e-8205-3ef047210a73">
<img width="680" alt="Screen Shot 2023-11-03 at 5 39 44 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/e5f89fdf-42e0-4d3e-a9f2-92baa5538df2">
<img width="694" alt="Screen Shot 2023-11-03 at 5 39 35 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/57ef789b-7b37-4f6f-90dd-6c6e2f8fb7b5">
<img width="700" alt="Screen Shot 2023-11-03 at 5 40 49 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/39f5a4d1-8bd2-4105-976c-479f5034ffde">
<img width="678" alt="Screen Shot 2023-11-03 at 5 41 21 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/13ba6503-6eb3-41f9-99ca-c96d66100694">
<img width="686" alt="Screen Shot 2023-11-03 at 5 42 13 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/f2ee8ed5-ffd9-43d7-8789-465b8d6d20b0">
<img width="672" alt="Screen Shot 2023-11-03 at 5 41 44 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/87330bae-aa92-4e5c-bcf7-315806ebaf85">
<img width="666" alt="Screen Shot 2023-11-03 at 5 43 09 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/b04e5d57-e24c-4152-b38c-97a19da2fd4a">
<img width="708" alt="Screen Shot 2023-11-03 at 5 42 22 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/35810770-662f-40a9-8237-e4becacdabc5">
<img width="682" alt="Screen Shot 2023-11-03 at 5 44 56 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/3665a852-89c1-4a15-9187-a3017e5cd975">
<img width="695" alt="Screen Shot 2023-11-03 at 5 45 12 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/d845e68d-c499-4866-93db-14cb2edd3e9a">

## Query Matrix
<img width="693" alt="Screen Shot 2023-11-03 at 5 45 29 PM" src="https://github.com/aanjum2003/healthcare/assets/148798153/26e66b4a-24f5-4031-9943-a3a8a40d0324">

## Database Information
Name of Database: ns_F2339217Group7
