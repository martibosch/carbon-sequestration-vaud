# Evaluation of the carbon sequestration for the canton of Vaud

## Analysis DAG

TODO

## Instructions to reproduce the repository

### Preparing the environment

1. Create the conda environment

        # the environment's name will be `carbonseq_vaud`
        conda env create -f environment.yml

2. Configure your S3 profile (credentials, region and endpoint URL)

3. Enter the fresh environment

        conda activate carbonseq_vaud

4. Already within the environment, make it available as a `jupyter` kernel as in:

        python -m ipykernel install --user --name carbonseq_vaud --display-name "Python (carbonseq_vaud)"

### Reproducing

1. From the repository's root, create a folder named `papermill_outputs`

2. Pull the data from the dvc remote

        dvc pull
        
3. Reproduce the land data frame

        dvc repro data/vaud_ldf.csv.dvc
        
Now you can execute the Notebook `invest.ipynb`
