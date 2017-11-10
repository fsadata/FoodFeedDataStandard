# Food Sampling Data Standard (Proposed)

### What Is This Document?

This document describes the data standard for submitting food sampling results data to the Food Standards Agency. It describes the fields, their data types and order as well as providing specific guidance on acceptable values and which fields use specific reference data values.

This document does not describe the mechanism by which data can be submitted to the Food Standards Agency (the FSA).

### Who Is This Document For?

This document is written for Local Authority and Laboratory users who need to submit sampling and results data to the FSA.

### How This Document Is Structured

- [Food Standard Overview](#food-standard-overview) Contains a brief overview of all the fields in the standard.  
- [Field Definitions](#field-definitions) Complete definitions for each field in the standard, includes constraints and specific data type formatting requirements.  
 1. [Local Authority](#1-local-authority)  
 2. [Sample Date](#2-sample-date)  
 3. [Sample Identifier](#3-sample-identifier)  
 4. [Sample Category](#4-sample-identifier)  
 5. [Brand Name](#5-brand-name)  
 6. [Food Description](#6-food-description)  
 7. [Premises Name](#7-premises-name)  
 8. [Premises Postcode](#8-premises-postcode)  
 9. [Premises Type](#9-premises-type)  
 10. [Sample Reason](#10-sample-reason)  
 11. [Sample Type](#11-sample-type)  
 12. [Follow Up Required](#12-follow-up-required)  
 13. [Follow Up Identifier](#13-follow-up-identifier)  
 14. [Food Poisoning](#14-food-poisoning)  
 15. [Food Poisoning Details](15-#food-poisoning-details)  
 16. [Survey Identifier](#16-survey-identifier)  
 17. [Product Type](#17-product-identifier)  
 18. [Manufacturer Name](#18-manufacturer-name)  
 19. [Distributor Name](#19-distributor-name)  
 20. [Importer Name](#20-importer-name)  
 21. [Country of Origin](#21-country-of-origin)  
 22. [Laboratory](#22-laboratory)  
 23. [Laboratory Comments](#23-laboratory-comments)  
 24. [Determinand](#24-determinand)  
 25. [Result (Numeric)](#25-result-numeric)  
 26. [Resut (Text)](#26-result-text)  
 27. [Satisfactory](#27-satisfactory)  
 28. [Reported Date](#28-reported-date)  
 29. [Prosecution](#29-prosecution)  
 30. [Output](#30-output)  
 31. [Result Fail Code](#31-result-fail-code)  
 32. [Result Level 1](#32-result-level-1)  
 33. [Result Level 2](#33-result-level-2)  
 34. [Result Level 3](#34-result-level-3)  
 35. [Determination](#35-determination)  
- Supported File Types
- Other Requirements
- File Naming Conventions

## Food Standard Overview

The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.

Index | Field Name | Description | Data Type | Optional | Controlled Vocabulary
------|------------|-------------|-----------|----------|----------------------
1|local_authority|Local Authority identifier|Text|No|Yes
2|sample_date|Date sample taken|Date|No|No
3|sample_id|Sample unique identifier|Text|No|No
4|sample_category|Sample category reference|Text|No|Yes
5|brand_name|Brand name|Text|No|No
6|food_description|**REVIEW** Free text food description|Text|Yes|No
7|premises_name|**DEFINE** Name of the premises where the sample was taken|Text|No|No
8|premises_postcode|Post code of the premises where the sample was taken|Text|No|No
9|premises_type|Premises type reference|Text|No|Yes
10|sample_reason|The reason for sampling|Text|No|Yes
11|sample_type|The type of sample|Text|No|Yes
12|follow_up|**DEFINE** Follow up visit required|Boolean|No|Yes
13|follow_up_id|**DEFINE** Original sample unique identifier|Number|Yes|No
14|food_poisoning|**REVIEW** Food poisoning result|Text|No|Yes
15|food_poisoning_details|**REVIEW** Test details of food poisoning|Text|Yes|No
16|survey_id|Survey unique identifier|Number|Yes|No
17|product_type|**REVIEW** Product type|Text|No|Yes
18|manufacturer|Name of the manufacturer|Text|Yes|No
19|distributor|Name of the distributor|Text|Yes|No
20|importer|Name of the importer|Text|Yes|No
21|country|Country of origin|Text|Yes|Yes
22|laboratory|Laboratory identifier|Text|No|Yes
23|laboratory_comments|Examiner's opinion of the sample|Text|Yes|No
24|determinand|Determinand identifier|Text|Yes|Yes
25|result_numeric|Numerical value outcome of test|Number|No|No
26|result_text|Text explanation of outcome of test|Text|Yes|No
27|satisfactory|Shows if sample was satisfactory|Text|No|Yes
28|reported_date|Date results were reported to the Local Authority|Date|No|No
29|prosecution|Does the sample form part of a prosecution|Boolean|No|Yes
30|output|**REVIEW** Test fields, not sure of value|Text|Yes|No
31|result_fail_code|**REVIEW** Codes relating to result level 1|Text|Yes|No
32|result_level_1|**REVIEW** Description of results at top level|Text|Yes|Yes
33|result_level_2|**REVIEW** Description of results at next level|Text|Yes|Yes
34|result_level_3|**REVIEW** Summary description of test result|Text|Yes|Yes
35|determination|**REVIEW** Result of test, chemical found.|No|Yes|No

## Field Definitions

### Local Authority
**Field Name:** `local_authority`  
**Data Type:** Text (from register)  
**Optional:** No  
**Comments:** This is the three character Local Authority code as listed in the Government Digital Service (GDS) register for [England](https://local-authority-eng.register.gov.uk/), [Northern Ireland](https://local-authority-nir.discovery.openregister.org/), and [Wales](https://principal-local-authority.register.gov.uk/) repsectively. It should be noted that the Northern Ireland register is currently only in discovery, but GDS have advised us that the three character code is unlikely to change.

### 2. Sample Date
**Field Name:** `sample_date`  
**Data Type:** Date (YYYY-MM-DD)  
**Optional:** No  
**Comments:** The date the sample was taken, this should follow the YYYY-MM-DD format as laid out in the International Standard ISO 8601.

### 3. Sample Identifier
**Field Name:** `sample_id`  
**Data Type:** Text (32 character maximum)  
**Optional:** No  
**Comments:** The sample number, as recorded by the sampling body. This must be a unique value within the records of that sampling body. It can be any combination of numeric or alphanumeric characters as long as it is unique.  

### 4. Sample Category
**Field Name:** `sample_category`  
**Data Type:** Text (from register, format: `00.00.00.00`)  
**Optional:** No  
**Comments:** The [sampling taxonomy](http://data.food.gov.uk/codes/enforcement-monitoring/sampling) defines the acceptable values for this field. The sample taxonomy is a hierarchy of sampling classification with four levels. They are organised as `Clan > Family > Group > Type`. Each item in each level is numbered, these values are concatenated into a single string with a `.` used to separate them. Because they have a strict hierarchical relationship the classification only needs to be reported at the type level (format `00.00.00.00`), the group, family and clan do not need to be supplied.  

### 5. Brand Name
**Field Name:** `brand_name`  
**Data Type:** Text (50 character maximum)  
**Optional:** No  
**Comments:** The brand name of the product being sampled (where appropriate). Samples that do not have a brand name should be recorded as `N/A`  

### 6. Food Description
**Field Name:** `food_description`  
**Data Type:** Text (255 character maximum)  
**Optional:** Yes  
**Comments:** A free text description of the food being sampled. *This field may not be necessary, and may reduce overall data quality*  

### 7. Premises Name
**Field Name:** `premises_name`  
**Data Type:** Text (50 character maximum)  
**Optional:** No  
**Comments:** The name of the premises where the sample was taken. *This definition needs more clarity for how to handle things like chains with multiple branches* 

### 8. Premises Postcode
**Field Name:** `premises_postcode`  
**Data Type:** Text (Between 5 and 8 characters)  
**Optional:** No  
**Comments:** The postcode of the premises where the sample was taken.  

### 9. Premises Type
**Field Name:** `premises_type`  
**Data Type:** Text (from register)  
**Optional:** No  
**Comments:** The premises type as defined by the [Categories of Food Establishment Register](http://data.food.gov.uk/codes/business/establishment), the notation should be provided, for example a premises designated as a take-away has the notation `RC-TA`.  

### 10. Sample Reason
**Field Name:** `sample_reason`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** No  
**Comments:** The acceptable values for this field are:
 - `Surveillance` or `S`
 - `Monitoring` or `M`
 - `Enforcement` or `E`
 - `Investigation` or `I`

### 11. Sample Type
**Field Name:** `sample_type`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** No  
**Comments:** The acceptable values for this field are:
 - `Formal` or `F`
 - `Informal` or `I` 

### 12. Follow Up
**Field Name:** `follow_up`  
**Data Type:** Boolean (True/False)  
**Optional:** No  
**Comments:** Indicates whether this sample was taken during a follow-up visit. **This isn't entirely clear, could be to indicate a follow up is required -- DECISION NEEDED**  

### 13. Follow Up Reference
**Field Name:** `follow_up_id`  
**Data Type:** Text (32 character maximum)  
**Optional:** Yes  
**Comments:** The unique sample reference number for the original sample to which this is a follow up.

### 14. Food Poisoning
**Field Name:** `food_poisoning`  
**Data Type:** Boolean (True/False)  
**Optional:** No  
**Comments:**  *Needs better definition*

### 15. Food Poisoning Details
**Field Name:** `food_poisoning_details`  
**Data Type:** Text ()  
**Optional:** Yes  
**Comments:** *Needs better definition*

### 16. Survey Identifier
**Field Name:** `survey_id`  
**Data Type:** Text ()  
**Optional:** Yes  
**Comments:** A unique reference to identify the survey under which this sample was taken. An entry in the fields indicates that this sample was taken as part of a survey, a null entry indicates that it was not.  

### 17. Product Type
**Field Name:** `product_type`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** No  
**Comments:** *This field should be considered for deprecation as it duplicates information with the sample type* 
The acceptable values for this field are:
 - `Raw` or `R`
 - `Ready to eat` or `E`
 - `Swab` oe `S`
 - `Non-food` or `N`
 - `Processed` or `P` 

### 18. Manufacturer Name
**Field Name:** `manufacturer`  
**Data Type:** Text ()  
**Optional:** Yes  
**Comments:** The name of the manufacturer of the sampled product.  

### 19. Distributor Name
**Field Name:** `distributor`  
**Data Type:** Text ()  
**Optional:** Yes  
**Comments:** The name of the distributor of the sampled product.  

### 20. Importer Name
**Field Name:** `importer`  
**Data Type:** Text ()  
**Optional:** Yes  
**Comments:** The name of the importer of the sampled product.  

### 21 Country of Origin
**Field Name:** `country`  
**Data Type:** Text ()  
**Optional:** Yes  
**Comments:** The country of origin. The field `country` from the [GDS Country Register](https://country.register.gov.uk/records) must be used. This is a two character ISO 3166 alpha 2 code.  

### 22. Laboratory
**Field Name:** `laboratory`  
**Data Type:** Text ()  
**Optional:** No  
**Comments:** The name of the laboratory completing the testing on the sample. The notation for each lab will be published in due course. In the interim period a plain text name can be used.  

### 23. Laboratory Comments
**Field Name:** `lab_comments`  
**Data Type:** Text (2000 character maximum)  
**Optional:** Yes  
**Comments:** This free text field shows the examiners opinion of the sample.  

### 24. Determinand
**Field Name:** `determinand`  
**Data Type:** Text (from register)  
**Optional:** Yes  
**Comments:** Describes the exact test completed on the sample. The [determinands taxonomy](www.data.food.gov.uk/codes) contains this information. It is heirarchical and has four levels. Only the most detailed level should be used. For example, the test for Tartrazine assessed on a miligrams per kilogram basis has the notation `CE102-05`.  

### 25. Result (Numeric)
**Field Name:** `result_numeric`  
**Data Type:** Number (any valid numeric data type)  
**Optional:** Yes  
**Comments:** The result of the test completed on the sample, where the result is numerical, e.g. `1.4`  

### 26. Result (Text)
**Field Name:** `result_text`  
**Data Type:** Text (255 character limit)  
**Optional:** Yes  
**Comments:** The result of the test completed on the sample, where the result cannot be expressed numerically, e.g. `<1.4` or `less than one`  

### 27. Satisfactory
**Field Name:** `satisfactory`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** No  
**Comments:** Indicates whether a sample is deemed satisfactory for a specific test. The acceptable values are:
 - `Satisfactory` or `S`
 - `Unsatisfactory` or `U`
 - `Borderline` or `B`  

### 28. Reported Date
**Field Name:** `report_date`  
**Data Type:** Date (YYYY-MM-DD)  
**Optional:** No  
**Comments:** The date the results were reported, this should follow the YYYY-MM-DD format as laid out in the International Standard ISO 8601.  

### 29. Prosecution
**Field Name:** `prosecution`  
**Data Type:** Boolean (True/False)  
**Optional:** No  
**Comments:** Indicates whether the sample forms part of a prosecution. It is critical to get this field correct as it will make sure that those samples involved in prosecutions are not published.  

### 30. Output
**Field Name:** `output`  
**Data Type:** Text (255 character limit)  
**Optional:** Yes  
**Comments:** This field requires a full definition.  

### 31. Result Fail Code
**Field Name:** `result_fail_code`  
**Data Type:** Test (255 character limit)  
**Optional:** Yes  
**Comments:** This field requires a full definition.  

### 32. Result Level 1
**Field Name:** `result_level_1`  
**Data Type:** Test (255 character limit)  
**Optional:** Yes  
**Comments:** This field requires a full definition.  

### 31. Result Level 2
**Field Name:** `result_level_2`  
**Data Type:** Test (255 character limit)  
**Optional:** Yes  
**Comments:** This field requires a full definition.  

### 31. Result Level 3
**Field Name:** `result_level_3`  
**Data Type:** Test (255 character limit)  
**Optional:** Yes  
**Comments:** This field requires a full definition.  

### 31. Determination
**Field Name:** `determination`  
**Data Type:** Test (255 character limit)  
**Optional:** Yes  
**Comments:** This field requires a full definition.  

## Supported File Types

Currently we are only supporting the standard for comma separated values (CSV) files. We have chosen this format as it is open, widely supported and easy to understand. Our new process for submitting the data to the FSA means that using CSV we can do some validation on files as they are submitted.

The [current standard for CSV](https://tools.ietf.org/html/rfc4180) gives a detailed explanation of the common format for CSV files. It's concise and clear and we recommend reading it.

We expect to be able to support other formats (e.g. JSON or XML) in future, and are actively exploring it, but this would mean the sender would be responsible for validating their data against the standard.

## Other Requirements

### Text Fields

The majority of the fields in the standard are text, which needs to be treated carefully when stored in a CSV file. All text fields must be enclosed within double quotes `"this is the text"`. You should try to avoid using double quotes within a text field as this can cause the field to be misread, but the RFC4180 standard allows it if handled appropriately >If double-quotes are used to enclose fields, then a double-quote
       appearing inside a field must be escaped by preceding it with another double quote. For example: `"aaa","b""bb","ccc"`