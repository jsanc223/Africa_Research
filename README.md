
# Africa Final API Project

This repository contains Python scripts designed for interacting with the Elsevier API to retrieve and organize detailed author and affiliation information associated with academic articles through their DOI values.

## Table of Contents
- [Introduction](#introduction)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
  - [get_author_info](#get_author_info)
  - [populate_author_df](#populate_author_df)
- [Acknowledgments](#acknowledgments)

## Introduction

The Africa Final API Project aims to facilitate the extraction of author and affiliation information from academic articles using the Elsevier API. The project provides utility functions to interact with the API, process the responses, and organize the obtained data into structured pandas DataFrames.

## Getting Started

### Prerequisites

Ensure that you have the following installed on your system:
- Python 3.x
- pandas
- numpy
- requests

### Installation

1. Clone this repository to your local system.
   ```sh
   git clone <Your Repository Link Here>
   ```
2. Navigate to the project directory and install the required Python packages.
   ```sh
   pip install pandas numpy requests
   ```

## Usage

1. Prepare an input DataFrame, `df`, containing a column `'DO'` with the DOI values of the articles you want to process.
2. Execute the provided Python scripts to generate a new DataFrame, `Author_df`, populated with author and affiliation information corresponding to each DOI.

## Features

### get_author_info

- **Input:**
  - `DO_value`: A string representing a DOI value.
- **Functionality:**
  - Sends requests to the Elsevier API to retrieve the abstracts associated with the provided DOI and extracts information about authors and their affiliations.
  - Retrieves detailed affiliation information including name, city, and country.
- **Output:**
  - Returns lists containing authors' names, affiliation IDs, affiliation names, cities, and countries.

### populate_author_df

- **Input:**
  - `df_subset`: A subset of the original DataFrame.
- **Functionality:**
  - Iterates over the rows of `df_subset`, calling `get_author_info()` for each DOI and creating a mini DataFrame with the obtained information.
  - Concatenates all the mini DataFrames to create a final DataFrame, `Author_df`.
- **Output:**
  - Returns a DataFrame, `Author_df`, containing detailed author and affiliation information.


## Acknowledgments

- Elsevier, for providing the API allowing access to a wealth of academic article information.
