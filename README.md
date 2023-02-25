# CMS_Home_Health_Compare_January_2023_Refresh_Analysis
![CMS_Star_Rating](https://user-images.githubusercontent.com/94148420/214742856-a5c8407f-39a1-4977-aea8-f60cba9fe8de.png)

![Home_Health_Star_Ratings](https://user-images.githubusercontent.com/94148420/214742886-5c719324-640a-4d44-b395-67b8bc43b719.png)

Welcome to the debut of the CMS Home Health Compare Refresh Analysis.  This first edition will feature a comprehensive analysis of the **CMS January 2023 Home Health Compare Refresh**.

### Quick Links
* [Overview](#overview)
* [Quality Star Rating Analysis](#quality-star-rating-analysis)

## Overview
### What is CMS Care Compare?

The Centers for Medicare and Medicaid Services (CMS) has provided a tool called **Care Compare** to *find* and *compare* the different types of Medicare providers.  Care Compare includes the following providers:

* Doctors and Clinicians
* Hospitals
* Nursing Homes, including rehabilitation services
* Home Health Services
* Hospice Care
* Inpatient Rehabilitation Facilities
* Long Term Care Hospitals
* Dialysis Facilities

Care Compare provides information regarding providers and facilities, including contact information, location, quality, and patient experience.  The CMS Care Compare homepage can be found [here](https://www.medicare.gov/care-compare/).  

### Home Health Star Ratings

The focus of this analysis is to take a deeper dive into the **quality** and **patient survey** data that CMS has made publically available through its [Provider Data Catalog](https://data.cms.gov/provider-data/).  CMS updates Home Health Compare on a quarterly basis.  This analysis looks specifically at the data from the **January 2023 Care Compare Refresh**.

Care Compare provides tools, including **star ratings**, that summarize various current health care provider performance measures.  There are two types of home health star ratings:

1.  Quality of Patient Care Star Ratings
2.  Patient Survey Star Ratings

### Quality of Patient Care Star Ratings Overview

CMS states that all Medicare-certified home health agengencies (HHAs) may potentially receive a Quality of Patient Care Star Rating. HHAs must have data for at least 20 complete quality episodes for each measure to be reported on Home Health Care Compare. Completed episodes are paired with the start or resumption of care and end of care OASIS assessments.  OASIS is the *Outcome and Assessment Information Set* and is a group of standard data elements HHAs integrate into their comprehensive assessment to collect and report quality data to CMS.  These data elements are collected and reported at the Start of Care (SOC), Resumption of Care (ROC), Follow-Up (FU), Transfer to in Inpatient Facility (TRN), or Discharge from Agency - not to an inpatient facility (DC).  Episodes must have an end-of-care date within the 12-month reporting period, regardless of the start date. To have a Quality of Patient Care Star Rating computed, HHAs must have reported data for 5 of the 7 measures used in the Quality of Patient Care Star Ratings calculation. 

The 7 measures that are part of the Quality of Patient Star Rating are:

* Timely Initiation of Care (process measure)
* Improvement in Ambulation (outcome measure)
* Improvement in Bed Transferring (outcome measure)
* Improvement in Bathing (outcome measure)
* Improvement in Shortness of Breath (outcome measure)
* Improvement in Management of Oral Medications (outcome measure)
* Acute Care Hospitalization (claims-based) (outcome measure)

### Patient Survey Star Ratings Overview

CMS also states that all Medicare-certified HHAs have the potential to receive a Patient Survey Star Rating. However, HHAs must have 40 or more completed surveys over the four-quarter reporting period to receive Star Ratings for that reporting period. Home health agencies that do not have 40 or more completed surveys for calculating Star Ratings will still have their patinet survey (HHCAHPS) data publicly reported on the Home Health Compare website, but they will not receive star ratings.  HHCAHPS scores based on fewer than 40 completed surveys do not have sufficient statistical reliability to ensure that those scores measure true performance and not noise in the data for reporting star ratings.

The Patient Survey star ratings include these four measures reported on Care Compare:

* Care of Patients (Survey items: Q9, Q16, Q19, and Q24)
* Communication Between Providers and Patients (Survey items: Q2, Q15, Q17, Q18, Q22, and Q23)
* Specific Care Issues (Survey items: Q3, Q4, Q5, Q10, Q12, Q13, and Q14)
* Overall Rating of Care Provided by the Home Health Agency (Q20)

CMS reports that the star rating does not include the *Willingness to Recommend the HHA* item because the results for this item are very similar to those based on the *Overall Rating of Care* item.

Additional detail regarding home health quality and patient survey star ratings can be found [here](https://www.cms.gov/Medicare/Quality-Initiatives-Patient-Assessment-Instruments/HomeHealthQualityInits/HHQIHomeHealthStarRatings).

The quality and patient survey data will be analyzed and presented on three levels:

* National level
* State level
* Type of Ownership level

### Resources
#### Code:
* https://github.com/1on1pt/CMS_Home_Health_Compare_January_2023_Refresh_Analysis/blob/main/HH_Care_Compare_January_2023.ipynb

#### Data:
* https://github.com/1on1pt/CMS_Home_Health_Compare_January_2023_Refresh_Analysis/blob/main/Resources/HHCAHPS_Provider_Jan2023.csv
* https://github.com/1on1pt/CMS_Home_Health_Compare_January_2023_Refresh_Analysis/blob/main/Resources/HH_Provider_Jan2023.csv

#### Software/Data Tools:
* Jupyter Notebook 6.5.2
* Python 3.9.16
* Seaborn 0.12.2
* matplotlib 3.6.2
* numpy 1.23.5

**Back to [Quick Links](#quick-links)**

## Quality Star Rating Analysis

There were a total of 11,609 Medicare certified agencies in the quality dataset. Of those Medicare certified agencies, **only 7786 (67%) had Quality Star Ratings**.  I found that to be an interesting finding and had expected the percentage to be higher.

Once the quality dataset was "cleaned", a star rating dataframe was created that specifically captured the following quality data:

* Overall Quality of Patient Care Star Rating

**And the 7 measures that make up the overall Quality of Patient Care Star Rating**

* How often the home health team began their patients care in a timely manner
* How often patients got better at walking or moving around
* How often patients got better at getting in and out of bed
* How often patients got better at bathing
* How often patients breathing improved
* How often patients got better at taking their drugs correctly by mouth
* How often home health patients had to be admitted to the hospital

### What is the Correlation of Each of the Seven Quality Measures and their Relationship with the Overall Quality Star Rating?

![star_rating_corr_chart](https://user-images.githubusercontent.com/94148420/220209715-58ba0577-d8a9-430d-a9cd-e9f6c8505d1b.png)

Here is the heatmap showing the correlation of the overall quality of patient care star rating and the seven quality measures:

![star_rating_corr_heatmap](https://user-images.githubusercontent.com/94148420/220210118-67c0a6f2-9f35-46a1-bf30-2b5798b63808.png)

The three measures that had the **greatest correlation** to the overall quality of patient care star rating are:

1. How often patients got better at walking or moving around (0.82)
2. How often patients got better at bathing (0.82)
3. How often patients got better at taking their drugs correctly by mouth (0.81)

Interesting to note the 0.86 correlation between *How often patients got better at walking or moving around* and *How often patients got better at bathing*.  This correlation may be in part due to a patient's level of mobility contributes to the bathing rating.

Also, the 0.81 correlation between *How often patients got better at walking or moving around* and *How often patients got better at getting in and out of bed* demonstrates that ambulation/mobility is a contributing factor to the transfer measure.  I've often said that **ambulation is the gait way measure**.

Here is a statistical description of the overall quality star rating and the seven outcome measures:

![star_rating_describe](https://user-images.githubusercontent.com/94148420/220212509-927884cf-461c-4914-871c-75a50aca934c.png)

### What is the Star Rating Distribution Amongst Agencies?

![qual_star_rating_dist_boxpl](https://user-images.githubusercontent.com/94148420/220226467-9e1ce9b5-bfd3-4fa5-83a1-824e0afea4d7.png)

### What is the National Level Quality Star Rating Distribution?

#### <ins>National Quality Star Rating Statistical Description</ins>

![nat_sr_stat_dist](https://user-images.githubusercontent.com/94148420/220228434-86772925-33ff-432e-b453-f28b956e4d5d.png)

#### <ins>National Quality Star Rating Boxplot</ins>

![nat_sr_stat_boxpl](https://user-images.githubusercontent.com/94148420/220228297-3868edfb-3da5-4962-ace3-a1294497d29c.png)

### What is the State Level Quality Star Rating Distribution?

#### <ins>State Level Quality Star Rating Statistical Description (AK through MS)</ins>

![state_sr_stat_desc_1a](https://user-images.githubusercontent.com/94148420/221028675-a65ab789-1f07-4705-bc0e-e9333f68213c.png)

#### <ins>State Level Quality Star Rating Statistical Description (MT through WY)</ins>

![state_sr_stat_desc_2a](https://user-images.githubusercontent.com/94148420/221028907-8180600a-d1d6-40f4-aabe-10d828755b79.png)

#### <ins>State Level Quality Star Rating Boxplot</ins>

![state_sr_stat_boxpl_1](https://user-images.githubusercontent.com/94148420/220785049-9b2e17a0-1dad-4b91-a0ed-bbc755df0422.png)

![state_sr_stat_boxpl_2](https://user-images.githubusercontent.com/94148420/220785203-16011696-5df9-4dbf-901f-9e1de60ae23e.png)

### What is the Quality Star Rating Distribution Based on Type of Ownership?

For home health, CMS catagorizes seven *types of ownership*:

* GOVERNMENT - COMBINATION GOVT & VOLUNTARY
* GOVERNMENT - LOCAL
* GOVERNMENT - STATE/COUNTY
* PROPRIETARY
* VOLUNTARY NON-PROFIT - OTHER
* VOLUNTARY NON-PROFIT - PRIVATE
* VOLUNTARY NON PROFIT - RELIGIOUS AFFILIATION

This analysis will look at each type of ownership separately to see if any differences exist.

#### <ins>Type of Ownership Quality Star Rating Statistical Description</ins>

![too_sr_desc](https://user-images.githubusercontent.com/94148420/221174991-b28401b5-f09b-4463-81ef-506bbfea63ab.png)

#### <ins>Type of Ownership Quality Star Rating Boxplot</ins>

![too_sr_boxplot](https://user-images.githubusercontent.com/94148420/221175388-28bb54b7-e668-454d-8b2f-e1c3455c9533.png)

In addition to the boxplot above, each type of ownership was analyzed for its specific Quality Star Rating distribution.

#### <ins>Government Combination Quality Star Rating Statistical Description</ins>

![gov_combo_sr_desc](https://user-images.githubusercontent.com/94148420/221177343-d88ad39d-eb03-4d91-b4fb-4b341155878a.png)

#### <ins>Government Combination Quality Star Rating Boxplot</ins>

![gov_combo_sr_boxplot](https://user-images.githubusercontent.com/94148420/221177702-41385e7f-815d-44f2-a69e-9ce8f2cdce08.png)

#### <ins>Government Local Quality Star Rating Statistical Description</ins>

![gov_loc_sr_desc](https://user-images.githubusercontent.com/94148420/221178404-3383f007-a1b2-4168-aa7f-f75a53cebd2b.png)

#### <ins>Government Local Quality Star Rating Boxplot</ins>

![gov_loc_sr_boxplot](https://user-images.githubusercontent.com/94148420/221186010-8029055d-8a2e-4cc5-b4e1-9b18e0bc15e8.png)

#### <ins>Government State/County Quality Star Rating Statistical Description</ins>

![gov_sc_sr_desc](https://user-images.githubusercontent.com/94148420/221179036-a8ae4e06-e396-4cf9-8d35-f76035394efd.png)

#### <ins>Government State/County Quality Star Rating Boxplot</ins>

![gov_sc_sr_boxplot](https://user-images.githubusercontent.com/94148420/221180386-56e41ba7-92e7-40fc-bc52-68af1afc39e0.png)


#### <ins>Proprietary Quality Star Rating Statistical Description</ins>

![prop_sr_desc](https://user-images.githubusercontent.com/94148420/221186328-bcf36aeb-a765-4e92-b136-06e7c2787bb3.png)

#### <ins>Proprietary Quality Star Rating Boxplot</ins>

![prop_sr_boxplot](https://user-images.githubusercontent.com/94148420/221186616-1be6f374-2ba3-402c-ad11-08f6d86f28d7.png)

#### <ins>Voluntary Non-Profit Religious Quality Star Rating Statistical Description</ins>

![vol_np_rel_sr_desc](https://user-images.githubusercontent.com/94148420/221186909-7d0eae07-402d-44db-8b2d-584529f59148.png)

#### <ins>Voluntary Non-Profit Religious Quality Star Rating Boxplot</ins>

![vol_np_rel_sr_boxplot](https://user-images.githubusercontent.com/94148420/221187262-eee42831-7766-47f4-9104-8a5e3cf3dc86.png)

#### <ins>Voluntary Non-Profit Other Quality Star Rating Statistical Description</ins>

![vol_np_other_sr_desc](https://user-images.githubusercontent.com/94148420/221187552-ed49d096-609a-4009-9e58-517da510e9b8.png)

#### <ins>Voluntary Non-Profit Other Quality Star Rating Boxplot</ins>

![vol_np_other_sr_boxplot](https://user-images.githubusercontent.com/94148420/221187811-91f9a434-7290-4bb0-974f-ae652d3c13b9.png)

#### <ins>Voluntary Non-Profit Private Quality Star Rating Statistical Description</ins>

![vol_np_private_sr_desc](https://user-images.githubusercontent.com/94148420/221188073-ee78f8e3-5a34-451b-aec0-8235edac3132.png)

#### <ins>Voluntary Non-Profit Private Quality Star Rating Boxplot</ins>

![vol_np_private_sr_boxplot](https://user-images.githubusercontent.com/94148420/221188402-104d6928-3a76-48c5-bfe3-0e3058856546.png)

## Publically Reported Measures NOT Included in the Star Rating Measure

There are ten measures that are included in Home Health Care Compare that are *NOT* included in the Quality Star Rating.  These measures include:

* How often the home health team taught patients (or their family caregivers) about their drugs
* How often the home health team determined whether patients received a flu shot for the current flu season
* How often patients receiving home health care needed urgent, unplanned care in the ER without being admitted
* Changes in skin integrity post-acute care: pressure ulcer/injury
* How often physician-recommended actions to address medication issues were completely timely
* Percent of Residents Experiencing One or More Falls with Major Injury
* Application of Percent of Long Term Care Hospital Patients with an Admission and Discharge Functional Assessment and a Care Plan that Addresses Function
* Discharge to Community (DTC) Risk-Standardized Rate
* Potentially Preventable 30-Day Post Discharge Readmission (PPR) Risk-Standardized Rate
* How much Medicare spends on an episode of care at this agency, compared to Medicare spending across all agencies nationally

The following analysis will take a look at each of these ten measures at the National, State, and Type of Ownership level.

### How Often the Home Health Team Taught Patients (or their family caregivers) About Their Drugs

Take note of all the outliers!

#### <ins>National Teaching Patients/Caregivers About Drugs Statistical Description</ins>

![nat_teach_dr_desc](https://user-images.githubusercontent.com/94148420/221357626-83eebfde-5355-48a0-88b2-308306cee83c.png)

#### <ins>National Teaching Patients/Caregivers About Drugs Boxplot</ins>

![nat_teach_dr_boxplot](https://user-images.githubusercontent.com/94148420/221357743-2d60e093-9435-4468-ba57-126216141baf.png)

#### <ins>State Level Teaching Patients/Caregivers About Drugs Statistical Description (AK through MS)</ins>

![state_teach_dr_desc_1](https://user-images.githubusercontent.com/94148420/221358130-4f9a98f2-c8bb-49ae-842d-e18552f4a2c8.png)

#### <ins>State Level Teaching Patients/Caregivers About Drugs Statistical Description (MT through WY)</ins>

![state_teach_dr_desc_2](https://user-images.githubusercontent.com/94148420/221358342-0d27377c-10a3-4f65-9398-6ad703c71b96.png)

#### <ins>State Level Teaching Patients/Caregivers About Drugs Boxplot</ins>

![state_teach_dr_boxplot_1](https://user-images.githubusercontent.com/94148420/221358453-cefe084d-22c4-4586-85c2-50ab23c0c1ee.png)

![state_teach_dr_boxplot_2](https://user-images.githubusercontent.com/94148420/221358530-24e44ea9-5af5-4e85-9b4e-20c7a5eb8db2.png)

#### <ins>Type of Ownership Teaching Patients/Caregivers About Drugs Statistical Description</ins>

![too_teach_dr_desc](https://user-images.githubusercontent.com/94148420/221358634-352a4cd6-2afa-4622-b9be-c84ce0e51f92.png)

#### <ins>Type of Ownership Teaching Patients/Caregivers About Drugs Boxplot</ins>

![too_teach_dr_boxplot](https://user-images.githubusercontent.com/94148420/221358706-71d730ce-6f69-43a7-bcb5-d4a4a91cf70c.png)

### How Often the Home Health Team Determined Whether Patients Received a Flu Shot for the Current Flu Season

#### <ins>National Flu Shot Statistical Description</ins>

![nat_flu_shot_desc](https://user-images.githubusercontent.com/94148420/221359181-6d360234-921b-4de0-bfb6-41e79583f26f.png)

#### <ins>National Flu Shot Boxplot</ins>

![nat_flu_shot_boxplot](https://user-images.githubusercontent.com/94148420/221359252-f4097cda-e76b-4caa-a6e6-a134aae45ec6.png)

#### <ins>State Level Flu Shot Statistical Description (AK through MS)</ins>

![state_flu_shot_desc_1](https://user-images.githubusercontent.com/94148420/221359370-6c7f53ba-9fd1-4096-a0d3-513956770e08.png)

#### <ins>State Level Flu Shot Statistical Description (MT through WY)</ins>

![state_flu_shot_desc_2](https://user-images.githubusercontent.com/94148420/221359450-175e3f87-fe05-4945-90bb-dd4b2921d1ce.png)

#### <ins>State Level Flu Shot Boxplot</ins>

![state_flu_shot_boxplot_1](https://user-images.githubusercontent.com/94148420/221359566-9c2bbe33-fb4f-4727-8bf7-9eb32047a62a.png)

![state_flu_shot_boxplot_2](https://user-images.githubusercontent.com/94148420/221359608-5e38db7d-0738-45f3-9ec9-861ea70b136b.png)

#### <ins>Type of Ownership Flu Shot Statistical Description</ins>

![too_flu_shot_desc](https://user-images.githubusercontent.com/94148420/221359799-1c04f244-852e-413a-a6f2-5f190b47c61e.png)

#### <ins>Type of Ownership Flu Shot Boxplot</ins>

![too_flu_shot_boxplot](https://user-images.githubusercontent.com/94148420/221359858-74a9dc8b-4e75-46d5-ba80-9fd6246570ee.png)

### How Often Patients Receiving Home Health Care Needed Urgent, Unplanned Care in the ER Without Being Admitted

