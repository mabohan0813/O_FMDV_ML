# O-type FMDV specific antibody classifier based on machine learning model
O_FMDV_ML is based on machine learning models to predict O-type FMDV-specific antibodies.

## Args:

```
-i, IMGT HighV-QUEST results file dir.
  --input dir
     --result file1(name the folder as the antigen_name)
     --result file2(name the folder as the antigen_name)
     --...
-o, Output path
--remove_redandunt, default=True,
   True or False. It is faster when running on non-redandunt data.
--format, csv or tsv. Output file format of prediction. 
--cpu, Specify how many cores to use, default=1
--olga_path, The absolute path of python script: compute_pgen.py. /xxx/xx/olga/compute_pgen.py
--pssm_path, The absolute path of PSSM result files
--mode, validate or predict, default="predict"
--antigen_names, The folder names of IMGT HighV-QUEST result files, split by ',', default="hiv,flu,pps,acpa,tt,hcv,hbv"
```

## Requirements:

```
Linux environment
python 3.9.25
pandas              : 2.3.3
Bio (Biopython)     : 1.85
joblib              : 1.5.2
```
