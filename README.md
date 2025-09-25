# Data_Mining


Analyzing Global Trends in Cervical Cancer Screening Programs
=======

- Cervical cancer is one of the most preventable cancers through effective screening programs.
- The dataset consists of 3 different screening methods, and I tried to compare their effectiveness across countries.
- The project aims to analyze cervical cancer screening programs for women aged 30-49 in the year 2019 using WHO data.

# Research Question

**Research Question: 
What are the most commonly used screening methods for cervical cancer, and how effective are they among women aged 30-49 across different countries?** 

**Dataset**
- Data Sources:
Prevalence of cervical cancer screening among women aged 30-49 (%).
Coverage of national cervical cancer screening programs (%).
Most widely used screening methods in national programs.
Mortality rates associated with cervical cancer.
Prevalence of cancer (Ratio per 100,000 people)
Incidence of cancer (Ratio per  100,000 people)
Disability adjusted life years (Number of years per 100,000 people)
Years lost with disability  (Number of years per 100,000 people)
Years lived with disability   (Number of years per 100,000 people)
Links to Sources (if relevant):
WHO, Global Health Data Repository

Link to data source:
[WHO, Global Health Data Repository](https://www.who.int/data/gho)
[Link to other data sources](https://vizhub.healthdata.org/gbd-results/)

---

## Data Preprocessing

- Ensured consistency of location_name in all datasets by mapping them to a common reference.
- Extracted unique “location_id” and “location_name” pairs from the mortality dataset to create a mapping/dictionary.
- Iterated through each dataset and compared location_id with the reference mapping.
- For each matched “location_id”, the corresponding “location_name” was updated in the respective dataset to ensure consistency.


---

## Data Preprocessing - Merging the datasets
- Cleaned all the datasets by removing columns with missing values.
- Filtered data to retain only 2019 entries.
- Removed redundant columns.
- Renamed some columns for clarity (e.g., to indicate they belong to the coverage dataset).
- Converted some string values into numerical values where required.
- Exported each of the cleaned datasets to a CSV file.

  ---

## Data Preprocessing - Cleaning the data
- Merged_df1: Merged datasets (coverage, prevalence, screening) based on location.
- Merged_df2: Merged the rest of the datasets based on location and age_name because those datasets have 4 categories of ages (30-34, 35-39, 40-44, and 45-49 years).
- Finally merged the two dataframes: merged_df1 and merged_df2 on basis of location.

---

## Data Preprocessing - Standardization
- Mortality, Coverage, Prevalence of screened patients dataset values are in percentage.
- Prevalence of cancer, Incidence of cancer dataset values are in ratio per 100,000 people.
- Disability adjusted life years, Years lost with disability, Years lived with disability  dataset values are in number of years per 100,000 people.
- MinMax standardization was then used to bring all the data values into the 0-1 range. 

---

## Methodology
- Clustering:
Used 3 clustering techniques to group countries based on the effectiveness of their screening methods.
1. Agglomerative Clustering
2. K-Means
3. DBScan
- The goal is to find patterns that highlight successful screening programs and those that need improvement.
[Visual inspection , HPV test , PAP smear](https://github.com/ZarinTasnimBiash/Data_Mining/blob/main/images/Methodology.png)


## Methodology: Agglomerative Clustering

- Generated the dendrogram on the right after performing agglomerative clustering.
- A deduction is then done that the clustering numbers can be set to 4 according to the dendrogram to try out the K-Means clustering method as well.
[Dendogram for Agglomerative Clustering](https://github.com/ZarinTasnimBiash/Data_Mining/blob/main/images/Agglomerative_Clustering.png)
---

## Results

- Apply K-Means with k = 4 on the dataset.
- Plot the dataset based on selected attributes to capture their distribution.
- [K-Means Figure 1](https://github.com/ZarinTasnimBiash/Data_Mining/blob/main/images/KMeans1.png)
- [K-Means Figure 2](https://github.com/ZarinTasnimBiash/Data_Mining/blob/main/images/KMeans2.png)
- [K-Means Figure 3](https://github.com/ZarinTasnimBiash/Data_Mining/blob/main/images/KMeans3.png)
- [K-Means Figure 4](https://github.com/ZarinTasnimBiash/Data_Mining/blob/main/images/KMeans4.png)

## DBScan

- Final parameters giving clear clusters:
	Epsilon = 0.15
	Min_samples = 5
- [DBScan Figure 1](https://github.com/ZarinTasnimBiash/Data_Mining/blob/main/images/DBScan1.png)
- [DBScan Figure 2](https://github.com/ZarinTasnimBiash/Data_Mining/blob/main/images/DBScan3.png)

## Conclusion
- The widely available data related to cervical cancer is quite large and detailed.
- The least effective method was as expected the visual inspection method. On the other hand, the most effective and widely used proved to be the PAP smear method.
- IIt was difficult to interpret the outcomes of our clustering algorithms.











