# Processing Cookbook (Holland Lab) 

A suite of scripts developed to automate the processing of omics data within the lab.

To generate the processing script `Cookbook-script.sh`, do the following steps.

1. Update `Cookbook-instructions.txt` script: (1) specify input and output directories, path to genome fasta/index (where needed) and gene annotation gtf (where needed); (2) specify tools at each processing step, or select `Skip` if the step is skipped; (3) add/remove required arguments for each tool. Save the updated instruction file.

2.  To generate a processing script, run the following:

```bash
bash Cookbook-generate.sh -i Cookbook-instructions.txt -o Cookbook-script.sh
```

3. Run the generated script `Cookbook-script.sh`. Use `slurm` submission, if working through HPC. Ensure that all required tools are pre-installed.

To generate the processing report `Processing-report.csv`, run the following:

```bash
bash Cookbook-stats.sh -i Cookbook-stats-instructions.csv -o Processing-report.csv \
  -p <full-path-to-directory-with-processed-files> \
  -d <full-path-to-directory-with-input-files>
```

For the path to the input and processing directory, use the full (not relative) path. Can be run interactively as this script, works fast, and does not require a lot of memory.

