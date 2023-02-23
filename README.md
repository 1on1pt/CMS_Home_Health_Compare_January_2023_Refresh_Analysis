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




