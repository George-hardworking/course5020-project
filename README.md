## Course5020Project
This repository was established to complete the course assignment, which is a mini group project of the **Environmental Modeling and Big Data Analysis** course, proposed by **Prof. Luoye Chen**. 

The members of our team are as follows:
`Kaibiao ZHU, Junye ZHONG, Hongyue WU, Yueting ZHANG `

### Setup Environment

Use conda to create a reproducible environment

```bash
# create environment with a specific python version
conda create -n course5020 python=3.11 -y
conda activate course5020

# install pip and project dependencies
conda install pip -y
pip install --upgrade pip
pip install -r requirements.txt
```

Optional: register a Jupyter kernel for interactive runs

```bash
conda install ipykernel -y
python -m ipykernel install --user --name course5020 --display-name "course5020"
```

Notes
- The dataset is moderately large. Ensure you have sufficient memory (8GB+ recommended) when running full-year aggregations
- For faster conda installs consider using mamba: `conda install mamba -n base -c conda-forge` then `mamba install ...`

### Download Dataset

All raw data used in this project should be placed under the `raw_data` folder. The repository already includes many required files under `raw_data` but if you need to (re)download or update data, follow these guidelines

- Satellite fire data (MODIS) : expected filenames like `modis_2010_china.csv` ... `modis_2019_china.csv` and are located in `raw_data/satellite_fire_data/`
- PM2.5 per station or gridded data : expected filenames like `HLJ_2010_PM2.5.csv` etc and are located in `raw_data/specific_data/`
- County shapefiles and other auxiliary data : placed in `raw_data/CHN_County/`

Notes about missing years
- The provided PM2.5 dataset has no 2017 file this project handles that gracefully during preprocessing but if you have 2017 data, add it to `raw_data/specific_data/` with the same naming convention (eg HLJ_2017_PM2.5.csv)

If you need to fetch original sources you can obtain MODIS active fire products from NASA FIRMS or your institutional mirror and export them to CSV matching the expected columns used in the notebooks (`latitude longitude brightness acq_date confidence frp ...`)

### Project Structure
```
    ├── docs
    ├── raw_data
    ├── results
    │   ├── challenge3
    │   ├── task1
    │   ├── task2
    │   ├── task3
    │   └── task4
    ├── src
    │   ├── challenge1.ipynb
    │   ├── challenge3.1.ipynb
    │   ├── challenge3.2.ipynb
    │   ├── main_self.ipynb
    │   └── main_self_eng.ipynb
    ├── LICENSE
    ├── README.md
    └── requirements.txt  
```

### Running the project
```
cd src
python main.py                  #core task
python challenge1.ipynb
python challenge3.1.ipynb
python challenge3.2.ipynb
```

Quick tips for running notebooks

- Use JupyterLab or Jupyter Notebook to open the .ipynb files and run cells interactively
- To run a notebook end to end from the command line use nbconvert execute

```bash
jupyter nbconvert --to notebook --execute challenge3.2.ipynb --inplace
```

- If you run into memory issues during aggregation, try processing subset years or use Dask (optional dependency listed in requirements)

Outputs
- Processed daily aggregations and analysis CSVs are saved to `results/challenge3/` when you run the notebooks
- Figures produced by notebooks appear inline. You may export them manually if needed

Reproducibility
- After a successful run record exact package versions with

```bash
pip freeze > requirements-lock.txt
```

Contact and citation
- If you use this repository in your work please cite the project and contact the original authors or course instructor as appropriate






