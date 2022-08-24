# Predicting_NBA_MVP
## Goal 

Get data insights from web scrapping NBA data, build and deploy machine leraning model to predict top NBA MVP winner 

## Data decriptions 
1. MVP voting data: A dataset which has all the MVP voting information from 1990 to 2021
2. Team data: Team performance from 1990 to 2021 
3. Player statistics: Per game statistics on each player from 1990 to 2021 

## Data preprocessing 
Garbage in and garbage out, cleaning data is important 

Somewhere I clear the data:

### From Player statistics data 
- Remove star behind the player name : The reason that the data has a star, behind the player name may because all the Hall of Fame player has a star behind the their names in this data set 

    |      | Player       | Pos   |   Age | Tm   |
    |-----:|:-------------|:------|------:|:-----|
    | 3477 | Kobe Bryant* | SF    |    18 | LAL  |
    | 4076 | Kobe Bryant* | SF    |    19 | LAL  |
    | 4637 | Kobe Bryant* | SG    |    20 | LAL  |
    | 5172 | Kobe Bryant* | SG    |    21 | LAL  |
    | 5682 | Kobe Bryant* | SG    |    22 | LAL  |

- The same player have more than one record in the same year: This is because this player was traded into different team in the same year. Solution to this is using groupby method(groupby the year and the player name) and use the latest team he palyed 
    |    | Player   | Pos   |   Age | Tm   |
    |---:|:---------|:------|------:|:-----|
    | 25 | Uwe Blab | C     |    27 | TOT  |
    | 26 | Uwe Blab | C     |    27 | GSW  |
    | 27 | Uwe Blab | C     |    27 | SAS  |

### When mergeing the MVP player and player statistics data, there are empty fields. This is because not all the player are voted to be shortlisted in MVP voting. Simple solution to this is fill in 0.


### For team standing data: 
- Fill in 0 for leading team in that year 

    |    |   W |   L |   W/L% | GB   |   PS/G |
    |---:|----:|----:|-------:|:-----|-------:|
    |  0 |  53 |  29 |  0.646 | —    |  110.2 |
    |  1 |  52 |  30 |  0.634 | 1.0  |  110   |
    |  2 |  45 |  37 |  0.549 | 8.0  |  108.3 |
    |  3 |  31 |  51 |  0.378 | 22.0 |  107.7 |
    |  4 |  18 |  64 |  0.22  | 35.0 |  100.6 |

Data cleaning process is more than what i show here.

## EDA 



