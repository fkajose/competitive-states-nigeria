# competitive-states-nigeria

 Analysis of competitive states in Nigeria

This project was conducted for an article on Our Red Eagle about the most competitive states in Nigeria besides Lagos. The data used was compiled from the Nigerian Bureau of Statistics (NBS)

## Sources

1. [Computation of Human Development Indices for the UNDP Nigeria Human Development Report (2016)](/https://nigerianstat.gov.ng/elibrary/read/830/)
2. [BudgIT's 2022 State of States](/https://yourbudgit.com/wp-content/uploads/2022/10/2022-State-of-States-Report.pdf/)
3. [Selected Food Prices Watch (September 2022)](/https://nigerianstat.gov.ng/elibrary/read/1241247/)
4. [Labor Force Statistics: Unemployment and Underemployment Report (Q4 2020)](/https://nigerianstat.gov.ng/elibrary/read/1238/)
5. [Internally Generated Revenue At State Level (2019 - 2021)](/https://nigerianstat.gov.ng/elibrary/read/1241239/)
6. [Crime Statistics: Reported Offences by Type and State (2017)](/https://nigerianstat.gov.ng/elibrary/read/786/)
7. [Road Transport Data (Q3 & Q4 2021)](/https://nigerianstat.gov.ng/elibrary/read/1241145/)

## Methodology

Due to inconsistent availability of data, the metrics used were not all from the same year. 

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

### Score Calculations

I=IHDI;
Ig=IGR per Capita;
M=MPI;
L=Literacy Rate;
U=Unemployment Rate;
C=Crimes per 100000 persons;
A=Accidents per 100,000 persons;
F=Average Food Price;
```math
score = \frac{6I + 5\frac{Ig}{max(Ig)}) + 4(1-M) + 3(\frac{L}{100}) + 2(\frac{U}{100}) + (1-\frac{C}{max(C)}) + (1-\frac{A}{max(A)}) + (1-\frac{F}{max(F)})}{23}
```
