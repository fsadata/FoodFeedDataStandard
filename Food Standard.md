# Food Sampling Data Standard (Proposed)

### What Is This Document?

This document describes the data standard for submitting food sampling results data to the Food Standards Agency. It describes the fields, their data types and order as well as providing specific guidance on acceptable values and which fields use specific reference data values.

This document does not describe the mechanism by which data can be submitted to the Food Standards Agency (the FSA).

### Who Is This Document For?

This document is written for Local Authority and Laboratory users who need to submit sampling and results data to the FSA.

### How This Document Is Structured

1. [Food Standard Overview](#food-standard-overview)
2. [Detailed Field Definitions](#detailed-field-definitions)
3. Additional Definitions
4. File Types
5. File Naming Conventions

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
**Optional:** This field is not optional  
**Comments:** The sample number, as recorded by the sampling body. This must be a unique value within the records of that sampling body. It can be any combination of numeric or alphanumeric characters as long as it is unique.  

### 2. Local Authority
**Field Name:** `local_auth`  
**Data Type:** Text (3 character Local Authority code)  
**Optional:** This field is not optional  
**Comments:** This is the three character Local Authority code as listed in the Government Digital Service (GDS) register for [England](https://local-authority-eng.register.gov.uk/), [Northern Ireland](https://local-authority-nir.discovery.openregister.org/), and [Wales](https://principal-local-authority.register.gov.uk/) repsectively. It should be noted that the Northern Ireland register is currently only in discovery, but GDS have advised us that the three character code is unlikely to change.
