# Traiding tool with Binance 
This repo contains a [Dash app](https://plotly.com/dash/) for traiding using Binance and Kucoin public APIs information. To run it, we recommend to create a virtual environment and install required dependencies.

## Verify python version
Make sure your python version is greater or equal to 3.0.0
```shell 
python --version
```

## Create a virtual environment
To run the app, first create a virtual environment using python module `virtualenv`:
```shell 
python -m virtualenv <env name>
```

and activate it
- Mac/Linux: 
```shell 
source <env name>/bin/activate
```
- Windows: 
```shell 
source <env name>/Scripts/activate
```

If you name your environment something different from `my_env`, do not forget to add it to the `.gitignore` file. 

## Install dependencies
Then install dependencies with pip:
```shell
pip install -r requirements.txt
```

## Create a configuration file
You need to provide a configuration file with actual and test API tokens for Binance and Kucoin. Create a `secret.cfg` and **do not publish or share it**
```
[BINANCE]
ACTUAL_API_KEY = <your-actual-api-key>
ACTUAL_SECRET_KEY = <your-actual-secret-key>
```

## Create database
Create an empty sqlite3 database file: `trading_tool.db`:
```shell
touch trading_tool.db
```

## Load data
Load master data from binance:
```shell
python exec/create.py
```
```shell
python exec/insert_symbols.py
```
```shell
python exec/insert_klines_1d.py
```

## Run the app in your browser
and finally run it
```shell
python app.py
```

## Deactive virtual environment
When finished, remember to deactivate virtual environment
```shell 
deactivate
```
