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

`out_of_country.csv` should have a format like this:

```CSV
date,to_destination,re-entry
2020-01-01,Visiting Country B,0
2020-01-02,Resident Country A,1
2021-01-01,Visiting Country C,0
2021-01-02,Resident Country A,1
```

## Output

The output will be saved as `continuous_residence_under_180_days.csv`, which should return the above as all `False`. The total days outside of your resident country at any point of the rolling year period would be under 180 days.
