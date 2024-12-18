# Pronghorn - Snakemake SLURM Setup

This is setup for the SLURM scheduler for Snakemake Pipelines in Pronghorn. 

Note: Please, use the latest Snakemake version (8.X) 

- Step 1: Check the Snakemake version in your local pronghorn account by 
`snakemake --version`

- Step 2: If the version is *8.X*, then please download the `simple_v8/config.yaml` file in it and upload it into the correct folder as follows.  Create the directory structure using `mkdir -p ~/.config/snakemake/simple_v8/` then `cd ~/.config/snakemake/simple_v8/`
Afterwards use `wget` or `curl` to download the `config.yaml` file: 
```
wget https://raw.githubusercontent.com/Nevada-Bioinformatics-Center/pronghorn_snakemake_config/refs/heads/main/simple_v8/config.yaml
```
You may change the `simple_v8` directory name to a name of your choice. Later, this will be your snakemake profile when executed.

- Step 3: Install the following commands 
```
pip install snakemake-executor-plugin-slurm

```
and 
```
pip install snakemake-executor-plugin-cluster-generic
```

- Step 4: Go to the folder/directory containing the Snakefile you wish to run.

- Step 5: Run the following command
  ```
  snakemake --profile simple_v8 --jobs 2 -n
  ```
  Here, `--profile` is the `simple_v8` directory/folder name which house the config.yaml file, followed by the number of jobs `--jobs` which is 2. And `-n` is just for `dryrun`.
