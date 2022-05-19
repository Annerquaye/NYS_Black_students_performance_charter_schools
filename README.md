## Black students' performance in NYC Charter Schools
Data from this project came from the [New York State Department of Education] (data.nysed.gov). The files accessed for this analysis were the

``` sh 2020-2021 Enrollment Database ```

This database contains school, district, county, and statewide enrollment by grade, race/ethnicity, gender, and other groups.


```sh 2020-2021 Graduation Rate Database ```
This database contains annual graduation, and dropout data for the state as well as by county, Need to Resource Capacity group, district, public school and charter school. Annual graduation data is included for the current four-year cohort (June and August graduates), five-year June and August, and six-year June and August cohorts.


The extensions of both files were accdb which could be opened using MS Access. 

```sh ACC HS Chronic Absenteeism --- Is the xlsx file that shows absenteeism data as extracted from Enrollment Database

```sh ACC HS Graduation Rate -- Is the xlsx file extracted from the graduation data as listed above.
```
#### Merging and cleaning

In order to be able to juxtapose the impact of absenteeism on graduation rate, the two xlsx files were merged on `Institution ID` which is unique for schools as captured in both data files.

As the merged file contains data on schools from all of New York City, to differentiate between charter and public schools we refer to the data documentation `SRC2021ReadMe_GroupI`.

The documentation shows that charter schools have `'86'` in their `ENTITY_CD` column -- which is 12-digit code for public schools statewide, by county, by N/RC group, for public school districts, public schools, and charter schools.


After drilling down to charter and non-charter schools, more cleaning needs to be done. Each row in the data shows a demographic data such as `Black African/American`, `Hispanics`, etc and their corressponding data showing enrollment, absent rate, grad rate etc.


In  cleaning the data, we opted to use `All Students` so that a row becomes a single school with other attributes such as `absent rate`, `grad rate`, `economically disadvantaged`, etc computed at the school level.

Of importance to the analysis is `Absent Rate`, `Grad Rate`, `Enrollment` and `Economicaly Disadvantaged`. So typically, a single row of data will show a school, its total enrollment, the absent rate of the overall students population, the % which are blacks, blacks' graduation rate, the absent rate of black student etc.

The clean data is now rady to be used for regression analysis to find out how blacks' students grad rate could be explained by factors such as poverty, absent rate etc.

The regressions conducted indicated that black students' graduation rate are higher in charter schools as against non charter when you control for absent rate and povert rates.






