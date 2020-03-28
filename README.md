# VISA Indefinite Leave to Remain Jupyter Notebook

Verifying that one has more than 180 continuous resident days in a country.

## Dependencies

- python3
- venv

## Installation

```bash
python3 -m venv venv
source ./venv/bin/activate
pip install -r requirements.txt
```

This will install all dependencies.

In order to use your local `venv` dependencies, run the following:

```bash
ipython kernel install --user --name=venv
```

## Start

To start the Python notebook, run:
`jupyter notebook`

## Input

In a file called `out_of_country.csv`, fill in your own travel history.

It should have a format like this:

```CSV
date,to_destination,re-entry
2020-01-01,Visiting Country B,0
2020-01-02,Resident Country A,1
2021-01-01,Visiting Country C,0
2021-01-02,Resident Country A,1
```

In this example, a person travelled to the `to_destination`: "Visiting Country B" on `date`: 2020-01-01. They returned to their resident country on the next day and the `re-entry` was set to `1`, as they were re-entering their resident country.

## Output

The output will be saved as `continuous_residence_under_180_days.csv`.

It will have a format like this:

```csv
date,re-entry
2020-01-01,False
2024-01-01,True
```

If the total days of continuous residency is below 180 days at any point in a rolling window of a year (365 days), it will return `True`.
