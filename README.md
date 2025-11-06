## Course5020Project
This repository was established to complete the course assignment, which is a mini group project of the **Environmental Modeling and Big Data Analysis** course, proposed by **Prof. Luoye Chen**. 

The members of our team are as follows:
`Kaibiao ZHU, Junye ZHONG, Hongyue WU, Yueting ZHANG `

---

### Setup Environment

Use `conda` to create a reproducible environment:

1. Create environment with a specific python version.

```bash
conda create -n course5020 python=3.11 -y
conda activate course5020
```

2. Install pip and project dependencies.

```
conda install pip -y
pip install --upgrade pip
pip install -r requirements.txt
pip install ipykernel
```
Notes：
- The dataset is moderately large. When conducting the annual summary operation, please ensure that you have sufficient memory (recommending more than 8GB) and sufficient time - it may take up to two hours.

### Download Dataset

All raw data used in this project should be placed under the `raw_data` folder. The details of all the dataset are as follows:

-  For the part of core tasks, the dataset is already presented in the `raw_data` folder.
-  For the part of challenge, you can get the dataset by sending an email to author.

Notes about missing years
- The provided PM2.5 dataset has no 2017 file this project handles that gracefully during preprocessing but if you have 2017 data, add it to `raw_data/specific_data/` with the same naming convention (eg: HLJ_2017_PM2.5.csv)


### Project Structure
```
course5020-project
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
You can enter the following code in the terminal to run the main program：
```
cd src
python main.py  
python challenge1.ipynb
python challenge3.1.ipynb
python challenge3.2.ipynb
```

Quick tips for running notebooks：

- Use JupyterLab or Jupyter Notebook to open the .ipynb files and run cells interactively.

### Contact and citation
- If you want to contact the auther, please send an email to `kzhu597@connect.hkust-gz.edu.cn`.  

- If you find this project useful, please cite it as follows:

```
@misc{zhu2025investigating,
      title={Investigating Agricultural Burning with Remote Sensing Data}, 
      author={Kaibiao Zhu and Junye Zhong and Hongyue Wu and Yueting Zhang},
      year={2025},
      url={https://github.com/George-hardworking/course5020-project},
      note={GitHub repository},
}
```




