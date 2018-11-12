# Evaluation of the carbon sequestration for the canton of Vaud

## Preparing the environment

1. Create the conda environment

        # the environment's name will be `carbonseq_vaud`
        conda env create -f environment.yml

2. Follow [this instructions](https://conda.io/docs/user-guide/tasks/manage-environments.html#saving-environment-variables) to set the environment variables `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` for the fresh `floodreg_vaud` conda environment (in order for [boto3 to find your S3-like credentials](https://boto3.amazonaws.com/v1/documentation/api/latest/guide/configuration.html#configuring-credentials) for DigitalOcean Spaces). They correspond to the DigitalOcean Spaces access and secret key respectively. **Important note:** the command `jupyter-notebook` must be launched from within the `floodreg_vaud` environment so the access keys can be extracted from the environment variables

3. Enter the fresh environment

        conda activate carbonseq_vaud

4. Already within the environment, make it available as a `jupyter` kernel as in:

        python -m ipykernel install --user --name carbonseq_vaud --display-name "Python (carbonseq_vaud)"

## Reproducing

1. From the repository's root, create a folder named `papermill_outputs`

2. Pull the data from the dvc remote

        dvc pull
        
3. Reproduce the land data frame

        dvc repro data/vaud_ldf.csv.dvc
        
Now you can execute the Notebook `invest.ipynb`
