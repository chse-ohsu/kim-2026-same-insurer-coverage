### Overview  
This repository contains select code used to identify same Medicare/Medicaid insurer status among dual-eligible individuals who use LTSS, as published in  

Kim H, Senders A, Cheekati M, et al. Same-Insurer Coverage Associated With Fewer Hospitalizations, More Outpatient Visits Among Dual-Eligible Enrollees. Health Aff (Millwood). 2026;45(9):1010-1017. doi:10.1377/hlthaff.2025.01411

Same-insurer status is defined as a dual eligible enrollee having a Medicare Advantage (MA) and Medicaid managed care plan owned by the same parent organization. Dual-eligible enrollees in MA have one MA plan but may have several Medicaid plans covering medical (MCO), behavioral health (BHO), and/or long-term services and supports (MLTSS), each of which may be owned by a different parent organization. This code provides the broad steps needed to assign same insurer status at the enrollee-level, including how to:  

- Identify each MA plan's parent organization  
- Identify each Medicaid plan's parent organization  
- For each enrollee, flag MA/Medicaid plan pairs that share a parent and assign an integration category based on which Medicaid plan type is owned by the same parent (e.g., "integrated with MCO," "integrated with MCO + MLTSS," "not integrated")  

We also provide select code to run staggered DiD regressions for the following outcomes:  

- Any emergency department visit  
- Any all-cause hospitalization  
- Number of outpatient visits     
- Any avoidable hospitalization  
- Among all-cause hospitalizations  
  - Length-of-stay  
  - Any 30-day readmission  
  - Discharge to home (vs. post-acute care)  
  
### Data availability  
This analysis uses CMS Research Identifiable Files (RIFs) obtained under a Data Use Agreement with CMS. The data cannot be redistributed and are not included in this repository. Researchers may [request RIF access through CMS](https://www.cms.gov/data-research/cms-data/data-available-researchers). The following source files were used in this study:  

- 2018-2021 [Medicare Master Beneficiary Summary File Base A/B/C/D](https://resdac.org/cms-data/files/mbsf-base)  
- 2018-2021 [Medicare Plan Characteristics File](https://resdac.org/cms-data/files/plan-characteristics) 
- 2018-2021 [Medicare Encounter Inpatient](https://resdac.org/cms-data/files/ip-encounter)
- 2018-2021 [Medicare Encounter Outpatient](https://resdac.org/cms-data/files/op-encounter)
- 2018-2021 [Medicare Encounter Carrier](https://resdac.org/cms-data/files/carrier-encounter)
- 2018-2021 [Medicare Encounter Skilled Nursing Facility](https://resdac.org/cms-data/files/snf-encounter)
- 2018-2021 [Medicare Encounter Home Health Agency](https://resdac.org/cms-data/files/hha-encounter)
- 2018-2021 [Original Medicare (Fee-for-Service) Hospice](https://resdac.org/cms-data/files/hospice-ffs)
- 2018-2021 [T-MSIS Analytic File Demographic and Eligibility](https://resdac.org/cms-data/files/taf-de)  
- 2018-2021 [T-MSIS Analytic File Other Services](https://resdac.org/cms-data/files/taf-ot)  
- 2018-2021 [T-MSIS Analytic File Inpatient](https://resdac.org/cms-data/files/taf-ip)  
- 2018-2021 [T-MSIS Analytic File Long Term Care](https://resdac.org/cms-data/files/taf-lt)  
- 2018-2021 CHSE Managed Care Organization Crosswalks (see below)  

###  Scope and intended use
This is not a turnkey pipeline. It is excerpted from a larger analytic workflow and omits data acquisition, cohort construction, cleaning, and validation steps. It assumes the user has already built an analytic file at the enrollee-month-Medicaid plan level (including Medicare plan information). Users will need to adapt any file paths, variable names, and data structures to their own environment.  

### CHSE MCO Crosswalk   
This study used an early version of a publicly available managed care crosswalk published by the Center for Health Systems Effectiveness at Oregon Health & Science University. This repo includes the version used to produce the published estimates; later versions reflect subsequent corrections and updates and will not reproduce results exactly. Interested parties are encouraged to [download the most recent version from GitHub](https://github.com/chse-ohsu/taf.functions/tree/main/Managed_Care_Crosswalks).  
  
### Included scripts  
This repo includes the following scripts:  
  
- select_code_to_identify_same_insurer_status.Rmd  
- select_code_to_identify_ed_visits.Rmd  
- select_code_to_identify_all-cause_hospitalizations.Rmd  
- select_code_to_identify_avoidable_hospitalizations.Rmd  
- select_code_to_identify_outpatient_visits.Rmd  
- select_code_to_run_regressions.Rmd    
  
### Included look-up tables  
This repo includes the following look-up tables & supplementary files:  

- mco_crosswalk_clean_20260306.csv  
- pqi_lookup.csv  

### Questions
Contact: Angela Senders, ND, MCR, PhD senders@ohsu.edu  

