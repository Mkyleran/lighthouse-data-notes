# `pip install`

geopy
- Required by `geopandas.tools.geocode()`
- [Documentation](https://geopy.readthedocs.io/en/stable/)
- [PyPI](https://pypi.org/project/geopy/)

[ipywidgets](https://ipywidgets.readthedocs.io/en/stable/index.html)
- Interactive Jupyter Lab cells

## Bootcamp DevEnv

- `brew install miniforge` miniforge is the Anaconda implementation built for Apple Silicon  
- Quit & Reopen the terminal
- Create an environment:  
`conda create --name <env_name> python=<version number>`
- Link the environment to ZSH:  
`conda init zsh`
- Quit & Reopen the terminal
- Activate the environment:  
`conda activate base_env`
- Install additional packages:  
`conda install numpy pandas matplotlib plotly scikit-learn jupyter jupyterlab`

### jupyter lab

- From [documentation](https://jupyterlab.readthedocs.io/en/stable/user/extensions.html#), installing a source extension requires rebuilding JupyterLab which requires Node.js  
`conda install nodejs`

### Git

[install git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

### Kite

`pip install "jupyterlab-kite>=2.0.2"`

### Graph Decision Tree

`pip install pydotplus`  
`conda install graphviz` installing from pip gave raised the error `GraphViz's executables not found` in the python code. Conda installed a newer version and extra dependancies which solved the problem.

### PostgreSQL

`pip/conda install psycopg2`

###
flask, flask_restful

conda install numpy pandas matplotlib plotly scikit-learn jupyter jupyterlab nodejs graphviz psycopg2 flask

pip install jupyterlab-kite pydotplus flask_restful

## Brew
postgresql
Tableau Public W3D1
MongoDB
Cyberduck
Docker