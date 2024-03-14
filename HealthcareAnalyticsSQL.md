#Better Healthcare Through Data

In my time as a physical therapist, I’ve worked in the hospital setting and have first-hand experience working in the delicate balance of providing high quality patient care while considering appropriate health care utilization and its related costs. In this project I’m excited to demonstrate my shift from a front-line clinician trying to find health care efficiencies one patient at a time to working as a healthcare data analyst finding more impactful ways to improve patient outcomes.
In this analysis I’ve used SQL to explore demographic and hospital admission data for more than 2000 diabetic patients. The data used for this analysis was collected from 130 hospitals over a 10-year period and includes a multitude of data including hospital admission type, length of stay, treatments administered, and patient readmission outcomes. The data used in this analysis can be found here. 
This analysis focuses primarily on the amount of time a patient stays in the hospital or length of stay, and the amount of care the patient receives during that hospital stay. Hospital length of stay and cost of care provided during a hospital admission are extremely important KPI’s in the hospital setting. Care utilization is directly tied to quality standards that affect hospital reimbursement rates. It's often the case that hospitals are reimbursed a flat rate based on a patient’s diagnoses and severity level. It’s in the interest of the hospital to meet patient care goals without unnecessary procedures or cost and to do so in as short of a time period as possible without sacrificing quality of care.
In this scenario I have been asked to complete the following tasks by a cross functional committee investigating utilization and hospital length of stay for patients with diabetes related diagnoses:
Create a basic length of stay distribution visualization and determine the average length of stay to ensure that most patients are staying fewer than 7 days in hospital.
Categorize utilization based on procedure count to see how number of procedures performed influences patient length of stay.
Determine if subconscious racial bias exists based on average number of procedures performed.
Identify the medical specialties that have higher care utilization rates per admission.
Pull records of all patients admitted through ED that spent below average time in hospital.
Provide a summary report of patients with high utilization based on number of medications administered and number of lab procedures performed.
 
The Analysis:
Length of stay distribution and calculating average length of stay:
While SQL is a less than ideal platform to create data visualizations in this case a basic histogram can be created to look at hospital length.


This histogram counts the number of patients for each length of stay to show length of stay distribution. It is confirmed for the committee that length of stay for most patients is less than 7 days.
Average length of stay for all the patients in this data set is calculated below:



These first two queries inform the committee that the distribution of patient length of stay is skewed less than 7 days and that the average patient length of stay is 4.4 days. The committee can use this information to initially understand the current state of this KPI to implement care strategies and reasonable goals to improve this metric
.
How does number of procedures per admission affect length of stay?
For this task it was requested that number of procedures be grouped into 3 categories to more easily understand and communicate the relationship between utilization and length of stay. To accomplish this in SQL a CASE statement is used to create utilization categories.
Procedure count can be classified as “Higher, “Lower,” and “Expected.” From a statistical standpoint “Expected” utilization includes admission that have a procedure count within one standard deviation of the average procedure count. Those admissions that fall outside of one standard deviation are classified as either “Higher” or “Lower” utilization.



The results show that number of procedures performed has an effect on length of stay. The relationship here may be that sicker patients need more care and wind up staying longer in hospital. That might not be the case, however, and further analysis of patient diagnoses and co-morbidities could be beneficial to understand the true relationship and if there is room to reduce utilization for patients in the "Higher" category without sacrificing patient outcomes.
 
Does subconscious racial bias play a role in amount of care received during admission?
To answer this question, it’s necessary to pull both demographic and health information simultaneously. Since the data is separated into 2 tables with one housing demographic data and the other housing admission and health data a JOIN is used to retrieve the needed information. This is possible because both tables use a unique and identical patient identification number that can be used to link individual patient demographic information to their respective health information. The presence of racial bias can be explored by comparing the average number of procedures performed grouped by race.



Our output shows that there does not seem to be any subconscious racial bias in the delivery of care as measured by average number of procedures performed per admission.

Are there medical specialties that have higher care utilization per admission?
To examine care utilization by medical specialty the average number of procedures performed by each medical specialty can be calculated. To finetune the results the committee asked to identify the medical specialties that have more frequent admissions (50 or greater) and an average procedure count of greater than 2.5 per admission. To filter the aggregated medical specialty information a HAVING statement is added to the query.



The results show that diabetic patients admitted by medical specialties related to various types of surgery, radiology, and cardiology have higher average procedure counts per admission. By identifying these specialties the committee can focus efforts on determining if this higher average procedure count is completely medically necessary or if there are care efficiencies to be had that could reduce the overall cost for these admissions.

Identify patients admitted through the emergency department (ED) that had shorter than average length of stay:
Identifying patients who had shorter length of stays can be a valuable tool for the committee to potentially identify best practices or treatment plans of care that result in or may reduce average time in hospital. To pull the correct information the query must pull all patients admitted through the ED and then filter that group to those patients that had lower than average length of stay. Since part of the Where clause criterion is a calculated value, a Common Table Expression (CTE) can be used to find the average length of stay to define that part of the filter. According to the data dictionary associated with this data set, patients with a hospital admission type “1” are those patient admitted from the ED and added to the WHERE clause.



This list of patients represents a subset of data that can be further analyzed to explore how and why these patients have lower than average lengths of stays.
 
Provide a summary report of 50 patient admissions with the highest number of medications administered and lab procedures performed:
In this final task the descriptive summary report requested by the committee is created in SQL using the CONCATENATE function. The committee has specifically asked for the patient identification number, race, number of medications, number of procedures, and readmission status for these high utilization patients. To efficiently create the desired list a CASE clause is nested in the CONCAT statement to create the proper verbiage based on readmission status of the patient pulled. A JOIN is required to pull specific demographic and health data from the 2 different tables. The data is sorted using an ORDER BY clause and only the top 50 patients are pulled by using LIMIT in this query.


Key insights presented to the committee:
Average hospital length of stay is skewed to less than 7 days with the current average time in hospital being 4.4 days.
Patients that have higher than expected procedure counts are the source of much longer than average lengths of stay.
Racial bias does not seem to be a factor in utilization and delivery of care.
Surgery, cardiology, and radiology tend to be the medical specialties with highest utilization rates
Identification of patients admitted through ED with lower length of stay and those top 50 patients that received higher utilization of medicine and lab procedures can be useful in further analysis to find health care efficiencies and improve length of stay and cost of care KPI's.

Thank you for taking the time to explore this analysis with me. I hope that you found it interesting and insightful. My name is Andrew, I'm an experienced health care clinician transitioning to a career in data analysis. I welcome and appreciate any feedback or suggestions you may have as I continue to sharpen my data skills.
