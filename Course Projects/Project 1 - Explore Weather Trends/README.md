# ⛅ Project 1: Explore Weather Trends

## Step 1: Data exploration
- Tool: Udacity SQL Workspace
- Objective: See how the data looks like in each table

```SQL
SELECT * FROM city_list
LIMIT 5;
```
| city      | country              |
|-----------|----------------------|
| Abidjan   | Côte D'Ivoire        |
| Abu Dhabi | United Arab Emirates |
| Abuja     | Nigeria              |
| Accra     | Ghana                |
| Adana     | Turkey               |

Table `city_list` has 2 columns: `city` and `country`. Since I’m living in *Vietnam*, I want to know which cities are available in this table:

```SQL
SELECT * FROM city_list
WHERE country = 'Vietnam';
```
| city             | country |
|------------------|---------|
| Hanoi            | Vietnam |
| Ho Chi Minh City | Vietnam |

To see how data looks like in the table `city_data`, I query:

```SQL
SELECT * FROM city_data
LIMIT 5;
```
| year | city    | country       | avg_temp |
|------|---------|---------------|----------|
| 1849 | Abidjan | Côte D'Ivoire | 25.58    |
| 1850 | Abidjan | Côte D'Ivoire | 25.52    |
| 1851 | Abidjan | Côte D'Ivoire | 25.67    |
| 1852 | Abidjan | Côte D'Ivoire |          |
| 1853 | Abidjan | Côte D'Ivoire |          |

This table has 4 columns: `year`, `city`, `country`, and `avg_temp`. Noticed that `avg_temp` has BLANK.
To see the sample data in the table `global_data`, I query:

```SQL
SELECT * FROM global_data
LIMIT 5;
```
| year | avg_temp |
|------|----------|
| 1750 | 8.72     |
| 1751 | 7.98     |
| 1752 | 5.78     |
| 1753 | 8.39     |

This table has 2 columns: `year` and `avg_temp`.

## Step 2: Data preparation

- Tool: Udacity SQL Workspace & Microsoft Excel
- Objective: Get the needed data to analyze

I query and download the temperature data for *Ho Chi Minh City* and save it as  `city_data.csv`.
```SQL
SELECT * FROM city_data
WHERE city = 'Ho Chi Minh City'
AND country = 'Vietnam'
```
| year | city             | country | avg_temp |
|------|------------------|---------|----------|
| 1825 | Ho Chi Minh City | Vietnam | 27.11    |
| 1826 | Ho Chi Minh City | Vietnam |          |
| 1827 | Ho Chi Minh City | Vietnam |          |
| 1828 | Ho Chi Minh City | Vietnam |          |
| …    |                  |         |          |
I do similarly for the global_data and save it as `global_data.csv`.
```SQL
SELECT * FROM global_data
```
| year | avg_temp |
| --- | --- |
| 1750 | 8.72 |
| 1751 | 7.98 |
| 1752 | 5.78 |
| 1753 | 8.39 |
| … |  |
## Step 3: Data wrangling

- Tool: Microsoft Excel
- Objective: calculate moving averages

First, I use `VLOOKUP` to take the relevant data from `global_data.csv` to `city_data.csv`. 

The first year in the Ho Chi Minh City dataset is 1825, while the first year in the global dataset is 1750. 
I choose 1825 as the starting year to calculate moving averages.
Using `AVERAGE`, I can calculate 20-year moving averages for Ho Chi Minh City and World data.

![Untitled](https://github.com/qanhnn12/Udacity-Data-Analyst-Nanodegree/assets/84619797/8d770cb0-ac35-4a2c-9867-267145221577)

## Step 4: Data visualization
- Tool: Microsoft Excel
- Objective: have a chart that displays local and global temperature trends

I use three columns: `year`, `Ho Chi Minh City` and `World` in the table above to make the line chart.

![1](https://github.com/qanhnn12/Udacity-Data-Analyst-Nanodegree/assets/84619797/889f2a96-4690-45a3-9343-2c9516d59771)

## Step 5: Data analysis
- Tool: Microsoft Excel
- Objective: Provide some insights about Ho Chi Minh City and the world’s temperatures

Besides the chart, I use `MIN()`, `MAX()`, `AVERAGE()`, `MEDIAN()`, `MODE.SNGL()`, `STDEV.S()` functions in Excel to calculate some statistics for the averages (not the moving averages) of Ho Chi Minh City and the global temperature. 

|  | Ho Chi Minh city | World |
| --- | --- | --- |
| Min | 24.85 | 7.38 |
| Max | 28.46 | 9.73 |
| Range (Max-Min) | 3.61 | 2.35 |
| Mean | 27.18 | 8.48 |
| Median | 27.23 | 8.44 |
| Mode | 26.87 | 8.18 |
| Std Deviation | 0.498447 | 0.497769 |

- Overall, the average temperature of Ho Chi Minh City and the world has increased over time.
- The data of both is clustered around the mean because of low standard deviation (~0.5), which means the temperature fluctuation over time is quite small.
- The temperature range (difference between the max and the min) in Ho Chi Minh City is higher than that of the world (Ho Chi Minh City: 3.61, the world: 2.35).
- Ho Chi Minh City is 3 times hotter than the world on average. The difference (about 18°C) has been consistent throughout the years, as the two lines in the chart are nearly parallel.
