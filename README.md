# Pewlett-Hackard-Analysis

# 1. Overview of the Analysis

## Overview
The purpose of this analysis was to project the number of employees who might be retirining in the near future at a large company called Pewlett-Hackard. This will help the company estimate the number of retirment packages they might have to offer, along with identifying which positions will need to be filled. Due to the company's size, a sudden surge in retiring employees could leave huge portions of their workforce vacant. Conducting this analysis now helps Pewlett-Hackard plan for the future and protect themselves from sudden shocks to their business. 

## Methodology
To conduct the analysis, we were provided six CSV files containing all necessary information. It was determine SQL would be a more efficient way to work through the data. The CSV files were reviewed to identify the primary keys, data types, and foreign keys. An entity relatioship diagram was created to visualize the relationships between the files. From there, the files were imported into a PostgreSQL database, where we conducted our analysis. The analysis will be covered in more detail in section 2. Below is a copy of the ERD that was created. 

![EDF](https://github.com/jbalooshie/Pewlett-Hackard-Analysis/blob/main/EmployeeDB.png)

# 2. Results

To determine the requirement criteria, we combined several datasets and then filtered them to only show employees born between 1952-1955. From there, the combined dataset was organized by job title, and the potential retirees in each title were totaled. A second table was constructed from the original six datasets to identify employees born in the year 1965 who are stillwith Pewlett-Hackard. These employees are potential candidates for a mentorship program, where a retiring employee trains them to fill the position they are leaving. 

## Retirement by title

- The most urgent item Pewlett-Hackard needs to address is the possibility of almost 45,000 engineers retiring. Right now they have 29,414 employees with the title of Senior Engineer who meet the criteria for a near-future retirement. There are also 14,222 employees with the title of Engineer who also meet the criteria. A plan needs to be put into place to attract middle and senior level engineers to fill these roles. Promoting internally is an option, but that will be tough given the number of middle level engineers potentially retiring. 

- Middle manaagement will be unaffected by possible retirement. There are only two employees with the title of manager who meet the criteria for potential retirement. Pelett-Hackard can look to existing managers to potentially fill Senior Leadership positions that might open up. There are 28,254 employees with the title of Senior Staff who meet the retirement criteria. 

## Mentorship Possibilities

- The mentorship program would not be able to fill all of the positions potentially opening up. Under the current criteria, there are only 1,549 employees who could be mentored. With 14,222 mid level engineering positions opening up, this would be insufficient for just that one role, let alone across the whole company.  

- Answer 2

# 3. Summary

## Questions
- How many roles will need to be filled as the "silver tsunami" begins to make an impact?
  Pewlett-Hackard will need to fill 90,398 roles over the course of the "Silver Tsunami". 

- Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?
There are enough qualified, retirement-ready employees ready to mentor the next generation of Pewlett-Hackard employees. 98% of the employees retiring are senior or mid-level based on their titels. However, the pool of employees eligible for mentorship is far too small to fill all the positions that would be vacated. 

## Additional Insight
 - Widening the range of employees eligible for the mentorship program would help find more internal options to fill positions. Right now it is restricted to employees born in the year 1965. The seems arbitrary. Retirement for a lot of employees typically happens around a certain age, but promotions/mentoring opportunities should not be exclusive to individuals born in 1965. If the pool is still insufficient, then an agressive external hiring strategy should be considered. We can modify the existing code to list all employees from 1965-1970. The updated code would be as follows:
 `WHERE de.to_date = ('9999-01-01') 
	  AND (e.birth_date BETWEEN '1965-01-01' AND '1970-12-31')`
    
- 
