<h1 align="center">
    <img alt="MACHINE LEARNING - REGRESSÃO - BASE DE SATISFAÇÃO DE VIDA (LIFESAT) - PIB PER CAPITA vs SATISFAÇÃO DE VIDA" title="#ML_REGRESSION_LIFE_SAT" src="./assets/banner.png" />
</h1>

<h4 align="center"> 
	🚧 MACHINE LEARNING - REGRESSÃO - BASE DE SATISFAÇÃO DE VIDA (LIFESAT) - PIB PER CAPITA vs SATISFAÇÃO DE VIDA - 1.0 🚀 em desenvolvimento... 🚧
</h4>

<p align="center">
  <img alt="GitHub language count" src="https://img.shields.io/github/languages/count/emersonrafaels/ml_regression_life_sat?color=%2304D361">

  <img alt="Repository size" src="https://img.shields.io/github/repo-size/emersonrafaels/ml_regression_life_sat">

  	
  <a href="https://www.linkedin.com/in/emerson-rafael/">
    <img alt="Siga no Linkedin" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white">
  </a>
	
  
  <a href="https://github.com/emersonrafaels/ml_regression_life_sat/commits/main">
    <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/emersonrafaels/ml_classification_credit_dataset">
  </a>

  <img alt="License" src="https://img.shields.io/badge/license-MIT-brightgreen">
   <a href="https://github.com/emersonrafaels/ml_regression_life_sat/stargazers">
    <img alt="Stargazers" src="https://img.shields.io/github/stars/emersonrafaels/ml_regression_life_sat?style=social">
  </a>
</p>


## 💻 About the project

📦 **MACHINE LEARNING - REGRESSÃO - BASE DE SATISFAÇÃO DE VIDA (LIFESAT) - PIB PER CAPITA vs SATISFAÇÃO DE VIDA** é um projeto de machine learning para obtenção da satisfação de vida de um país a partir dos dados de PIB.

Or in english:

📦 **MACHINE LEARNING - Regression - Life satisfaction data (LIFESAT) - GDP PER CAPITA vs LIFE SATISFACTION** is a machine learning project for get life satisfaction from a country using it GDP PER CAPITA.


# Life satisfaction and GDP per capita
## Life satisfaction
### Source
This dataset was obtained from the OECD's website at: http://stats.oecd.org/index.aspx?DataSetCode=BLI

### Data description

    Int64Index: 3292 entries, 0 to 3291
    Data columns (total 17 columns):
    ﻿"LOCATION"              3292 non-null object
    Country                  3292 non-null object
    INDICATOR                3292 non-null object
    Indicator                3292 non-null object
    MEASURE                  3292 non-null object
    Measure                  3292 non-null object
    INEQUALITY               3292 non-null object
    Inequality               3292 non-null object
    Unit Code                3292 non-null object
    Unit                     3292 non-null object
    PowerCode Code           3292 non-null int64
    PowerCode                3292 non-null object
    Reference Period Code    0 non-null float64
    Reference Period         0 non-null float64
    Value                    3292 non-null float64
    Flag Codes               1120 non-null object
    Flags                    1120 non-null object
    dtypes: float64(3), int64(1), object(13)
    memory usage: 462.9+ KB

### Example usage using python Pandas

    >>> life_sat = pd.read_csv("oecd_bli_2015.csv", thousands=',')
    
    >>> life_sat_total = life_sat[life_sat["INEQUALITY"]=="TOT"]
    
    >>> life_sat_total = life_sat_total.pivot(index="Country", columns="Indicator", values="Value")
    
    >>> life_sat_total.info()
    <class 'pandas.core.frame.DataFrame'>
    Index: 37 entries, Australia to United States
    Data columns (total 24 columns):
    Air pollution                                37 non-null float64
    Assault rate                                 37 non-null float64
    Consultation on rule-making                  37 non-null float64
    Dwellings without basic facilities           37 non-null float64
    Educational attainment                       37 non-null float64
    Employees working very long hours            37 non-null float64
    Employment rate                              37 non-null float64
    Homicide rate                                37 non-null float64
    Household net adjusted disposable income     37 non-null float64
    Household net financial wealth               37 non-null float64
    Housing expenditure                          37 non-null float64
    Job security                                 37 non-null float64
    Life expectancy                              37 non-null float64
    Life satisfaction                            37 non-null float64
    Long-term unemployment rate                  37 non-null float64
    Personal earnings                            37 non-null float64
    Quality of support network                   37 non-null float64
    Rooms per person                             37 non-null float64
    Self-reported health                         37 non-null float64
    Student skills                               37 non-null float64
    Time devoted to leisure and personal care    37 non-null float64
    Voter turnout                                37 non-null float64
    Water quality                                37 non-null float64
    Years in education                           37 non-null float64
    dtypes: float64(24)
    memory usage: 7.2+ KB

## GDP per capita
### Source
Dataset obtained from the IMF's website at: http://goo.gl/j1MSKe

### Data description

    Int64Index: 190 entries, 0 to 189
    Data columns (total 7 columns):
    Country                          190 non-null object
    Subject Descriptor               189 non-null object
    Units                            189 non-null object
    Scale                            189 non-null object
    Country/Series-specific Notes    188 non-null object
    2015                             187 non-null float64
    Estimates Start After            188 non-null float64
    dtypes: float64(2), object(5)
    memory usage: 11.9+ KB

### Example usage using python Pandas

    >>> gdp_per_capita = pd.read_csv(
    ...     datapath+"gdp_per_capita.csv", thousands=',', delimiter='\t',
    ...     encoding='latin1', na_values="n/a", index_col="Country")
    ...
    >>> gdp_per_capita.rename(columns={"2015": "GDP per capita"}, inplace=True)

