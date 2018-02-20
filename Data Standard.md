# Food and Feed Sampling Data Standard (Proposed)

### What Is This Document?

This document describes the data standard for submitting food sampling results data to the Food Standards Agency. It describes the fields, their data types and order as well as providing specific guidance on acceptable values and which fields use specific reference data values.

This document does not describe the mechanism by which data can be submitted to the Food Standards Agency (the FSA).

### Who Is This Document For?

This document is written for Local Authority and Laboratory users who need to submit sampling and results data to the FSA.

### How This Document Is Structured

- [Food Standard Overview](#food-standard-overview) Contains a brief overview of all the fields in the standard.  
- [Field Definitions](#field-definitions) Complete definitions for each field in the standard, includes constraints and specific data type formatting requirements.  
 1. [Local Authority](#1-local-authority)  
 2. [Sample Date](#2-sample-date-time) 
 3. [Sample Identifier](#3-sample-identifier)
 4. [Food or Feed](#4-food-or-feed)  
 5. [Sample Category](#5-sample-identifier)  
 6. [Sample of](#6-sample-of)   
 7. [Premises Name](#7-premises-name)  
 8. [Premises Postcode](#8-premises-postcode)  
 9. [Premises Type](#9-premises-type)  
 10. [Sample Reason](#10-sample-reason)  
 11. [Sample Type](#11-sample-type)  
 11. [Animal Feed_Type](#12-animal-feed-type)  
 12. [Animal Feed Type](#12 animal-feed-type)  
 13. [Follow Up Identifier](#13-follow-up-identifier)  
 14. [Shelf Life Type](#14-shelf-life-type)  
 15. [Durability Date](#15-durability-date)  
 16. [Survey Identifier](#16-survey-identifier)  
 17. [Manufacturer Name](#17-manufacturer-name)  
 18. [Distributor Name](#18-distributor-name)  
 19. [Importer Name](#19-importer-name)  
 20. [Country of Origin](#20-country-of-origin)  
 21. [Sampling Officer](#21-sampling-officer)  
 22. [LA Instructions](#22-la-instructions)  
 23. [Laboratory](#23-laboratory)  
 24. [Laboratory Comments](#24-laboratory-comments)  
 25. [Determinand](#25-determinand)  
 26. [Units](#26-units)  
 27. [Result (Numeric)](#27-result-numeric)  
 28. [Result (Text)](#28-result-text)  
 29. [Satisfactory](#29-satisfactory)  
 30. [Reported Date](#30-eported-date)   
 31. [Result Fail Code](#31-result-fail-code) 
 32. [Deviating Sample Comments](#32-deviating-sample-comments)
 33. [Lab Identifier](#33-lab-identifier)
- [Supported File Types](#supported-file-types)
- [Other Requirements](#other-requirements)
- [File Naming Conventions](#file-naming-conventions)

## Food Standard Overview

The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.

Index | Field Name | Description | Data Type | Optional | Controlled Vocabulary | Source
------|------------|-------------|-----------|----------|-----------------------|-------
1|local_authority|Local Authority identifier|Text|No|Yes|LA
2|sample_date_time|Date and time sample taken|Date|No|No|LA
3|sample_id|Sample unique identifier|Text|No|No|LA
4|food_or_feed|Food or Feed flag|Text|No|Yes|LA
5|sample_category|Sample category reference|Text|No|Yes|LA
6|sample_of|Free text food description|Text|Yes|No|LA
6|sample_of|Free text food description|Text|Yes|No|LA
7|premises_name|Name of the premises where the sample was taken|Text|No|No|LA
8|premises_postcode|Post code of the premises where the sample was taken|Text|No|No|LA
9|premises_type|Premises type reference|Text|No|Yes|LA
10|sample_reason|The reason for sampling|Text|No|Yes|LA
11|sample_type|The type of sample|Text|No|Yes|LA
12|animal_feed_type|The type of feed|Text|Yes|Yes|LA
13|follow_up_id|Original sample unique identifier|text|Yes|No|LA
14|shelf_life_type|Shelf life type reference|Text|No|Yes|LA
15|durability_date|Durability date of the sample|Date|No|No|LA
16|survey_id|Survey unique identifier|text|Yes|No|LA
17|manufacturer|Name of the manufacturer|Text|Yes|No|LA
18|distributor|Name of the distributor|Text|Yes|No|LA
19|importer|Name of the importer|Text|Yes|No|LA
20|country|Country of origin|Text|Yes|Yes|LA
21|sampling_officer|Name of sampling officer|text|No|No|LA
22|la_instructions|Addtional instructions from Local Authority|text|Yes|No|LA
23|laboratory|Laboratory identifier|Text|No|Yes|LA
24|laboratory_comments|Autorisor's opinion of the sample|Text|Yes|No|Lab
25|determinand|Determinand identifier|Text|Yes|Yes|Lab
26|units|Units used|Text|Yes|Yes|Lab
27|result_numeric|Numerical value outcome of test|Number|No|No|Lab
28|result_text|Text explanation of outcome of test|Text|Yes|No|Lab
29|satisfactory|Shows if sample was satisfactory|Text|No|Yes|Lab
30|reported_date|Date results were reported to the Local Authority|Date|No|No|Lab
31|result_fail_code|The result fail code|Text|Yes|No|Lab
32|deviating_sample_comments|If sample is in-line with FLCoP|Text|Yes|No|Lab
33|lab_id|Sample unique identifier|Text|No|No|Lab

## Field Definitions

### 1. Local Authority
**Field Name:** `local_authority`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** No  
**Source:** Local Authority  
**Comments:** This is the three character Local Authority code as listed in the Government Digital Service (GDS) register for [England](https://local-authority-eng.register.gov.uk/), [Northern Ireland](https://local-authority-nir.discovery.openregister.org/), and [Wales](https://principal-local-authority.register.gov.uk/) repsectively. It should be noted that the Northern Ireland register is currently only in discovery, but GDS have advised us that the three character code is unlikely to change.

### 2. Sample Date Time
**Field Name:** `sample_date_time`  
**Data Type:** Date (format: `YYYY-MM-DD hh:mm:ss`)  
**Optional:** No  
**Source:** Local Authority  
**Comments:** The date and time the sample was taken, this should follow the YYYY-MM-DD hh:mm:ss format as laid out in the International Standard ISO 8601.

### 3. Sample Identifier
**Field Name:** `sample_id`  
**Data Type:** Text (32 character limit)  
**Optional:** No  
**Source:** Local Authority  
**Comments:** The sample number, as recorded by the sampling body. This must be a unique value within the records of that sampling body. It can be any combination of numeric or alphanumeric characters as long as it is unique.  

### 4. Food or Feed
**Field Name:** `food_or_feed`  
**Data Type:** Text (Between 0 and 10 characters) 
**Optional:** No  
**Source:** Local Authority  
**Comments:** The acceptable values for this field are:
 - `Food`
 - `Feed`

### 5. Sample Category
**Field Name:** `sample_category`  
**Data Type:** Text (controlled vocabulary, format: `00.00.00.00`)  
**Optional:** No  
**Source:** Local Authority  
**Comments:** The [sampling taxonomy](http://data.food.gov.uk/codes/enforcement-monitoring/sampling) defines the acceptable values for this field. The sample taxonomy is a hierarchy of sampling classification with four levels. They are organised as `Clan > Family > Group > Type`. Each item in each level is numbered, these values are concatenated into a single string with a `.` used to separate them. Because they have a strict hierarchical relationship the classification only needs to be reported at the type level (format `00.00.00.00`), the group, family and clan do not need to be supplied.  

### 6. Food Description
**Field Name:** `sample_of`  
**Data Type:** Text (255 character limit)  
**Optional:** Yes  
**Source:** Local Authority  
**Comments:** A free text description of the food being sampled. Where possible, the description should include the brand name as well as a short description of the type of product, e.g. "Mr Yum's Chocolate Digestives".  

### 7. Premises Name
**Field Name:** `premises_name`  
**Data Type:** Text (50 character limit)  
**Optional:** No  
**Source:** Local Authority  
**Comments:** The name of the premises where the sample was taken. For premises that are one of many locations with the same business name, it is advisabel to include the street where that specific premises is located, e.g. Frank's Deli, High Street.  

### 8. Premises Postcode
**Field Name:** `premises_postcode`  
**Data Type:** Text (Between 5 and 8 characters)  
**Optional:** No  
**Source:** Local Authority  
**Comments:** The postcode of the premises where the sample was taken.  

### 9. Premises Type
**Field Name:** `premises_type`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** No  
**Source:** Local Authority  
**Comments:** The premises type as defined by the [Categories of Food Establishment Register](http://data.food.gov.uk/codes/business/establishment), the notation should be provided, for example a premises designated as a take-away has the notation `RC-TA`.  

### 10. Sample Reason
**Field Name:** `sample_reason`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** No  
**Source:** Local Authority  
**Comments:** The acceptable values for this field are:
 - `Surveillance` or `S`
 - `Monitoring` or `M`
 - `Enforcement` or `E`
 - `Investigation` or `I`

### 11. Sample Type
**Field Name:** `sample_type`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** No  
**Source:** Local Authority  
**Comments:** The acceptable values for this field are:
 - `Formal` or `F`
 - `Informal` or `I`
 - `Complaint` or `C`
 
### 12. Animal Feed Type
**Field Name:** `animal_feed_type`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** Yes  
**Source:** Local Authority  
**Comments:** This is an Animal Feeds field and is the code for the animal species type of the feeding stuff.
 
### 13. Follow Up Identifier
**Field Name:** `follow_up_id`  
**Data Type:** Text (32 character limit)  
**Optional:** Yes  
**Source:** Local Authority  
**Comments:** The unique sample reference number for the original sample to which this is a follow up.

### 14. Shelf life Type
**Field Name:** `shelf_life_type`  
**Data Type:** Text (controlled vocabulary)   
**Optional:** No  
**Source:** Local Authority  
**Comments:** Shelf life provided by the manufacturer/producer/FBO, The acceptable values for this field are:
 - 'Use by' or 'UB'
 - 'Best Before' or 'BB'
 - 'Best Before End' or 'BBE'
 - 'Not Provided' or 'NP'
 
### 15. Durability Date
**Field Name:** `durability_date`  
**Data Type:** Date (format: `YYYY-MM-DD`)  
**Optional:** No  
**Source:** Local Authority  
**Comments:** The durability date of the sample, this should follow the YYYY-MM-DD format as laid out in the International Standard ISO 8601.

### 16. Survey Identifier
**Field Name:** `survey_id`  
**Data Type:** Text (50 character limit)  
**Optional:** Yes  
**Source:** Local Authority  
**Comments:** A unique reference to identify the survey under which this sample was taken. An entry in the fields indicates that this sample was taken as part of a survey, a null entry indicates that it was not.  

### 17. Manufacturer Name
**Field Name:** `manufacturer`  
**Data Type:** Text (255 character limit)  
**Optional:** Yes  
**Source:** Local Authority  
**Comments:** The name of the manufacturer of the sampled product.  

### 18. Distributor Name
**Field Name:** `distributor`  
**Data Type:** Text (255 character limit)  
**Optional:** Yes  
**Source:** Local Authority  
**Comments:** The name of the distributor of the sampled product.  

### 19. Importer Name
**Field Name:** `importer`  
**Data Type:** Text (255 character limit)  
**Optional:** Yes  
**Source:** Local Authority  
**Comments:** The name of the importer of the sampled product.  

### 20. Country of Origin
**Field Name:** `country`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** Yes  
**Source:** Local Authority  
**Comments:** The country of origin. The field `country` from the [GDS Country Register](https://country.register.gov.uk/records) must be used. This is a two character ISO 3166 alpha 2 code.  

### 21. Sampling Officer
**Field Name:** `sampling_officer`  
**Data Type:** Text (255 character limit)  
**Optional:** No  
**Source:** Local Authority  
**Comments:** The name of the sampling officer.  

### 22. LA Instructions
**Field Name:** `la_instructions`  
**Data Type:** Text (2000 character limit)  
**Optional:** Yes  
**Source:** Local Authority   
**Comments:** This free text field shows any Local Authority's supplementary instructions.  

### 23. Laboratory
**Field Name:** `laboratory`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** No  
**Source:** Local Authority  
**Comments:** The code representing the laboratory completing the testing on the sample. The notation for each lab can be found in the [approved laboratories register](http://data.food.gov.uk/codes/controlled-establishments/laboratories/_approved-laboratory).  

### 24. Laboratory Comments
**Field Name:** `lab_comments`  
**Data Type:** Text (2000 character limit)  
**Optional:** Yes  
**Source:** Laboratory  
**Comments:** This free text field shows the authoriser's opinion of the sample.  

### 25. Determinand
**Field Name:** `determinand`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** Yes  
**Source:** Laboratory  
**Comments:** Describes the exact test completed on the sample. The [determinands taxonomy](www.data.food.gov.uk/codes) contains this information. It is heirarchical and has four levels. Only the most detailed level should be used. For example, the test for Tartrazine assessed on a miligrams per kilogram basis has the notation `CE102-05`.  

### 26. Units
**Field Name:** `units`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** Yes  
**Source:** Laboratory  
**Comments:** Describes the units used in the results / test completed on the sample.   e.g. '%', 'g/100g', 'cfu per gram', 'mg/kg', 'g/100g' etc.

### 27. Result (Numeric)
**Field Name:** `result_numeric`  
**Data Type:** Number (any numeric data type)  
**Optional:** Yes  
**Source:** Laboratory  
**Comments:** The result of the test completed on the sample, where the result is numerical, e.g. `1.4`  

### 28. Result (Text)
**Field Name:** `result_text`  
**Data Type:** Text (255 character limit)  
**Optional:** Yes  
**Source:** Laboratory  
**Comments:** The result of the test completed on the sample, where the result cannot be expressed numerically, e.g. `<1.4` or `less than one`  

### 29. Satisfactory
**Field Name:** `satisfactory`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** No  
**Source:** Laboratory  
**Comments:** Indicates whether a sample is deemed satisfactory for a specific test. The acceptable values are:
 - `Satisfactory` or `S`
 - `Unsatisfactory` or `U`
 - `Borderline` or `B`  
 - `Potential injurious to health / unfit for human consumption` or `P` 

### 30. Reported Date
**Field Name:** `report_date`  
**Data Type:** Date (format: `YYYY-MM-DD`)  
**Optional:** No  
**Source:** Laboratory  
**Comments:** The date the results were reported, this should follow the YYYY-MM-DD format as laid out in the International Standard ISO 8601.  

### 31. Result Fail Code
**Field Name:** `result_fail_code`  
**Data Type:** Test (255 character limit)  
**Optional:** Yes  
**Source:** Laboratory  
**Comments:** This is the outcome failcode for the test applied. This captures the judgement on the result by the approver.  

### 32. Deviating Sample Comments
**Field Name:** `deviating_sample_comments`  
**Data Type:** Test (255 character limit)  
**Optional:** Yes  
**Source:** Laboratory  
**Comments:** To record if the sample isn’t in line with the FLCoP or if temp control requirements not met..  

### 33. Lab Identifier
**Field Name:** `lab_id`  
**Data Type:** Text (32 character limit)  
**Optional:** No  
**Source:** Laboratory  
**Comments:** The sample number, as recorded by the lab. This must be a unique value within the records of that lab. It can be any combination of numeric or alphanumeric characters as long as it is unique.  

## Supported File Types

Currently we are supporting the standard for comma separated values (CSV), Json and XML files.

The [current standard for CSV](https://tools.ietf.org/html/rfc4180) gives a detailed explanation of the common format for CSV files. It's concise and clear and we recommend reading it.

## Other Requirements

### Text Fields

The majority of the fields in the standard are text, which needs to be treated carefully when stored in a CSV file. All text fields must be enclosed within double quotes `"this is the text"`. You should try to avoid using double quotes within a text field as this can cause the field to be misread, but the RFC4180 standard allows it if handled appropriately.

>If double-quotes are used to enclose fields, then a double-quote appearing inside a field must be escaped by preceding it with another double quote. For example: `"aaa","b""bb","ccc"`

### Encoding

Where possible please use `UTF-8` encoding.

## File Naming Conventions

In order to make it easy for us to manage the files longer term, it will be important to name files so that we can tell who has submitted them and the time period that each file covers. The format will be the laboratory code from the laboratories register, and the date of submission in `YYYYMMDD` format.

For example, the file from the laboratory with code `LAB10` for sampling data submitted the 31st of January 2017 would be named `LAB1020170131.csv`.
