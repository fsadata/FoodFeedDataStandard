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

### 1. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text (32 character maximum)  
**Optional:** No  
**Comments:** The sample number, as recorded by the sampling body. This must be a unique value within the records of that sampling body. It can be any combination of numeric or alphanumeric characters as long as it is unique.  

### 2. Local Authority
**Field Name:** `local_auth`  
**Data Type:** Text (3 character Local Authority code)  
**Optional:** No  
**Comments:** This is the three character Local Authority code as listed in the Government Digital Service (GDS) register for [England](https://local-authority-eng.register.gov.uk/), [Northern Ireland](https://local-authority-nir.discovery.openregister.org/), and [Wales](https://principal-local-authority.register.gov.uk/) repsectively. It should be noted that the Northern Ireland register is currently only in discovery, but GDS have advised us that the three character code is unlikely to change.

### 3. Local Authority Name
**Field Name:** `local_auth_name`  
**Data Type:** Text (50 character maximum)  
**Optional:** Yes  
**Comments:** **This field should be considered for removal**  

### 4. Analysis Type
**Field Name:** `analysis_type`  
**Data Type:** Text (Fixed values)  
**Optional:** Yes  
**Comments:** **This field should be considered for removal**  
The acceptable values for this field are:
 - Microbiological
 - Chemical

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
**Comments:** The name of the premises where the sample was taken. 

### 8. Premises Postcode
**Field Name:** `premises_postcode`  
**Data Type:** Text (Between 5 and 8 characters)  
**Optional:** No  
**Comments:** The postcode of the premises where the sample was taken.  

### 9. Premises Type
**Field Name:** `premises_type`  
**Data Type:** Text (5 character maximum)  
**Optional:** No  
**Comments:** The premises type as defined by the [Categories of Food Establishment Register](http://data.food.gov.uk/codes/business/establishment), the notation should be provided, for example a premises designated as a take-away has the notation `RC-TA`.  

### 10. Sample Reason
**Field Name:** `sample_reason`  
**Data Type:** Text (13 character maximum)  
**Optional:** No  
**Comments:** The acceptable values for this field are:
 - Surveillance
 - Monitoring
 - Enforcement
 - Investigation

### 11. Sample Type
**Field Name:** `sample_type`  
**Data Type:** Text (8 character maximum)  
**Optional:** No  
**Comments:** The acceptable values for this field are:
 - Formal
 - Informal  

### 12. Follow Up
**Field Name:** `follow_up`  
**Data Type:** Boolean (True/False)  
**Optional:** No  
**Comments:** Indicates whether a follow-up visit is required.  

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

### 16. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 17. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 18. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 19. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 20. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 21. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 22. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 23. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 24. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 25. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 26. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 27. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 28. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 29. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 30. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 31. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 32. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 33. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

### 34. Sample Number
**Field Name:** `sample_no`  
**Data Type:** Text ()  
**Optional:** Yes/No  
**Comments:**  

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
