# CMS_Home_Health_Compare_January_2023_Refresh_Analysis
![CMS_Star_Rating](https://user-images.githubusercontent.com/94148420/214742856-a5c8407f-39a1-4977-aea8-f60cba9fe8de.png)

![Home_Health_Star_Ratings](https://user-images.githubusercontent.com/94148420/214742886-5c719324-640a-4d44-b395-67b8bc43b719.png)

Welcome to the debut of the CMS Home Health Compare Refresh Analysis.  This first edition will feature a comprehensive analysis of the **CMS January 2023 Home Health Compare Refresh**.

### Quick Links
* [Overview](#overview)


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

The focus of this analysis is to take a deeper dive into the **quality** and **patient survey** data that CMS has made publically available through its [Provider Data Catalog](https://data.cms.gov/provider-data/).  This data will be analyzed on three levels:

* National level
* State level
* Type of Ownership level

CMS updates Home Health Compare on a quarterly basis.  This analysis looks specifically at the data from the **January 2023 Care Compare Refresh**.

Care Compare provides tools, including **star ratings**, that summarize various current health care provider performance measures.  There are two types of home health star ratings:

1.  Quality of Patient Care Star Ratings
2.  Patient Survey Star Ratings

### Quality of Patient Care Star Ratings Overview

CMS states that all Medicare-certified home health agengencies (HHAs) may potentially receive a Quality of Patient Care Star Rating. HHAs must have data for at least 20 complete quality episodes for each measure to be reported on Home Health Care Compare. Completed episodes are paired with the start or resumption of care and end of care OASIS assessments. Episodes must have an end-of-care date within the 12-month reporting period, regardless of the start date. To have a Quality of Patient Care Star Rating computed, HHAs must have reported data for 5 of the 7 measures used in the Quality of Patient Care Star Ratings calculation. 

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

## Quality Star Rating Analysis
