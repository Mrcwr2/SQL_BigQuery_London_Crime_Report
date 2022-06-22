# SQL Code

## sum_major_catergory_crimes:

    SELECT
    
    major_category, # Selecting the major category of this dataframe and showing the numbers by value columns
    
    SUM(value) AS num_crimes
    
    FROM
    
    `bigquery-public-data.london_crime.crime_by_lsoa`
    
    GROUP BY
    
    major_category # Grouping by major category
    
    ORDER BY
    
    num_crimes DESC # number of crimes is in descending order

## num_crimes_per_yr

    SELECT
    
    year, # Selecting the year of this dataframe and showing the numbers by value columns
    
    count(value) AS num_crimes_per_year
    
    FROM
    
    `bigquery-public-data.london_crime.crime_by_lsoa`
    
    WHERE # removing anything not showing as 0
    
    value != 0
    
    GROUP BY
    
    year # grouping by year
    
    ORDER BY
    
    year DESC #order by descending

## monthly_crimes

    SELECT
    
    month, # Selecting the month of this dataframe and showing the numbers by value columns called monthly crimes
    
    count(value) AS monthly_crimes
    
    FROM
    
    `bigquery-public-data.london_crime.crime_by_lsoa`
    
    WHERE # removing anything not showing as 0
    
    value != 0
    
    GROUP BY
    
    month # grouping by month
    
    ORDER BY
    
    month DESC # order descending

## num_crimes_per_borough

    SELECT
    
    borough,
    
    minor_category,
    
    count(value) AS num_crimes_per_borough # Selecting the borough & minor category of this dataframe and showing the numbers by value columns called num crimes per borough
    
    FROM
    
    `bigquery-public-data.london_crime.crime_by_lsoa`
    
    WHERE
    
    value != 0 # removing anything not showing as 0
    
    GROUP BY
    
    borough,
    
    minor_category # grouping by borough & minor category
    
    ORDER BY
    
    num_crimes_per_borough DESC # order descending

## total_num_of_crimes

    SELECT
    
    minor_category,
    
    count(value) AS total_num_crimes_per_borough # Selecting the minor category of this dataframe and showing the numbers by value columns called total num crimes per borough
    
    FROM
    
    `bigquery-public-data.london_crime.crime_by_lsoa`
    
    WHERE
    
    value != 0 # removing anything with 0 amounts
    
    GROUP BY
    
    minor_category # grouping by the minor category
    
    ORDER BY
    
    total_num_crimes_per_borough DESC # descending order

