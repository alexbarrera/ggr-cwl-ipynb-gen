# ggr-cwl-ipynb-gen
Jupyter notebook generator to download and execute the processing files for GGR related datasets.
At this point, is not intented to cover all use cases, but to serve as a quick generator of all
related files and scripts to pre-process genomic data generated at the [Duke-GCB Sequencing Core](https://genome.duke.edu/cores-and-services/sequencing-and-genomic-technologies) in [HARDAC](https://genome.duke.edu/cores-and-services/computational-solutions/compute-environments-genomics).

Example of usage:
```
$ ggr_cwl_ipynb_gen \
  --root-dir /path/to/rootdir \
  --metadata examples/Hong_3979_170316B1.xlsx \
  --out /path/to/output_dir \
  --force
```
The information in the example metadata and configuration file should reveal what is needed to download and pre-process the samples.

For a full list of options:
```
$ ggr_cwl_ipynb_gen -h
usage: Generator of Jupyter notebooks to execute CWL pre-processing pipelines
       [-h] -o OUT -m METADATA [-f] [-n] [--metadata-sep SEP]
       [--project-name PROJECT_NAME]
       [--data-from {dukeds,sftp,miseq,other,local}] [-c CONF_FILE] [-u USER]
       [-e USER_DUKE_EMAIL] [-r ROOT_DIR] [-v VERSION]

optional arguments:
  -h, --help            show this help message and exit
  -o OUT, --out OUT     Jupyter notebook output file name
  -m METADATA, --metadata METADATA
                        Metadata file with samples information
  -f, --force           Force to overwrite output file
  -n, --no-upload       Avoids uploading generated data to database when
                        specified
  --metadata-sep SEP    Separator for metadata file (when different than Excel
                        spread sheet)
  --project-name PROJECT_NAME
                        Project name (by default, basename of metadata file
                        name)
  --data-from {dukeds,sftp,miseq,other,local}
                        Choices: dukeds, sftp, miseq, other, local
  -c CONF_FILE, --conf-file CONF_FILE
                        YAML configuration file (see examples)
  -u USER, --user USER  HARDAC User used in SLURM (default: ${USER})
  -e USER_DUKE_EMAIL, --user-duke-email USER_DUKE_EMAIL
                        Email(s) notified when execution is finished (default:
                        ${USER}@duke.edu)
  -r ROOT_DIR, --root-dir ROOT_DIR
                        Root directory where all subfolders and files will be
                        created (semi-required: either defined here or in
                        conf-file)
  -v VERSION, --version VERSION
                        Print version of the program and exit
```
