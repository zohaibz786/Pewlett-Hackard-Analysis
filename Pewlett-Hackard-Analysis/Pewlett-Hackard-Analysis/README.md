# Pewlett-Hackard-Analysis

#### *Employee database analysis on retiring employees using SQL, PostgreSqL and pgAdmin*

## Overview
The goal of this project was to play the role of an RH Analyst for Pewlett Hackard and create concrete data about
the employees retiring in near future years and as well as determining the number of positions that is expected to
to be filled.
This data creation and analysis, was a key to create a list of all the employees eligibile for a retirement package as well as a list of the number of jobs by title that will be open after the retirement of these employees.

## Results
- After creating the unique_titles table by joining the employees and titles tables, filtering them by date of birth and date hired, removing duplicates, and ordering the data points by date hired there are **72458 employees retiring** as per the above criterion.

![ unique retirement titles](/Pewlett-Hackard-Analysis/screenshots/unique_titles.png)


- Out of those employees leaving, there are 25,916 Senior Engineers, 24,926 Senior Staff, 9,285 Engineers, 7,636 Staff, 3,603 Technique Leaders, 1,090 Assistant Engineers, and 2 Managers. 

![retiring titles](/Pewlett-Hackard-Analysis/screenshots/retiring_titles.png)


- Created the mentorship_eligibility table by joining the employees, department employees, and titles tables. In this case, the criterion for the join was that the employees were born in 1965 and that they were currently working at PH, in order for them to apply to the retiring/mentorship package. There were 1,549 employees eligible

![mentorship eligibilty](/Pewlett-Hackard-Analysis/screenshots/mentorship_eligibilty.png)

- Out of those eligible employees, there are 569 Senior Staff, 501 Engineers, 169 Senior Engineers, 155 staff, 78 Assistant Engineers and 77 Technique Leaders.

![eligible titles](/Pewlett-Hackard-Analysis/screenshots/eligible_titles.png)

note : the above table was created using this query:

```
SELECT COUNT(me.emp_no), me.title
FROM mentorship_eligibility as me
GROUP BY title
ORDER BY COUNT(title) DESC;

```
the csv file for this table can be found inside the 'Data' directory.







