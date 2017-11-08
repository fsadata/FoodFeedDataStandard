# Food Sampling Data Standard (Proposed)

### What Is This Document?

This document describes the data standard for submitting food sampling results data to the Food Standards Agency. It describes the fields, their data types and order as well as providing specific guidance on acceptable values and which fields use specific reference data values.

This document does not describe the mechanism by which data can be submitted to the Food Standards Agency (the FSA).

### Who Is This Document For?

This document is written for Local Authority and Laboratory users who need to submit sampling and results data to the FSA.

### How This Document Is Structured

- [Food Standard Overview](#food-standard-overview)
- [Detailed Field Definitions](#detailed-field-definitions)
 1. Local Authority  
 2. Sample Identifier  
 3. Sample Date  
 4. Sample Category  
 5. Brand Name  
 6. Food Description  
 7. Premises Name  
 8. Premises Postcode  
 9. Premises Type  
 10. Sample Reason  
 11. Sample Type  
 12. Follow Up Required  
 13. Follow Up Identifier  
 14. Food Poisoning  
 15. Food Poisoning Details  
 16. Survey Reference Number  
 17. Product Type  
 18. Manufacturer Name  
 19. Distributor Name  
 20. Importer Name  
 21. Country of Origin  
 22. Laboratory  
 23. Laboratory Comments  
 24. Determinand  
 25. Result (Numeric)  
 26. Resut (Text)  
 27. Satisfactory  
 28. Reported Date  
 29. Prosecution  
 30. Output  
 31. Result Fail Code  
 32. Result Level 1  
 33. Result Level 2  
 34. Result Level 3  
 35. Determination  
- Additional Definitions
- File Types
- File Naming Conventions

## Food Standard Overview

The following table lists the fields (name and description), their data types, whether they are optional, and whether they use reference data or a controlled vocabulary.

Index | Field Name | Description | Data Type | Optional | Reference Data
------|------------|-------------|-----------|----------|---------------
1|local_authority|Local Authority identifier|Text|No|Yes
2|sample_id|Sample unique identifier|Text|No|No
3|sample_date|Date sample taken|Date|No|No
4|sample_category|Sample category reference|Text|No|Yes
5|brand_name|Brand name|Text|No|No
6|food_description|**REVIEW** Free text food description|Text|Yes|No
7|premises_name|Name of the premises where the sample was taken|Text|No|No
8|premises_postcode|Post code of the premises where the sample was taken|Text|No|No
9|premises_type|Premises type reference|Text|No|Yes
10|sample_reason|The reason for sampling|Text|No|Yes
11|sample_type|The type of sample|Text|No|Yes
12|follow_up|**DEFINE** Follow up visit required|Boolean|No|Yes
13|follow_up_id|**DEFINE** Original sample unique identifier|Number|Yes|No
14|food_poisoning|**REVIEW** Food poisoning result|Text|No|Yes
15|food_poisoning_details|**REVIEW** Test details of food poisoning|Text|Yes|No
16|survey_number|Survey unique identifier|Number|Yes|No
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
35|determination|**REVIEW** Result of test, chemical found.|No|Yes|1

## Detailed Field Definitions

### 1. Sample Identifier
**Field Name:** `sample_id`  
**Data Type:** Text (32 character maximum)  
**Optional:** No  
**Comments:** The sample number, as recorded by the sampling body. This must be a unique value within the records of that sampling body. It can be any combination of numeric or alphanumeric characters as long as it is unique.  

### 2. Local Authority
**Field Name:** `local_authority`  
**Data Type:** Text (from register)  
**Optional:** No  
**Comments:** This is the three character Local Authority code as listed in the Government Digital Service (GDS) register for [England](https://local-authority-eng.register.gov.uk/), [Northern Ireland](https://local-authority-nir.discovery.openregister.org/), and [Wales](https://principal-local-authority.register.gov.uk/) repsectively. It should be noted that the Northern Ireland register is currently only in discovery, but GDS have advised us that the three character code is unlikely to change.

### 4. Analysis Type
**Field Name:** `analysis_type`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** Yes  
**Comments:** **This field is being considered for deprecation as the determinand field also describes what the tests are for. A sample can also be subject to multiple tests.**  
The acceptable values for this field are:
 - `Microbiological` or `M`
 - `Chemical` or `C`

### 5. Sampling Officer
**Field Name:** `sampling_officer`  
**Data Type:** Text (30 character maximum)  
**Optional:** No  
**Comments:**  **This field should be considered for removal**

### 6. Sample Date
**Field Name:** `sample_date`  
**Data Type:** Date (YYYY-MM-DD)  
**Optional:** No  
**Comments:** The date the sample was taken, this should follow the YYYY-MM-DD format as laid out in the International Standard ISO 8601.

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
**Field Name:** `follow_up_ref`  
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

### 16. Survey
**Field Name:** `survey`  
**Data Type:** Boolean (True/False)  
**Optional:** No  
**Comments:** *This field should not be necessary as can be handled by assessing whether sruvey number field is present or null*  

### 17. Survey Number
**Field Name:** `survey_number`  
**Data Type:** Text ()  
**Optional:** Yes  
**Comments:** A unique reference to identify the survey under which this sample was taken. An entry in the fields indicates that this sample was taken as part of a survey, a null entry indicates that it was not.  

### 18. Brand Name
**Field Name:** `brand_name`  
**Data Type:** Text (50 character maximum)  
**Optional:** No  
**Comments:** The brand name of the product being sampled (where appropriate). Samples that do not have a brand name should be recorded as `N/A`  

### 19. Food Description
**Field Name:** `food_description`  
**Data Type:** Text (255 character maximum)  
**Optional:** Yes  
**Comments:** A free text description of the food being sampled. *This field may not be necessary, and may reduce overall data quality*  

### 20. Sample Type
**Field Name:** `sample_type`  
**Data Type:** Text (from register, format: `00.00.00.00`)  
**Optional:** No  
**Comments:** The [sampling taxonomy](http://data.food.gov.uk/codes/enforcement-monitoring/sampling) defines the acceptable values for this field. The sample taxonomy is a hierarchy of sampling classification with four levels. They are organised as `Clan > Family > Group > Type`. Each item in each level is numbered, these values are concatenated into a single string with a `.` used to separate them. Because they have a strict hierarchical relationship the classification only needs to be reported at the type level (format `00.00.00.00`), the group, family and clan do not need to be supplied.  

### 24. Product Type
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

### 25. Manufacturer
**Field Name:** `manufacturer`  
**Data Type:** Text ()  
**Optional:** Yes  
**Comments:** The name of the manufacturer of the sampled product.  

### 26. Distributor
**Field Name:** `distributor`  
**Data Type:** Text ()  
**Optional:** Yes  
**Comments:** The name of the distributor of the sampled product.  

### 27. Importer
**Field Name:** `importer`  
**Data Type:** Text ()  
**Optional:** Yes  
**Comments:** The name of the importer of the sampled product.  

### 28. Country of Origin
**Field Name:** `country`  
**Data Type:** Text ()  
**Optional:** Yes  
**Comments:** The country of origin. The field `country` from the [GDS Country Register](https://country.register.gov.uk/records) must be used. This is a two character ISO 3166 alpha 2 code.  

### 29. Laboratory Name
**Field Name:** `lab_name`  
**Data Type:** Text ()  
**Optional:** No  
**Comments:** The name of the laboratory completing the testing on the sample. The notation for each lab will be published in due course. In the interim period a plain text name should be used.  

### 30. Laboratory Comments
**Field Name:** `lab_comments`  
**Data Type:** Text (2000 character maximum)  
**Optional:** Yes  
**Comments:** This free text field shows the examiners opinion of the sample.  

### 31. Prosecution
**Field Name:** `prosecution`  
**Data Type:** Boolean (True/False)  
**Optional:** No  
**Comments:** Indicates whether the sample forms part of a prosecution. It is critical to get this field correct as it will make sure that those samples involved in prosecutions are not published.  

### 32. Satisfactory
**Field Name:** `satisfactory`  
**Data Type:** Text (controlled vocabulary)  
**Optional:** No  
**Comments:** Indicates whether a sample is deemed satisfactory for a specific test. The acceptable values are:
 - `Satisfactory` or `S`
 - `Unsatisfactory` or `U`
 - `Borderline` or `B`  

### 33. Report Date
**Field Name:** `report_date`  
**Data Type:** Date (YYYY-MM-DD)  
**Optional:** No  
**Comments:** The date the results were reported, this should follow the YYYY-MM-DD format as laid out in the International Standard ISO 8601.  

### 34. Determinand
**Field Name:** `determinand`  
**Data Type:** Text (from register)  
**Optional:** Yes  
**Comments:** Describes the exact test completed on the sample. The [determinands taxonomy](www.data.food.gov.uk/codes) contains this information. It is heirarchical and has four levels. Only the most detailed level should be used. For example, the test for Tartrazine assessed on a miligrams per kilogram basis has the notation `CE102-05`. 

### 35. Result (Numeric)
**Field Name:** `result_numeric`  
**Data Type:** Number (any valid numeric data type)  
**Optional:** Yes  
**Comments:** The result of the test completed on the sample, where the result is numerical, e.g. `1.4`  

### 36. Result (Text)
**Field Name:** `result_text`  
**Data Type:** Text (255 character maxmium)  
**Optional:** Yes  
**Comments:** The result of the test completed on the sample, where the result cannot be adequately expressed numerically, e.g. `< 1.4` or `less than one`  

### 37. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 38. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 39. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 40. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 41. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 42. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 43. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 44. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 45. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 46. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 47. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  
