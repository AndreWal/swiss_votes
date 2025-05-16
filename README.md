# swiss_votes

**swiss_votes** is a comprehensive dataset of municipality-level voting outcomes for all Swiss popular votes from 1866 to 2023. This repository enables detailed analysis of voting behavior, trends, and regional variation across nearly 160 years of direct democracy.

## Datasets

- **final_1866_1999.parquet**  
  Municipality-level referendum results (1866–1999), mapped to the municipal boundaries as of 1999.

- **final_1866_2023.parquet**  
  Municipality-level referendum results (1866–2023), mapped to the municipal boundaries as of 2023.

- **all_combinations_1866_2023.parquet**  
  Complete set of all municipality–vote combinations from 1866 to 2023. Data until 1999 is mapped to the 1999 municipal structure; from 2000 onward, to the 2023 municipal structure.

## Columns

- `canton_id`: Official numeric ID of the canton  
- `canton_short`: Abbreviation of the canton  
- `mun_id`: Official numeric ID of the municipality  
- `mun_name`: Name of the municipality  
- `vote_id`: Official numeric ID of the popular vote  
- `year`: Year the popular vote took place  
- `date`: Date of the popular vote  
- `yes`: Number of yes votes  
- `no`: Number of no votes  

## Usage

The data files are in [Parquet](https://parquet.apache.org/) format and can be read using Python (e.g., with `pandas` or `pyarrow`), R, or other compatible tools. Example (Python):

```python
import polars as pl

df = pl.read_parquet("final_1866_2023.parquet")
print(df.head())
