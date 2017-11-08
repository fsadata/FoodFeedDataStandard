# Food Sampling Data Standard (Proposed)

### What Is This Document?

This document describes the data standard for submitting food sampling results data to the Food Standards Agency. It describes the fields, their data types and order as well as providing specific guidance on acceptable values and which fields use specific reference data values.

This document does not describe the mechanism by which data can be submitted to the Food Standards Agency (the FSA).

### Who Is This Document For?

This document is written for Local Authority and Laboratory users who need to submit sampling and results data to the FSA.

### How This Document Is Structured

- [Food Standard Overview](#food-standard-overview)
- [Detailed Field Definitions](#detailed-field-definitions)
 1. Sample Number  
 2. Local Authority  
 3. Local Authority Name  
 4. Analysis Type  
 5. Sampling Officer  
 6. Sample Date  
 7. Premises Name  
 8. Premises Postcode  
 9. Premises Type  
 10. Sample Reason  
 11. Sample Type  
 12. Follow Up  
 13. Follow Up Reference  
 14. Food Poisoning  
 15. Food Poisoning Details  
 16. Survey  
 17. Survey Number  
 18. Brand Name  
 19. Food Description  
 20. Sample Clan  
 21. Sample Family  
 22. Sample Group  
 23. Sample Type  
 24. Product Type  
 25. Manufacturer  
 26. Distributor  
 27. Importer  
 28. Country of Origin  
 29. Laboratory Name  
 30. Laboratory Comments  
 31. Prosecution  
 32. Satisfactory  
 33. Reported Date  
 34. Result  
 35. Test Result  
 36. Determinand  
 37. Output  
 38. Result Fail Code  
 39. Level 1 Result  
 40. Level 2 Result  
 41. Level 3 Result  
 42. Determination  
 43. Units  
 44. Level 1 Determination  
 45. Level 2 Determination  
 46. Level 3 Determination  
 47. Level 4 Determination  
- Additional Definitions
- File Types
- File Naming Conventions

## Food Standard Overview

The following table lists the fields (name and description), their data types, whether they are optional, and whether they use reference data or a controlled vocabulary.

Index | Field Name | Description | Data Type | Optional | Reference Data
------|------------|-------------|-----------|----------|---------------
1|sample_no|sample unique identifying number|Text|No|No
2|local_auth|Local Authority code from official list|text|No|Yes
3|local_auth_name|Local Authority official name from official list|text|Yes|Yes
4|analysis_type|Type of analysis conducted|text|Yes|Yes
5|sampling_officer|Name of sampling officer|text|No|No
6|sample_date|Date sample taken|date|No|No
7|premise_name|Name of company|text|No|No
8|premise_postcode|Post code of premises form where sample taken.|text|No|No
9|premise_type|Premise type from LAEMS codes - Alnnex_2|text|No|Yes
10|sample_reason|Will be surveillance or monitoring|text|No|Yes
11|sample_type|Type of sample|text|No|Yes
12|follow_up|Follow up visit required|text|No|Yes
13|follow_up_ref|Sample unique identifying number|numerical|Yes|No
14|food_poisoning|Food poisoning result|text|No|Yes
15|food_poisoning_details|Test details of food poisoning|text|Yes|No
16|survey|Was a survey completed.|text|No|Yes
17|survey_number|Survey unique identifying number|numerical|Yes|No
18|brand_name|Free text field for Brand|text|No|No
19|food_description|Free text field for food description|text|Yes|No
20|food_category|Food Category reference data from category decision tree document|text|No|Yes
21|food_sub_cat|As above|text|No|Yes
22|food_sub_sub_cat|As above|text|No|Yes
23|food_sub_sub_sub_cat|As above|text|No|Yes
24|product_type|Product type from set list.|text|No|Yes
25|manufacturer|Manufacturer business|text|Yes|No
26|distributor|Distributer business|text|Yes|No
27|importer|Name of the importer|text|Yes|No
28|country|Country of origin|text|Yes|Yes
29|laboratory_name|Name of Lab that completed the sample.|text|No|Yes
30|laboratory_comments|Will be examiners opinion of the sample.|text|Yes|No
31|prosecution|Was a prosecution completed.|text|No|Yes
32|satisfactory|Need to have labs record as yes, no borderline|text|No|Yes
33|reported_date|Date results reported to LA|date|No|No
34|result|Numerical value relating to outcome of test|number|No|No
35|test_result|Text explanation of result|text|Yes|No
36|det|Determination - looks like codes|text|Yes|No
37|output|Test fields, not sure of value|text|Yes|No
38|result_fail_code|Codes relating to result level 1|text|Yes|No
39|result_level_1|Description of results at top level|text|Yes|Yes
40|result_level_2|Description of results at next level|text|Yes|Yes
41|result_level_3|Summary description of test result|text|Yes|Yes
42|determination|Result of test, chemical found.|text|No|Yes
43|units|Measurement of results|test|No|Yes
44|det_level_1|Determination Level 1|text|No|Yes
45|det_level_2|Determination Level 2|text|No|Yes
46|det_level_3|Determination Level 3|text|No|Yes
47|det_level_4|Determination Level 4|text|No|Yes

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
**Comments:** Indicates whether this sample was taken during a follow-up visit.  

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
**Comments:** Describes the exact test completed on the sample. The [determinands taxonomy](www.data.food.gov.uk/codes) contains this information. It is heirarchical and has four levels. Only the most detailed level should be used.  

### 35. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 36. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

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
