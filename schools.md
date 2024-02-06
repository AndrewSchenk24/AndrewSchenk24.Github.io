# Improving Schools in Massachuetts

As a child of a middle-school English and history teacher I have a great respect and understanding for the effort and dedication educators commit to their students and the transformative effect a good education can have on students’ lives. That understanding made me especially interested in the prospect of uncovering insights through the analysis of educational data from the Massachusetts Department of Education.

In this scenario I have been asked by the Massachusetts Department of Education to __examine their data to providing an overview of the Massachusetts school system__ to assist policy makers and educators in making data-based decisions that could improve the educational system. It has been specifically requested that __information be provided regarding the following tasks__:

* Examine the influence of **class size on college attendance rates**.
* __Identify schools with the lowest graduation rates__ that may be in need of assistance or potential increase in resource allocation.
* Determine **which school districts excel in 4th Grade math proficiency** to help identify teaching best practices.

<br/>

### The Results:

* Larger class size __DOES NOT__ result in lower college attendance rates.
* __Thirty-six high schools in Massachusetts have a graduation rate below 50%__ and can be identified as schools in most need of further analysis and assistance from the Department of Education.
* __Six school districts have achieved 4th grade math levels of proficient or better__ and can be studied to identify teaching best practices that can be applied to improve math scores state-wide.

<br/>

### Visualization in Tableau- The Analysis:

**The data used in this analysis** is real data taken from the Massachusetts Department of Education (DOE) website and compiled in a data set that **can be found** [**here**](https://www.kaggle.com/datasets/ndalziel/massachusetts-public-schools-data). This dataset contains 302 attributes on 1861 schools in the state of Massachusetts with **each row in the data set representing an individual school**.

This analysis was completed in Tableau to visualize the pertinent data points and to address the questions posed by the Department of Education. Tableau is a great tool to use for this analysis as the relatively complex information contained in the data set can be easily communicated to the non-technical stakeholders who have requested and are interested in understanding this data. 

Please explore the full **Massachusetts DOE overview dashboard** created for this project on my [**Tableau Public**](https://public.tableau.com/app/profile/andrew.schenk6747/viz/MassachusettsSchoolDistrictProject/MassSchoolsDashboard).

<br/>

#### Does Class Size Affect College Attendance:

To explore this relationship a scatter plot was created to map each schools’ average class size and what percentage of their students attend college after graduating. Each point on the scatter plot represents an individual school:

<br/>

<img src="images/Class Size Viz.png?raw=true"/>

<br/>

While it would seem logical that smaller class sizes might be beneficial and improve college attendance, the data did not show this. The scatter plot shows that **larger class size does not result in decreased college attendance**. In fact, there is a slight seemingly counterintuitive trend represented in the scatter plot that smaller class size results in decreased college attendance. 

To explore this relationship one step further I decided to incorporate color hue into the chart to identify schools that are more economically disadvantaged. Adding this layer of context revealed that some of the most **economically disadvantaged schools have small class sizes but also lower college attendance**. When these schools are pin-pointed we see that many of these schools are technology and or trade-focused schools. This could explain why fewer students continue on to college and instead likely continue their education or training in their chosen trade.

In general, however, **class size should not be the focus of the Department of Education**. Investing time and further resources to affect class size likely would not greatly improve college attendance rates.

<br/> 

#### Identify Low Performing Schools Based on Graduation Rate:

Low performing schools are identified in the following bar chart:

<br/>

<img src="images/GradRateViz.png?raw=true"/>

<br/>

This bar chart is helpful in identifying **36 high schools whose graduation rates are below 50%**. The Department of Education can use this insight to focus on these schools and their needs. Changes can then be made to improve these schools’ graduation rates perhaps by providing improved resources for their students such as additional tutoring programs for those students in need.

<br/>

#### 4th Grade Math Proficiency:

**Fourth grade math proficiency** was identified by the Secretary of Education as a **key indicator of a student’s future success**. As such I was tasked with identifying the highest performing school districts that, according to scores on a standardized math test, have achieved a 4th grade math level of proficient or better for 80% or more of their students.

<br/>

<img src="images/4th Grade Math Viz.png?raw=true"/>

<br/>

This area chart provides insight into math proficiency across all school districts and also identifies the **11 school districts that excel in 4th grade math**. With this information, the Department of Education can **identify teaching best practices** utilized by these 11 districts that potentially can be introduced to lower performing districts. By doing so the Department of Education can improve 4th grade math scores state-wide in an effort to improve their student’s future educational success.

<br/>

### Recommendations for the Massachusetts Department of Education:

*Class size should not be the focus of efforts to improve state-wide educational performance as class size does not greatly influence college attendance rates.
*Focus increased resources and analysis on the 36 schools with lower than 50% graduation rates. 
*Identify teaching best practices in the 11 schools districts that excel in 4th grade math and apply these practices state-wide to improve this key performance indicator and future educational success.
 
Thank you for reading this article and I hope you were able to explore the full dashboard on Tableau. As I am continuing to develop my skill in data analysis and data visualization, I would greatly appreciate any suggestions or comments you may have. Follow and connect with me for more data analysis to come!
