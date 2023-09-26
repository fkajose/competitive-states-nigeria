# competitive-states-nigeria

 Analysis of competitive states in Nigeria

This project was conducted for [an article](https://redeagleng.com/economy/lagos-nigeria-states/) on [Our Red Eagle](https://redeagleng.com/) about the most competitive states in Nigeria besides Lagos. A competitive state is one that enables business environments, possesses resources and human capital, has good infrastructure, and is generally safe for business with a high consumer market. Competitive states are good at attracting investment and creating jobs that help reduce poverty and unemployment.

## Sources

1. [Computation of Human Development Indices for the UNDP Nigeria Human Development Report (2016)](https://nigerianstat.gov.ng/elibrary/read/830/)
2. [BudgIT's 2022 State of States](https://yourbudgit.com/wp-content/uploads/2022/10/2022-State-of-States-Report.pdf/)
3. [Selected Food Prices Watch (September 2022)](https://nigerianstat.gov.ng/elibrary/read/1241247/)
4. [Labor Force Statistics: Unemployment and Underemployment Report (Q4 2020)](https://nigerianstat.gov.ng/elibrary/read/1238/)
5. [Internally Generated Revenue At State Level (2019 - 2021)](https://nigerianstat.gov.ng/elibrary/read/1241239/)
6. [Crime Statistics: Reported Offences by Type and State (2017)](https://nigerianstat.gov.ng/elibrary/read/786/)
7. [Road Transport Data (Q3 & Q4 2021)](https://nigerianstat.gov.ng/elibrary/read/1241145/)

## Methodology

In defining my metrics, it was important to factor in economic activity, infrastructure, and security. The table below shows the metrics chosen and their weights. 

### Metrics Selection

 |Metric|Description|Range|Weight|
 |-------------------|-------------------|:----------------:|----------------|
 |IHDI|**Income-Adjusted Human Development Index.** A composite index to measure the quality of life, level of knowledge, and standard of living of a state while accounting for the inequalities within the state. The higher this metric the better.|0-1|6|
 |IGR per Capita | "**Internally Generated Revenue.** The internally generated revenues obtained within the state, majorly from taxes as reported by the National Bureau of Statistics. The higher this metric, the better."|0-1|5|
 |MPI|"**Multidimensional Poverty Index.** Measures the share of the population that is multi-dimensionally poor, adjusted by the intensity of deprivation. It accounts for inadequate amenities, health, nutrition, education, housing conditions, and a lack of job. Lower is better."|0-1|4|
 |Literacy|**Literacy rate.** The proportion of the adult population aged 15 years and over which is literate, expressed as a percentage of the corresponding population. Higher is better.|0-100|3|
 |Unemployment|"**Unemployment Rate.** The proportion of people (aged 15-64) who are looking for and are available for work, but are unable to secure a job. Lower is better."|0-100|2|
 |Avg Food Item Price|**Average Food Item Price.** The average price of selected food items in Naira as curated by the National Bureau of Statistics for the state in September 2022. Lower is better.|None|1|
 |Accidents/100k persons|**Accidents per 100,000 persons.** An indirect measure of infrastructure by accounting the number of recorded road traffic accidents per 100,000 persons in state. Lower is better.|None|1|
 |Crimes/100k persons|**Crimes per 100,000 persons.** A measure of how safe the state is, i.e., the number of reported crimes per 100,000 persons in state. Lower is better.|None|1|

### Score Calculation

A weighted score was created to help normalise the values and rank the states on a scale of 0-1. 

$I$=IHDI;
$Ig$=IGR per Capita;
$M$=MPI;
$L$=Literacy Rate;
$U$=Unemployment Rate;
$C$=Crimes per 100000 persons;
$A$=Accidents per 100,000 persons;
$F$=Average Food Price;
$$score = \frac{6I + 5\frac{Ig}{Ig_{max}} + 4(1-M) + 3\frac{L}{100} + 2\frac{U}{100} + (1-\frac{C}{C_{max}}) + (1-\frac{A}{A_{max}}) + (1-\frac{F}{F_{max}})}{23}$$

### Results

Lagos was used as a benchmark upon which all other states were judged. Radar charts displaying key metrics helped accomplish this, with the top 10 states besides Lagos being:

1. Federal Capital Territory (not a state)
2. Ogun State
3. Osun State
4. Delta State
5. Rivers State
6. Ondo State
7. Ekiti State
8. Kwara State
9. Enugu State
10. Cross River State
