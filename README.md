# CMS_Home_Health_Compare_January_2023_Refresh_Analysis
![CMS_Star_Rating](https://user-images.githubusercontent.com/94148420/214742856-a5c8407f-39a1-4977-aea8-f60cba9fe8de.png)

![Home_Health_Star_Ratings](https://user-images.githubusercontent.com/94148420/214742886-5c719324-640a-4d44-b395-67b8bc43b719.png)

Welcome to the debut of the CMS Home Health Compare Refresh Analysis.  This first edition will feature a comprehensive analysis and tell the data story of the **CMS January 2023 Home Health Compare Refresh**.

### Quick Links
* [Overview](#overview)
* [Quality Star Rating Analysis](#quality-star-rating-analysis)
* [Publically Reported Measures NOT Included in the Star Rating Measure](#publically-reported-measures-not-included-in-the-star-rating-measure)
* [Patient Survey Star Rating Analysis](#patient-survey-star-rating-analysis)
* [Patient Survey Additional Analysis - Willingness to Recommend](#patient-survey-additional-analysis---willingness-to-recommend)
* [Patient Survey Additional Analysis - Response Rate](#patient-survey-additional-analysis---response-rate)
* [Summary](#summary)

## Overview
### What is CMS Care Compare?

The Centers for Medicare and Medicaid Services (CMS) has provided a tool called **Care Compare** that allows patients and caregivers to *find* and *compare* the different types of Medicare providers.  Care Compare includes the following providers:

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

CMS also states that all Medicare-certified HHAs have the potential to receive a Patient Survey Star Rating. However, HHAs must have 40 or more completed surveys over the four-quarter reporting period to receive Star Ratings for that reporting period. Home health agencies that do not have 40 or more completed surveys for calculating Star Ratings will still have their patient survey (Home Health Consumer Assessment of Healthcare Providers and Systems or HHCAHPS) data publicly reported on the Home Health Compare website, but they will not receive star ratings.  HHCAHPS scores based on fewer than 40 completed surveys do not have sufficient statistical reliability to ensure that those scores measure true performance and not noise in the data for reporting star ratings.

The Patient Survey star ratings include these four measures reported on Care Compare:

* Care of Patients (Survey items: Q9, Q16, Q19, and Q24)
* Communication Between Providers and Patients (Survey items: Q2, Q15, Q17, Q18, Q22, and Q23)
* Specific Care Issues (Survey items: Q3, Q4, Q5, Q10, Q12, Q13, and Q14)
* Overall Rating of Care Provided by the Home Health Agency (Q20)

CMS reports that the star rating does not include the *Willingness to Recommend the HHA* item because the results for this item are very similar to those based on the *Overall Rating of Care* item.

Additional detail regarding home health quality and patient survey star ratings can be found [here](https://www.cms.gov/Medicare/Quality-Initiatives-Patient-Assessment-Instruments/HomeHealthQualityInits/HHQIHomeHealthStarRatings).

The quality and patient survey data will be analyzed and presented on three levels:

* National
* State
* Type of Ownership

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

### What is the Quality Star Rating Distribution Amongst Agencies?

![qual_star_rating_dist_boxpl](https://user-images.githubusercontent.com/94148420/220226467-9e1ce9b5-bfd3-4fa5-83a1-824e0afea4d7.png)

### What is the National Level Quality Star Rating Distribution?

#### <ins>National Quality Star Rating Statistical Description</ins>

![nat_sr_stat_dist](https://user-images.githubusercontent.com/94148420/220228434-86772925-33ff-432e-b453-f28b956e4d5d.png)

#### <ins>National Quality Star Rating Boxplot</ins>

![nat_sr_stat_boxpl](https://user-images.githubusercontent.com/94148420/220228297-3868edfb-3da5-4962-ace3-a1294497d29c.png)

### What is the State Level Quality Star Rating Distribution?

#### <ins>State Quality Star Rating Statistical Description (AK through MS)</ins>

![state_sr_stat_desc_1a](https://user-images.githubusercontent.com/94148420/221028675-a65ab789-1f07-4705-bc0e-e9333f68213c.png)

#### <ins>State Quality Star Rating Statistical Description (MT through WY)</ins>

![state_sr_stat_desc_2a](https://user-images.githubusercontent.com/94148420/221028907-8180600a-d1d6-40f4-aabe-10d828755b79.png)

#### <ins>State Quality Star Rating Boxplot</ins>

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

**Back to [Quick Links](#quick-links)**

## Publically Reported Measures NOT Included in the Star Rating Measure

There are ten measures that are included in Home Health Care Compare that are *NOT* included in the Quality Star Rating.  These measures include:

* How Often the Home Health Team Taught Patients (or Their Family Caregivers) About Their Drugs
* How Often the Home Health Team Determined Whether Patients Received a Flu Shot for the Current Flu Season
* How Often Patients Receiving Home Health Care Needed Urgent, Unplanned Care in the ER Without Being Admitted
* Changes in Skin Integrity Post-Acute Care: Pressure Ulcer/Injury
* How Often Physician-Recommended Actions to Address Medication Issues Were Completely Timely
* Percent of Residents Experiencing One or More Falls with Major Injury
* Application of Percent of Long Term Care Hospital Patients with an Admission and Discharge Functional Assessment and a Care Plan that Addresses Function
* Discharge to Community (DTC) Risk-Standardized Rate
* Potentially Preventable 30-Day Post Discharge Readmission (PPR) Risk-Standardized Rate
* How much Medicare Spends on an Episode of Care at this Agency, Compared to Medicare Spending Across All Agencies Nationally

The following analysis will take a look at each of these ten measures at the National, State, and Type of Ownership level.

### How Often the Home Health Team Taught Patients (or their family caregivers) About Their Drugs

Take note of all the outliers!

#### <ins>National Teaching Patients/Caregivers About Drugs Statistical Description</ins>

![nat_teach_dr_desc](https://user-images.githubusercontent.com/94148420/221357626-83eebfde-5355-48a0-88b2-308306cee83c.png)

#### <ins>National Teaching Patients/Caregivers About Drugs Boxplot</ins>

![nat_teach_dr_boxplot](https://user-images.githubusercontent.com/94148420/221357743-2d60e093-9435-4468-ba57-126216141baf.png)

#### <ins>State Teaching Patients/Caregivers About Drugs Statistical Description (AK through MS)</ins>

![state_teach_dr_desc_1](https://user-images.githubusercontent.com/94148420/221358130-4f9a98f2-c8bb-49ae-842d-e18552f4a2c8.png)

#### <ins>State Teaching Patients/Caregivers About Drugs Statistical Description (MT through WY)</ins>

![state_teach_dr_desc_2](https://user-images.githubusercontent.com/94148420/221358342-0d27377c-10a3-4f65-9398-6ad703c71b96.png)

#### <ins>State Teaching Patients/Caregivers About Drugs Boxplot</ins>

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

#### <ins>State Flu Shot Statistical Description (AK through MS)</ins>

![state_flu_shot_desc_1](https://user-images.githubusercontent.com/94148420/221359370-6c7f53ba-9fd1-4096-a0d3-513956770e08.png)

#### <ins>State Flu Shot Statistical Description (MT through WY)</ins>

![state_flu_shot_desc_2](https://user-images.githubusercontent.com/94148420/221359450-175e3f87-fe05-4945-90bb-dd4b2921d1ce.png)

#### <ins>State Flu Shot Boxplot</ins>

![state_flu_shot_boxplot_1](https://user-images.githubusercontent.com/94148420/221359566-9c2bbe33-fb4f-4727-8bf7-9eb32047a62a.png)

![state_flu_shot_boxplot_2](https://user-images.githubusercontent.com/94148420/221359608-5e38db7d-0738-45f3-9ec9-861ea70b136b.png)

#### <ins>Type of Ownership Flu Shot Statistical Description</ins>

![too_flu_shot_desc](https://user-images.githubusercontent.com/94148420/221359799-1c04f244-852e-413a-a6f2-5f190b47c61e.png)

#### <ins>Type of Ownership Flu Shot Boxplot</ins>

![too_flu_shot_boxplot](https://user-images.githubusercontent.com/94148420/221359858-74a9dc8b-4e75-46d5-ba80-9fd6246570ee.png)

### How Often Patients Receiving Home Health Care Needed Urgent, Unplanned Care in the ER Without Being Admitted

#### <ins>National ER Without Being Admitted Statistical Description</ins>

![nat_er_wo_adm_desc](https://user-images.githubusercontent.com/94148420/221364902-2d421c75-653f-4de5-a9f7-1a5e16fa39e7.png)

#### <ins>National ER Without Being Admitted Boxplot</ins>

![nat_er_wo_adm_boxplot](https://user-images.githubusercontent.com/94148420/221365016-a9cd56c9-d48c-48aa-8296-b9ccc1f35188.png)

#### <ins>State ER Without Being Admitted Statistical Description (AK through MS)</ins>

![state_er_wo_adm_desc_1](https://user-images.githubusercontent.com/94148420/221365742-cb41ffcc-c430-48a0-8b3a-72c9afbdd104.png)


#### <ins>State ER Without Being Admitted Statistical Description (MT through WY)</ins>

![state_er_wo_adm_desc_2](https://user-images.githubusercontent.com/94148420/221365278-b6805330-9b64-4cc5-8a06-e9f4702a220d.png)

#### <ins>State ER Without Being Admitted Boxplot</ins>

![state_er_wo_adm_boxplot_1](https://user-images.githubusercontent.com/94148420/221365414-dd045922-b830-4358-bc59-5af895244e5d.png)

![state_er_wo_adm_boxplot_2](https://user-images.githubusercontent.com/94148420/221422617-5dc26969-aa93-4da4-88b6-4945a5143a65.png)

#### <ins>Type of Ownership ER Without Being Admitted Statistical Description</ins>

![too_er_wo_adm_desc](https://user-images.githubusercontent.com/94148420/221365530-7c82e759-7e94-483b-8042-d88646e0e665.png)

#### <ins>Type of Ownership ER Without Being Admitted Boxplot</ins>

![too_er_wo_adm_boxplot](https://user-images.githubusercontent.com/94148420/221365585-398f63d5-d812-446f-8e1f-a343bd391bb5.png)

### Changes in Skin Integrity Post-Acute Care: Pressure Ulcer/Injury

#### <ins>National Skin Integrity Pressure Ulcer/Injury Statistical Description</ins>

![nat_si_pu_desc](https://user-images.githubusercontent.com/94148420/221378295-b2ff3e62-3175-4559-ba68-fbb3d4ba841d.png)

#### <ins>National Skin Integrity Pressure Ulcer/Injury Boxplot</ins>

![nat_si_pu_boxplot](https://user-images.githubusercontent.com/94148420/221378342-b22089c9-92fe-47b0-8946-63507ec82dc0.png)

#### <ins>State Skin Integrity Pressure Ulcer/Injury Statistical Description (AK through MS)</ins>

![state_si_pu_desc_1](https://user-images.githubusercontent.com/94148420/221378455-c24b5eaa-dad4-4808-9018-c7caee8d5069.png)

#### <ins>State Skin Integrity Pressure Ulcer/Injury Statistical Description (MT through WY)</ins>

![state_si_pu_desc_2](https://user-images.githubusercontent.com/94148420/221378556-848a94ea-70e2-4c62-b81d-e1a3302b90e9.png)

#### <ins>State Skin Integrity Pressure Ulcer/Injury Boxplot</ins>

![state_si_pu_boxplot_1](https://user-images.githubusercontent.com/94148420/221378671-3fe51996-224c-4bc4-b2c8-a4081e089178.png)

![state_si_pu_boxplot_2](https://user-images.githubusercontent.com/94148420/221378720-9d410906-a41c-4d9e-839f-f89c60492470.png)

#### <ins>Type of Ownership Skin Integrity Pressure Ulcer/Injury Statistical Description</ins>

![too_si_pu_desc](https://user-images.githubusercontent.com/94148420/221378795-8452a00b-b689-4cb8-88b0-8e4ba43436f8.png)

#### <ins>Type of Ownership Skin Integrity Pressure Ulcer/Injury Boxplot</ins>

![too_si_pu_boxplot](https://user-images.githubusercontent.com/94148420/221378872-e68a5ced-a5ed-487d-90db-8cd3fa75f90e.png)

### How Often Physician-Recommended Actions to Address Medication Issues Were Completely Timely

#### <ins>National Medication Issues Were Completed Timely Statistical Description</ins>

![nat_med_tim_desc](https://user-images.githubusercontent.com/94148420/221379062-d7695596-51aa-4200-98a1-21b4165b2950.png)

#### <ins>National Medication Issues Were Completed Timely Boxplot</ins>

![nat_med_tim_boxplot](https://user-images.githubusercontent.com/94148420/221379108-c24df0fd-206a-4e91-905d-cb66f6514010.png)

#### <ins>State Medication Issues Were Completed Timely Statistical Description (AK through MS)</ins>

![state_med_tim_desc_1](https://user-images.githubusercontent.com/94148420/221379178-45dbc0d0-9dc1-45cc-8be5-c14b01a83b25.png)

#### <ins>State Medication Issues Were Completed Timely Statistical Description (MT through WY)</ins>

![state_med_tim_desc_2](https://user-images.githubusercontent.com/94148420/221379238-d12f81ad-9217-4640-b8f7-632b7930b8e2.png)

#### <ins>State Medication Issues Were Completed Timely Boxplot</ins>

![state_med_tim_boxplot_1](https://user-images.githubusercontent.com/94148420/221379356-2dbeeae4-5a6c-47ba-8bb7-9b0d146c8277.png)

![state_med_tim_boxplot_2](https://user-images.githubusercontent.com/94148420/221379754-2f4b3682-345a-4c39-9a5f-c44c5fb19e7c.png)

#### <ins>Type of Ownership Medication Issues Were Completed Timely Statistical Description</ins>

![too_med_tim_desc](https://user-images.githubusercontent.com/94148420/221379462-f424f571-3310-48d0-844d-99f2596a13f0.png)

#### <ins>Type of Ownership Medication Issues Were Completed Timely Boxplot</ins>

![too_med_tim_boxplot](https://user-images.githubusercontent.com/94148420/221379512-efcd5282-8e91-4c88-ac93-2928c5537313.png)

### Percent of Residents Experiencing One or More Falls with Major Injury

#### <ins>National Falls with Major Injury Statistical Description</ins>

![nat_falls_desc](https://user-images.githubusercontent.com/94148420/221412682-c5d84748-4b7c-4456-b7d5-b0fd2dea6956.png)

#### <ins>National Falls with Major Injury Boxplot</ins>

![nat_falls_boxplot](https://user-images.githubusercontent.com/94148420/221412746-8c9819e2-903c-423f-a987-c478f4a99e19.png)

#### <ins>State Falls with Major Injury Statistical Description (AK through MS)</ins>

![state_falls_desc_1](https://user-images.githubusercontent.com/94148420/221412901-cd90723f-37f3-4169-ba85-295f44caf198.png)

#### <ins>State Falls with Major Injury Statistical Description (MT through WY)</ins>

![state_falls_desc_2](https://user-images.githubusercontent.com/94148420/221413020-3c0fb8e4-ebf8-4e7a-a217-0eb45b19defc.png)

#### <ins>State Falls with Major Injury Boxplot</ins>

![state_falls_boxplot_1](https://user-images.githubusercontent.com/94148420/221413171-65b3ceb1-18db-414e-9ac8-634d283e5d9d.png)

![state_falls_boxplot_2](https://user-images.githubusercontent.com/94148420/221413235-83af0bd4-2f8f-4393-b759-8c3bcdd5ed8a.png)

#### <ins>Type of Ownership Falls with Major Injury Statistical Description</ins>

![too_falls_desc](https://user-images.githubusercontent.com/94148420/221413421-d29eff6d-058f-49d3-88f4-5710228dc957.png)

#### <ins>Type of Ownership Falls with Major Injury Boxplot</ins>

![too_falls_boxplot](https://user-images.githubusercontent.com/94148420/221413516-3b673d1c-2ec0-4915-a03d-907fef7877a4.png)

### Application of Percent of Long Term Care Hospital Patients with an Admission and Discharge Functional Assessment and a Care Plan that Addresses Function

#### <ins>National Care Plan Addresses Function Statistical Description</ins>

![nat_care_plan_desc](https://user-images.githubusercontent.com/94148420/221413730-770fd1aa-751b-4320-823b-d95081baace1.png)

#### <ins>National Care Plan Addresses Function Boxplot</ins>

![nat_care_plan_boxplot](https://user-images.githubusercontent.com/94148420/221413863-6b3d3eb4-1722-4b54-b295-078bc0f40b5e.png)

#### <ins>State Care Plan Addresses Function Statistical Description (AK through MS)</ins>

![state_care_plan_desc_1](https://user-images.githubusercontent.com/94148420/221414070-c6865113-0401-4d8a-a8e9-c01ecbf7cfba.png)

#### <ins>State Care Plan Addresses Function Statistical Description (MT through WY)</ins>

![state_care_plan_desc_2](https://user-images.githubusercontent.com/94148420/221414153-8b48b585-92e9-4e62-86a3-1a4ee3ea10eb.png)

#### <ins>State Care Plan Addresses Function Boxplot</ins>

![state_care_plan_boxplot_1](https://user-images.githubusercontent.com/94148420/221414411-9b3b1958-b3ce-4cea-bda4-b40e09d30e5e.png)

![state_care_plan_boxplot_2](https://user-images.githubusercontent.com/94148420/221414480-5b7de2e0-0326-4cd3-84a2-f2bdbb7ab008.png)

#### <ins>Type of Ownership Care Plan Addresses Function Statistical Description</ins>

![too_care_plan_desc](https://user-images.githubusercontent.com/94148420/221414593-fd5a1bb7-e26e-4f35-b90c-17c7b44f4529.png)

#### <ins>Type of Ownership Care Plan Addresses Function Boxplot</ins>

![too_care_plan_boxplot](https://user-images.githubusercontent.com/94148420/221414686-4cb90047-00f9-48eb-9302-a82e29dba242.png)

### Discharge to Community (DTC) Risk-Standardized Rate

#### <ins>National Discharge to Community Statistical Description</ins>

![nat_dtc_desc](https://user-images.githubusercontent.com/94148420/221418235-46a36348-77ac-4a6d-9dc1-c684daf87e2e.png)

#### <ins>National Discharge to Community Boxplot</ins>

![nat_dtc_boxplot](https://user-images.githubusercontent.com/94148420/221418450-f31fc486-ec05-48a2-9a7e-bbdeed248b18.png)

#### <ins>State Discharge to Community Statistical Description (AK through MS)</ins>

![state_dtc_desc_1](https://user-images.githubusercontent.com/94148420/221418572-7f5d4814-3acc-416d-b0e7-34b60c69dc13.png)

#### <ins>State Discharge to Community Statistical Description (MT through WY)</ins>

![state_dtc_desc_2](https://user-images.githubusercontent.com/94148420/221418674-30aa24e4-e1eb-497a-ac5e-efecc147f4f2.png)

#### <ins>State Discharge to Community Boxplot</ins>

![state_dtc_boxplot_1](https://user-images.githubusercontent.com/94148420/221418787-d5b01dc7-216b-43db-bdff-1aec89cac1c3.png)

![state_dtc_boxplot_2](https://user-images.githubusercontent.com/94148420/221418939-dffa86c0-08d2-4907-a6dd-47b3ef7fefa5.png)

#### <ins>Type of Ownership Discharge to Community Statistical Description</ins>

![too_dtc_desc](https://user-images.githubusercontent.com/94148420/221419240-6f57fc8f-8ae1-4669-a38c-68b79acaa30b.png)

#### <ins>Type of Ownership Discharge to Community Boxplot</ins>

![too_dtc_boxplot](https://user-images.githubusercontent.com/94148420/221419347-22f87e54-430e-4c65-aca2-134a105d00c9.png)

### Potentially Preventable 30-Day Post Discharge Readmission (PPR) Risk-Standardized Rate

#### <ins>National 30-Day Readmission Statistical Description</ins>

![nat_readmit_desc](https://user-images.githubusercontent.com/94148420/221419523-3381997f-9c1e-4b81-9a70-164a8d69a541.png)

#### <ins>National 30-Day Readmission Boxplot</ins>

![nat_readmit_boxplot](https://user-images.githubusercontent.com/94148420/221419690-86e19ade-fd16-4f4c-b30c-9202416a556f.png)

#### <ins>State 30-Day Readmission Statistical Description (AK through MS)</ins>

![state_readmit_desc_1](https://user-images.githubusercontent.com/94148420/221419793-bbc6f63d-60f1-4458-b983-40928040bb41.png)

#### <ins>State 30-Day Readmission Statistical Description (MT through WY)</ins>

![state_readmit_desc_2](https://user-images.githubusercontent.com/94148420/221419960-b1bbd9ff-d772-423c-9872-5c62c2fd194b.png)

#### <ins>State 30-Day Readmission Boxplot</ins>

![state_readmit_boxplot_1](https://user-images.githubusercontent.com/94148420/221420229-eef376e8-21a9-419e-9009-01f4b7e46175.png)

![state_readmit_boxplot_2](https://user-images.githubusercontent.com/94148420/221420269-555a57de-054d-4fb7-ac95-18a6d1fc61d5.png)

#### <ins>Type of Ownership 30-Day Readmission Statistical Description</ins>

![too_readmit_desc](https://user-images.githubusercontent.com/94148420/221420360-06b4c239-eb47-4ef8-97d3-72a946243a33.png)

#### <ins>Type of Ownership 30-Day Readmission Boxplot</ins>

![too_readmit_boxplot](https://user-images.githubusercontent.com/94148420/221420435-a6474db6-3e56-46cc-8a6a-8eb587e5cc14.png)

### How much Medicare Spends on an Episode of Care at this Agency, Compared to Medicare Spending Across All Agencies Nationally

#### <ins>National Medicare Spending Statistical Description</ins>

![nat_spend_desc](https://user-images.githubusercontent.com/94148420/221420577-5a250438-dd3a-4bab-877e-a7d88bb9c995.png)

#### <ins>National Medicare Spending Boxplot</ins>

![nat_spend_boxplot](https://user-images.githubusercontent.com/94148420/221420651-64ef41a6-ebdf-4daf-81c3-5dbed8e647fc.png)

#### <ins>State Medicare Spending Statistical Description (AK through MS)</ins>

![state_spend_desc_1](https://user-images.githubusercontent.com/94148420/221420791-a2aca71d-fe84-4d61-9065-bce703c1e4b8.png)

#### <ins>State Medicare Spending Statistical Description (MT through WY)</ins>

![state_spend_desc_2](https://user-images.githubusercontent.com/94148420/221420892-74952fd8-f91c-4b6c-a68e-747d22d6c92f.png)

#### <ins>State Medicare Spending Boxplot</ins>

![state_spend_boxplot_1](https://user-images.githubusercontent.com/94148420/221420997-83c95405-d6d5-4595-a32a-1e517862b27c.png)

![state_spend_boxplot_2](https://user-images.githubusercontent.com/94148420/221421068-3e853c61-bdb3-472e-a88e-e567b7072c5f.png)

#### <ins>Type of Ownership Medicare Spending Statistical Description</ins>

![too_spend_desc](https://user-images.githubusercontent.com/94148420/221421189-8a6c50a1-2200-4158-86ab-9d965fd710b9.png)

#### <ins>Type of Ownership Medicare Spending Boxplot</ins>

![too_spend_boxplot](https://user-images.githubusercontent.com/94148420/221421253-4f14f8e6-dcb9-40af-aa3a-ffc878678b77.png)

**Back to [Quick Links](#quick-links)**

## Patient Survey Star Rating Analysis

There were a total of 11,609 Medicare certified agencies in the patient survey dataset. Of those Medicare certified agencies, **only 4720 (41%) had Patient Survey Star Ratings**.  Again, I found that to be an interesting finding and had expected the percentage to be higher.

Once the patient survey dataset was "cleaned", a patient survey star rating dataframe was created and merged with the quality star rating dataframe.  The patient survey dataset only included the CMS Certification Number (CCN) and no other identifying information.  The two dataframes were merged so that there would be complete identifying information for each agency.  The merged quality star rating and patient survey star rating dataframe specifically captured the following patient survey data:

* Overall Patient Survey Care Star Rating

**And the 4 measures that make up the overall Patient Survey Star Rating**

* Care of Patients
* Communication Between Provider and Patients
* Specific Care Issues
* Overall Rating of Care Provided by the Home Health Agency

Additional analysis will include the following:

* Willingness to Recommend
* Response Rate

### What is the Correlation of Each of the Four Patient Survey Measures and their Relationship with the Overall Patient Survey Star Rating?

![ps_sr_corr_desc_1](https://user-images.githubusercontent.com/94148420/221434935-342d801f-9943-4c63-8304-5dcf8cdcdfd5.png)

![ps_sr_corr_desc_2](https://user-images.githubusercontent.com/94148420/221435007-1267ecde-fa79-4164-8d91-19da673120f0.png)

Here is the heatmap showing the correlation of the overall patient survey star rating and the four patient survey measures:

![ps_sr_corr_heatmap](https://user-images.githubusercontent.com/94148420/221435052-3db566d2-7574-4562-a811-84f1a9879ca1.png)

This is how the four measures correlated with the overall patient survey star rating:

1. Star Rating for Care of Patients (0.84)
2. Star Rating for Communication Between Provider and Patients (0.83)
3. Star Rating for Specific Care Issues (0.77)
4. Star Rating for Overall Rating of Care Provided by the Home Health Agency (0.84)

Here is a statistical description of the overall patient survey star rating and the four outcome measures:

![ps_sr_desc](https://user-images.githubusercontent.com/94148420/221435790-404fb31a-d931-4468-a37e-1c336065c41d.png)

### What is the Patient Survey Star Rating Distribution Amongst Agencies?

![ps_sr_all_agency_dist](https://user-images.githubusercontent.com/94148420/221435916-f76a24c1-260c-4a1e-9f71-71dba9fc68ca.png)

### What is the National Level Patient Survey Rating Distribution?

#### <ins>National Patient Survey Star Rating Statistical Description</ins>

![nat_ps_sr_desc](https://user-images.githubusercontent.com/94148420/221436132-388b13f6-0ae5-4e41-acca-1235d4c837ce.png)

#### <ins>National Patient Survey Star Rating Boxplot</ins>

![nat_ps_sr_boxplot](https://user-images.githubusercontent.com/94148420/221436210-7a01dfe9-78e3-43b2-a04b-cd3541f3e32c.png)

### What is the State Level Patient Survey Star Rating Distribution?

#### <ins>State Patient Survey Star Rating Statistical Description (AK through MT)</ins>

![state_ps_sr_desc_1](https://user-images.githubusercontent.com/94148420/221436443-0cd0eeec-5a94-4d64-9e39-f3d9a166ef04.png)

#### <ins>State Patient Survey Star Rating Statistical Description (NC through WY)</ins>

![state_ps_sr_desc_2](https://user-images.githubusercontent.com/94148420/221443248-6d354806-20e4-4f32-ad17-0f6ea4ebc7a9.png)

#### <ins>State Patient Survey Star Rating Boxplot</ins>

![state_ps_sr_boxplot_1](https://user-images.githubusercontent.com/94148420/221436774-0e2c479e-52e6-4dc7-8e56-59deaa5c4be7.png)

![state_ps_sr_boxplot_2](https://user-images.githubusercontent.com/94148420/221436847-062caa6d-8617-4d73-9acc-04304d9a6fa9.png)

### What is the Patient Survey Star Rating Distribution Based on Type of Ownership?

#### <ins>Type of Ownership Patient Survey Star Rating Statistical Description</ins>

![too_ps_sr_desc](https://user-images.githubusercontent.com/94148420/221439519-4b1f1bd4-2b62-40dc-81c2-283030790cd7.png)

#### <ins>Type of Ownership Patient Survey Star Rating Boxplot</ins>

![too_ps_sr_boxplot](https://user-images.githubusercontent.com/94148420/221439622-47b15441-0a08-4a7d-8677-a0a9b20d6b89.png)

In addition to the boxplot above, each type of ownership was analyzed for its specific Patient Survey Star Rating distribution.

#### <ins>Government Combination Patient Survey Star Rating Statistical Description</ins>

![gov_combo_ps_sr_desc](https://user-images.githubusercontent.com/94148420/221440048-8a2b7995-459d-4380-bcb1-2de9790bbcbc.png)

#### <ins>Government Combination Patient Survey Star Rating Boxplot</ins>

![gov_combo_ps_sr_boxplot](https://user-images.githubusercontent.com/94148420/221440173-2a6e2092-531b-4933-83ce-1cdb37c97191.png)

#### <ins>Government Local Patient Survey Star Rating Statistical Description</ins>

![gov_loc_ps_sr_desc](https://user-images.githubusercontent.com/94148420/221440264-6eb7b6f2-972a-41fb-88d2-355de39bb2cb.png)

#### <ins>Government Local Patient Survey Star Rating Boxplot</ins>

![gov_loc_ps_sr_boxplot](https://user-images.githubusercontent.com/94148420/221440327-078a6b50-5c58-41fc-8d49-4cb757ba951d.png)

#### <ins>Government State/County Patient Survey Star Rating Statistical Description</ins>

![gov_sc_ps_sr_desc](https://user-images.githubusercontent.com/94148420/221440404-1f496158-ebdb-4702-bb8d-1b9916573e1d.png)

#### <ins>Government State/County Patient Survey Star Rating Boxplot</ins>

![gov_sc_ps_sr_boxplot](https://user-images.githubusercontent.com/94148420/221440518-8fc78e75-f800-4522-a769-1460bb73942d.png)

#### <ins>Proprietary Patient Survey Star Rating Statistical Description</ins>

![prop_ps_sr_desc](https://user-images.githubusercontent.com/94148420/221440649-bd7962dd-b0ea-48c2-bf7d-05fc0555f7a1.png)

#### <ins>Proprietary Patient Survey Star Rating Boxplot</ins>

![prop_ps_sr_boxplot](https://user-images.githubusercontent.com/94148420/221440720-0e1061eb-80f3-460e-a304-9b5fd6b3c211.png)

#### <ins>Voluntary Non-Profit Religious Patient Survey Star Rating Statistical Description</ins>

![vol_np_rel_ps_sr_desc](https://user-images.githubusercontent.com/94148420/221440782-77889b0c-e383-484a-9082-53f303e2ea7b.png)

#### <ins>Voluntary Non-Profit Religious Patient Survey Star Rating Boxplot</ins>

![vol_np_rel_ps_sr_boxplot](https://user-images.githubusercontent.com/94148420/221440876-9d76fecf-ace4-48f1-9e31-c41122b45f9a.png)

#### <ins>Voluntary Non-Profit Other Patient Survey Star Rating Statistical Description</ins>

![vol_np_other_ps_sr_desc](https://user-images.githubusercontent.com/94148420/221440960-34f7e10e-1d48-48af-82ab-9d05973058b2.png)

#### <ins>Voluntary Non-Profit Other Patient Survey Star Rating Boxplot</ins>

![vol_np_other_ps_sr_boxplot](https://user-images.githubusercontent.com/94148420/221441022-f318c592-c7c8-4161-b179-f0054328a4ad.png)

#### <ins>Voluntary Non-Profit Private Patient Survey Star Rating Statistical Description</ins>

![vol_np_private_ps_sr_desc](https://user-images.githubusercontent.com/94148420/221441088-0d098864-702d-4c08-9ea6-3e467e44555b.png)

#### <ins>Voluntary Non-Profit Private Patient Survey Star Rating Boxplot</ins>

![vol_np_private_ps_sr_boxplot](https://user-images.githubusercontent.com/94148420/221441152-2b46c0cd-13e8-4b39-9289-36e13fc8f883.png)

**Back to [Quick Links](#quick-links)**

### Patient Survey Additional Analysis - Willingness to Recommend

#### <ins>National Willingness to Recommend Statistical Description</ins>

![nat_wtr_desc](https://user-images.githubusercontent.com/94148420/221441527-4c819077-cbcc-45f5-b494-eebed6ac258d.png)

#### <ins>National Willingness to Recommend Boxplot</ins>

![nat_wtr_boxplot](https://user-images.githubusercontent.com/94148420/221441460-aba763e3-d319-4288-982d-eacb2d9a984e.png)

#### <ins>State Willingness to Recommend Statistical Description (AK through MS)</ins>

![state_wtr_desc_1](https://user-images.githubusercontent.com/94148420/221441629-62239a5f-65a8-4aa1-a03d-ca09052ec40d.png)

#### <ins>State Willingness to Recommend Statistical Description (MT through WY)</ins>

![state_wtr_desc_2](https://user-images.githubusercontent.com/94148420/221441739-fee9b2ec-13b8-403c-af58-1a4837041890.png)

#### <ins>State Willingness to Recommend Boxplot</ins>

![state_wtr_boxplot_1](https://user-images.githubusercontent.com/94148420/221441958-b8131089-0046-4fd7-b5b9-e6a68560310f.png)

![state_wtr_boxplot_2](https://user-images.githubusercontent.com/94148420/221442030-6da97398-37c7-4844-b9c5-6185b2077cdc.png)

#### <ins>Type of Ownership Willingness to Recommend Statistical Description</ins>

![too_wtr_desc](https://user-images.githubusercontent.com/94148420/221442182-e4735f99-d149-4e41-9793-5523465ebc8f.png)

#### <ins>Type of Ownership Willingness to Recommend Boxplot</ins>

![too_wtr_boxplot](https://user-images.githubusercontent.com/94148420/221442147-406bbc1b-9306-48f2-8318-92ee93c20afd.png)

**Back to [Quick Links](#quick-links)**

### Patient Survey Additional Analysis - Response Rate

#### <ins>National Response Rate Statistical Description</ins>

![nat_rr_desc](https://user-images.githubusercontent.com/94148420/221442262-2b72ea97-c52f-4661-89e0-df5548412b51.png)

#### <ins>National Response Rate Boxplot</ins>

![nat_rr_boxplot](https://user-images.githubusercontent.com/94148420/221442303-6fd11508-302a-4c8c-bdb4-3e5003c69c47.png)

#### <ins>State Response Rate Statistical Description (AK through MS)</ins>

![state_rr_desc_1](https://user-images.githubusercontent.com/94148420/221442378-34faa580-f625-40fe-b99a-f0dfbe23c1c8.png)

#### <ins>State Response Rate Statistical Description (MT through WY)</ins>

![state_rr_desc_2](https://user-images.githubusercontent.com/94148420/221442478-29a5d22c-8a56-4445-a09c-e50ed17f331f.png)

#### <ins>State Response Rate Boxplot</ins>

![state_rr_boxplot_1](https://user-images.githubusercontent.com/94148420/221442552-ef858b02-2b3b-44c1-9454-bd2e9e039446.png)

![state_rr_boxplot_2](https://user-images.githubusercontent.com/94148420/221442601-9d1ec9a5-f1d4-45da-b1a6-63ac4f8c2911.png)

#### <ins>Type of Ownership Response Rate Statistical Description</ins>

![too_rr_desc](https://user-images.githubusercontent.com/94148420/221442657-ceac67ef-200e-4c0d-b1d9-9ce938257ed2.png)

#### <ins>Type of Ownership Response Rate Boxplot</ins>

![too_rr_boxplot](https://user-images.githubusercontent.com/94148420/221442759-921ba799-50e2-4678-9e76-cafc7bbdf945.png)

**Back to [Quick Links](#quick-links)**

## Summary

This debut of the CMS Home Health Compare Refresh Analysis is a comprehensive analysis and data story of the **CMS January 2023 Home Health Compare Refresh**.  Home Health Quality Star Rating, Patient Survey Star Rating, and additional measures publicly reported on Home Health Compare were analyzed and described at a high level.

### Recommendations for Future Analysis

* One goal of this analysis was to exclusively use Python.  Future considerations could include other data tools, including Tableau.
* There are many outliers in the data.  Future consideration could include taking a deeper dive into these outliers.
* Look for geographical differences in Quality and Patient Survey Star Rating outcomes.

### What Would Have Done Differently

* Increase efficiency with code writing
*
**Back to [Quick Links](#quick-links)**

Thank you for taking the time to review this **CMS January 2023 Home Health Compare Refresh Analysis**.  Please provide any feedback or suggestions for future analysis.

John Beauchamp

e-mail: jbeauchamppt@gmail.com

LinkedIn:  https://www.linkedin.com/in/johnbeauchamppt/
