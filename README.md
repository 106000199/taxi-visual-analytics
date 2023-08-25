# Taxi Trip Visual Analytics

## Setup

### Create Conda Environment

Create a conda environment with the following command:
```
$ conda create -n taxi-trip-visual-analytics python=3.10
```

### Install Dependencies
```
$ pip install -r requirements.txt
```

### Update Dependencies

To add or remove dependencies, edit the [requirements.in](requirements.in) file and run the following command:
```
$ pip-compile requirements.in
```

Note: Skip this if you're not trying to modify `requirements.txt`.

### Download Cleaned and Sample Taxi and Land Use Data

We store our cleaned and sample taxi and land use data on Google Drive, to download them, run the following under `./application/data/` directory:
```
$ python download_clean_data.py
```

## Data Collection: Download Google Popular Times Data

To collect raw Google Popular Times data, add your API key to [./application/data/populartime.py](application/data/populartime.py) run the following under `./application/data/` directory:
```
$ python populartime.py
```

## Data Cleaning

The cleaned and sample cleaned data are provided in the [./application/data/clean/](application/data/clean/) and [./application/data/sample/](application/data/sample/) directories, respectively. To re-execute data cleaning, execute the following under `./application/data/` directory:
```
$ python data_cleaning [--data <dataset_name>] [--create_sample]
```
where `dataset_name` needs to be one of the following: `all`, `taxi`, `popular_times`, `land_use` and `--create_sample` is an optional flag that creates additional clean sample of size 1000 from the cleaned data.

## Run the App

To start the app, execute the following under `./application/` directory:
```
$ python app.py
```

Note make sure to download the cleaned data before launching the app. See [here](#download-cleaned-taxi-and-land-use-data).