# Phase 2 Project

**Author**: [Nat Berryman](https://github.com/natberr)

## Project Overview

The purpose of this regression model is to predict the house prices in King County by analysing the King County House Sales dataset.

### Business Problem

How can we predict the house price sales in King County?

In order to solve this problem, I intended to answer the below questions:
1. Does location impact sale price?
2. Does the size of the house impact sale price?
3. Does quality of the house impact sale price?

### The Data

This project uses the King County House Sales dataset, which can be found in  `kc_house_data.csv` in the data folder in this repo. The description of the column names can be found in `column_names.md` in the same folder.

**Data Cleaning**
- Dropped unnecessary data
- Replaced or removed null values
- Narrowed data to only included houses with <6 bedrooms
- Using the empirical formula I removed outliers
- Addressed multicollinearity
- Split data set between continuous and categorical data
- Binned Grade into Low, Average and High


### Exploratory Data Analysis

**Key Features include:**
Bathrooms
Square Foot living space
Grade
Latitude
Square Foot Above
Square Foot Living 15 (neighbors)

**Notes:** 
Zip code excluded as data-type is a string
Latitude correlates with price more than Longitude

I then created price vs zip code graph to explore price distribution across zip codes and then plotted to a heatmap.
Using these visualization I created  a new variable – **km_from_cbd**

Used mean normalization to standardise the data
Sqft living, sqft lot, sqft above, sqft living 15, sqft lot 15 appear good
Km from CBD is negatively skewed

Used KDE plot and joint plot to explore data

### Models

**Model 1**
- Used selected features identified in repo.
- R^ 0.527, however multiple variables had negative R^
- Residual graph was good

**Model 2**
- Used fewer variable in features (kept bathrooms, sqft living, sqft living15 and high grade)
- R^ 0.413
- Residual graph was good

**Model 3**
- Selected features included all variables with positive R^
- R^ 0.524
- Residual graph was good

### Conclusions

- I determined Model 3 was the must accurate model by using all features with postive R^ and removing variables with negative R^.
- Selected features all statistically significant with p-value <0.05
- sqft living15 coef – 0.2791
- sqft living coef – 0.3956
- distance from CBD coef - 0.3434
- bathrooms coef – 0.0645
- high grade rating coef– 0.4590
- These Coef figures mean for unit increase in any one of these variables there was in increase in price by ~0.3 units.

### For More Information

Please review the full analysis in [my Jupyter Notebook](http://localhost:8888/notebooks/Desktop/AcademyXI/ProjectTwo/dsc-phase-2-project/Project_Two/kc_house_price_regression_modelling.ipynb) or my [presentation pack](http://localhost:8888/files/Desktop/AcademyXI/ProjectTwo/dsc-phase-2-project/Project_Two/Regression%20Modelling%20Presentation.pdf).

For any additional questions, please contact **Nat Berryman** - nathaniel.berryman@gmail.com

### Repository Structure

```
├── images
├── data
├── regression modelling presentation.pdf
├── kc_house_price_regression_modelling.ipynb
└── README.md
```