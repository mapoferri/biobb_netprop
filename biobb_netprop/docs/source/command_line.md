# BioBB NetProp Command Line Help



Generic usage:
```python
biobb_command [-h] --config CONFIG --input_file(s) <input_file(s)> --output_file <output_file>
```
-----------------


## GDADisGenet
biobb_netprop Gene Disease Association DisGenet retrieval
### Get help
Command:
```python
gda_disgenet -h 
```
    usage: gda_disgenet [-h] [--config CONFIG] --input_file_path INPUT_FILE_PATH --output_csv_path OUTPUT_CSV_PATH
    
    Gene Disease Attributes retrieval from the DisGenet database.
    
    optional arguments:
      -h, --help            show this help message and exit
      --config CONFIG       Configuration file
    
    required arguments:
      --input_file_path INPUT_FILE_PATH
                            General path of working Dir.
      --output_csv_path OUTPUT_CSV_PATH
                            Results from the DisGenet database in CSV format. Accepted formats: csv.
### I / O Arguments
Syntax: input_argument (datatype) : Definition

Config input / output arguments for this building block:
* **input_file_path** (*string*): Path to the working dir.
* **output_csv_path** (*string*): Path to the CSV file with the Gene Disease Attributes from the DisGenet database. File type: csv. [Sample file](https://urlto.sample). Accepted formats: CSV
### Config
Syntax: input_parameter (datatype) - (default_value) Definition

Config parameters for this building block:

* **retrieve_by** (*str*) - Configuration params to pass for the retrieval of the association on the REST API (**gene, uniprot_entry, disease, source, evidences_gene, evidences_disease**).            
* **gene_id** (*str*) - Number identification for a gene or a list of genes separated by commas recognized by the database.
* **disease** (*str*) - Disease id or a list of disease separated by commas.
* **disease_type** (*str*) - Disease, phenotype, group.
* **source** (*str*) - Source of the associations (CURATED, INFERRED, ANIMAL_MODELS, ALL, BEFREE, CGI, CLINGEN, CLINVAR, CTD_human, CTD_mouse, CTD_rat, GENOMICS_ENGLAND, GWASCAT, GWASDB, HPO, LHGDN, MGD, ORPHANET, PSYGENET, RGD, UNIPROT).
* **disease_vocabulary** (*str*) - Disease vocabulary (icd9cm, icd10, mesh, omim, do, efo, nci, hpo, mondo, ordo).
* **disease_class** * - MeSh disease classes.
* **min_score** (*str*) -  Min value of the gene-disease score range.
* **max_score** (*str*) -  Max value of the gene-disease score range.
* **min_ei** (*str*) -  Min value of evidence index score range.
* **max_ei** (*str*) -  Max value of evidence index score range.
* **max_dsi** (*str*) - Max value of DSI range for the gene.
* **min_dsi** (*str*)  - Min value of DSI range for the gene.
* **max_pli** (*str*) -  Max value of pLI range for the gene.
* **min_pli** (*str*) -  Min value of pLI range for the gene.
* **format** (*str*) - Format output file.
* **limit** (*str*) - Number of GDAs to retrieve.
* **min_year** (*str*) - The year of the earliest publications.
* **max_year** (*str*) - The year of the latest publicatons.
* **offset** (*str*) - Starting offset of the page.
* **remove_tmp** (*bool*) - (True) [WF property] Remove temporal files.
* **restart** (*bool*) - (False) [WF property] Do not execute if output files exist.

### YAML
#### [Common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.yml)
```python
properties:
    retrieve_by: 'disease'
    disease_id: C0002395
    min_score: 0.2
    max_score: 1.0

```
#### Command line
```python
gda_disgenet --config config.yml --input_file_path /path/to/working/dir --output_csv_path gda_results.csv
```
### JSON
#### [Common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.json)
```python
{
  "properties": {
	"retrieve_by": "disease",
        "disease_id": C0002395,
        "min_score": 0.2,
        "max_score": 1.0,
  }
}
```
#### Command line
```python
gda_disgenet --config config.json --input_file_path /path/to/working/dir --output_csv_path gda_results.csv
```


## VDADisGenet
biobb_netprop Variant Disease Association DisGenet retrieval
### Get help
Command:
```python
vda_disgenet -h
```
    usage: vda_disgenet [-h] [--config CONFIG] --input_file_path INPUT_FILE_PATH --output_file_path OUTPUT_FILE_PATH

    Variant Disease Attributes retrieval from the DisGenet database.

    optional arguments:
      -h, --help            show this help message and exit
      --config CONFIG       Configuration file

    required arguments:
      --input_file_path INPUT_FILE_PATH
                            General path of working Dir.
      --output_file_path OUTPUT_FILE_PATH
                            Results from the DisGenet database in CSV format. Accepted formats: csv, json, tsv and xml.
### I / O Arguments
Syntax: input_argument (datatype) : Definition

Config input / output arguments for this building block:
* **input_file_path** (*string*): Path to the working dir.
* **output_file_path** (*string*): Path to the CSV file with the Variant Disease Attributes from the DisGenet database. File type: csv. [Sample file](https://urlto.sample). Accepted formats: CSV
### Config
Syntax: input_parameter (datatype) - (default_value) Definition

Config parameters for this building block:

* **retrieve_by** (*str*) - Configuration params to pass for the retrieval of the association on the REST API (**gene, variant, disease, source, evidences_gene, evidences_disease**).
* **variant_id** (*str*) - Number identification for a gene or a list of genes separated by commas recognized by the database.
* **disease_id** (*str*) - Disease id or a list of disease separated by commas.
* **disease_type** (*str*) - Disease, phenotype, group.
* **type** (*str*) - Disease, phenotype, group.
* **source** (*str*) - Source of the associations (CURATED, INFERRED, ANIMAL_MODELS, ALL, BEFREE, CGI, CLINGEN, CLINVAR, CTD_human, CTD_mouse, CTD_rat, GENOMICS_ENGLAND, GWASCAT, GWASDB, HPO, LHGDN, MGD, ORPHANET, PSYGENET, RGD, UNIPROT).
* **disease_vocabulary** (*str*) - Disease vocabulary (icd9cm, icd10, mesh, omim, do, efo, nci, hpo, mondo, ordo).
* **disease_class** * - MeSh disease classes.
* **min_score** (*str*) -  Min value of the gene-disease score range.
* **max_score** (*str*) -  Max value of the gene-disease score range.
* **min_ei** (*str*) -  Min value of evidence index score range.
* **max_ei** (*str*) -  Max value of evidence index score range.
* **max_dsi** (*str*) - Max value of DSI range for the gene.
* **min_dsi** (*str*)  - Min value of DSI range for the gene.
* **max_pli** (*str*) -  Max value of pLI range for the gene.
* **min_pli** (*str*) -  Min value of pLI range for the gene.
* **format** (*str*) - Format output file.
* **limit** (*str*) - Number of GDAs to retrieve.
* **min_year** (*str*) - The year of the earliest publications.
* **max_year** (*str*) - The year of the latest publicatons.
* **offset** (*str*) - Starting offset of the page.
* **remove_tmp** (*bool*) - (True) [WF property] Remove temporal files.
* **restart** (*bool*) - (False) [WF property] Do not execute if output files exist.

### YAML
#### [Common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.yml)
```python
properties:
    retrieve_by: 'disease'
    disease_id: C0002395
    min_score: 0.2
    max_score: 1.0

```
#### Command line
```python
vda_disgenet --config config.yml --input_file_path /path/to/working/dir --output_file_path vda_results.csv
```
### JSON
#### [Common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.json)
```python
{
  "properties": {
        "retrieve_by": "disease",
        "disease_id": C0002395,
        "min_score": 0.2,
        "max_score": 1.0,
  }
}
```
#### Command line
```python
vda_disgenet --config config.json --input_file_path /path/to/working/dir --output_file_path vda_results.csv
```
## DDADisGenet
biobb_netprop Disease Disease Association DisGenet retrieval
### Get help
Command:
```python
dda_disgenet -h
```
    usage: dda_disgenet [-h] [--config CONFIG] --input_file_path INPUT_FILE_PATH --output_file_path OUTPUT_FILE_PATH

    Disease Disease Attributes retrieval from the DisGenet database.

    optional arguments:
      -h, --help            show this help message and exit
      --config CONFIG       Configuration file

    required arguments:
      --input_file_path INPUT_FILE_PATH
                            General path of working Dir.
      --output_file_path OUTPUT_FILE_PATH
                            Results from the DisGenet database in CSV format. Accepted formats: csv, json, tsv and xml.
### I / O Arguments
Syntax: input_argument (datatype) : Definition

Config input / output arguments for this building block:
* **input_file_path** (*string*): Path to the working dir.
* **output_file_path** (*string*): Path to the CSV file with the Disease Disease Attributes from the DisGenet database. File type: csv. [Sample file](https://urlto.sample). Accepted formats: CSV
### Config
Syntax: input_parameter (datatype) - (default_value) Definition

Config parameters for this building block:

* **retrieve_by** (*str*) - Configuration params to pass for the retrieval of the association on the REST API (**genes or variants**).
* **disease_id** (*str*) - Disease id or a list of disease separated by commas.
* **source** (*str*) - Source of the associations (CURATED, INFERRED, ANIMAL_MODELS, ALL, BEFREE, CGI, CLINGEN, CLINVAR, CTD_human, CTD_mouse, CTD_rat, GENOMICS_ENGLAND, GWASCAT, GWASDB, HPO, LHGDN, MGD, ORPHANET, PSYGENET, RGD, UNIPROT).
* **disease_vocabulary** (*str*) - Disease vocabulary (icd9cm, icd10, mesh, omim, do, efo, nci, hpo, mondo, ordo).
* **pvalue** (*str*) -  Pvalue of the disease-disease score range.
* **format** (*str*) - Format output file.
* **limit** (*str*) - Number of disease to retrieve.
* **remove_tmp** (*bool*) - (True) [WF property] Remove temporal files.
* **restart** (*bool*) - (False) [WF property] Do not execute if output files exist.

### YAML
#### [Common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.yml)
```python
properties:
    retrieve_by: 'genes'
    disease_id: C0002395
    pvalue: 0.7
    limit: 10
```
#### Command line
```python
dda_disgenet --config config.yml --input_file_path /path/to/working/dir --output_file_path dda_results.csv
```
### JSON
#### [Common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.json)
```python
{
  "properties": {
        "retrieve_by": "disease",
        "disease_id": C0002395,
        "pvalue": 0.7,
        "limit": 10,
  }
}
```
#### Command line
```python
dda_disgenet --config config.json --input_file_path /path/to/working/dir --output_file_path dda_results.csv
```



## GADisGenet
biobb_netprop Gene Attribute DisGenet retrieval
### Get help
Command:
```python
ga_disgenet -h
```
    usage: ga_disgenet [-h] [--config CONFIG] --input_file_path INPUT_FILE_PATH --output_file_path OUTPUT_FILE_PATH

    Gene Attributes retrieval from the DisGenet database.

    optional arguments:
      -h, --help            show this help message and exit
      --config CONFIG       Configuration file

    required arguments:
      --input_file_path INPUT_FILE_PATH
                            General path of working Dir.
      --output_file_path OUTPUT_FILE_PATH
                            Results from the DisGenet database in CSV format. Accepted formats: csv, json, tsv and xml.
### I / O Arguments
Syntax: input_argument (datatype) : Definition

Config input / output arguments for this building block:
* **input_file_path** (*string*): Path to the working dir.
* **output_file_path** (*string*): Path to the CSV file with the Gene Attributes from the DisGenet database. File type: csv. [Sample file](https://urlto.sample). Accepted formats: CSV, TSV, JSON and XML.
### Config
Syntax: input_parameter (datatype) - (default_value) Definition

Config parameters for this building block:

* **retrieve_by** (*str*) - Configuration params to pass for the retrieval of the association on the REST API (**gene, uniprot, source**).
* **gene_id** (*str*) - Number identification for a gene or a list of genes separated by commas recognized by the database.
* **uniprot_id** (*str*) - Uniprot id or a list of disease separated by commas.
* **source** (*str*) - Source of the associations (CURATED, INFERRED, ANIMAL_MODELS, ALL, BEFREE, CGI, CLINGEN, CLINVAR, CTD_human, CTD_mouse, CTD_rat, GENOMICS_ENGLAND, GWASCAT, GWASDB, HPO, LHGDN, MGD, ORPHANET, PSYGENET, RGD, UNIPROT).
* **max_dsi** (*str*) - Max value of DSI range for the gene.
* **min_dsi** (*str*)  - Min value of DSI range for the gene.
* **max_pli** (*str*) -  Max value of pLI range for the gene.
* **min_pli** (*str*) -  Min value of pLI range for the gene.
* **format** (*str*) - Format output file.
* **limit** (*str*) - Number of GAs to retrieve.



#### [Common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.yml)
```python
properties:
    retrieve_by: 'gene'
    gene_id: 'AD3L'
    max_dsi: 0.7
```
#### Command line
```python
ga_disgenet --config config.yml --input_file_path /path/to/working/dir --output_file_path ga_results.json
```
### JSON
#### [Common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.json)
```python
{
  "properties": {
        "retrieve_by": "gene",
        "gene_id": AD3L,
        "max_dsi": 0.7,
  }
}
```
#### Command line
```python
ga_disgenet --config config.json --input_file_path /path/to/working/dir --output_file_path ga_results.csv
```

## VADisGenet
biobb_netprop Variant Attribute DisGenet retrieval
### Get help
Command:
```python
va_disgenet -h
```
    usage: va_disgenet [-h] [--config CONFIG] --input_file_path INPUT_FILE_PATH --output_file_path OUTPUT_FILE_PATH

    Variant Attributes retrieval from the DisGenet database.

    optional arguments:
      -h, --help            show this help message and exit
      --config config       configuration file

    required arguments:
      --input_file_path input_file_path
                            general path of working dir.
      --output_file_path output_file_path
                            results from the disgenet database in csv format. accepted formats: csv, json, tsv and xml.
### i / o arguments
syntax: input_argument (datatype) : definition

config input / output arguments for this building block:
* **input_file_path** (*string*): path to the working dir.
* **output_file_path** (*string*): path to the CSV file with the Variant Attributes from the DisGenet database. file type: csv, json, tsv, xml. [sample file](https://urlto.sample). accepted formats: csv, tsv, json and xml.
### config
syntax: input_parameter (datatype) - (default_value) definition

config parameters for this building block:

* **retrieve_by** (*str*) - configuration params to pass for the retrieval of the association on the rest api (**gene, variant, source**).
* **gene_id** (*str*) - number identification for a gene or a list of genes separated by commas recognized by the database.
* **variant_id** (*str*) - List of variants (dbSNP Identifiers) separated by "," up to 100.
* **source** (*str*) - source of the associations (curated, inferred, animal_models, all, befree, cgi, clingen, clinvar, ctd_human, ctd_mouse, ctd_rat, genomics_england, gwascat, gwasdb, hpo, lhgdn, mgd, orphanet, psygenet, rgd, uniprot).
* **max_dsi** (*str*) - max value of dsi range for the gene.
* **min_dsi** (*str*)  - min value of dsi range for the gene.
* **max_pli** (*str*) -  max value of pli range for the gene.
* **min_pli** (*str*) -  min value of pli range for the gene.
* **format** (*str*) - format output file.
* **limit** (*str*) - number of gas to retrieve.



#### [common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.yml)
```python
properties:
    retrieve_by: 'variant'
    variant_id: 'ad3l'
    max_dsi: 0.7
```
#### command line
```python
va_disgenet: --config config.yml --input_file_path /path/to/working/dir --output_file_path va_results.json
```
### JSON
#### [Common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.json)
```python
{
  "properties": {
        "retrieve_by": "variant",
        "variant_id": AD3L,
        "max_dsi": 0.7,
  }
}
```
#### Command line
```python
va_disgenet --config config.json --input_file_path /path/to/working/dir --output_file_path va_results.csv
```
## DADisGenet
biobb_netprop Disease Attribute DisGenet retrieval
### Get help
Command:
```python
da_disgenet -h
```
    usage: da_disgenet [-h] [--config CONFIG] --input_file_path INPUT_FILE_PATH --output_file_path OUTPUT_FILE_PATH

    Disease Attributes retrieval from the DisGenet database.

    optional arguments:
      -h, --help            show this help message and exit
      --config config       configuration file

    required arguments:
      --input_file_path input_file_path
                            general path of working dir.
      --output_file_path output_file_path
                            results from the disgenet database in csv format. accepted formats: csv, json, tsv and xml.
### i / o arguments
syntax: input_argument (datatype) : definition

config input / output arguments for this building block:
* **input_file_path** (*string*): path to the working dir.
* **output_file_path** (*string*): path to the csv file with the Disease Attributes from the DisGenet database. file type: csv, json, tsv, xml. [sample file](https://urlto.sample). accepted formats: csv, tsv, json and xml.
### config
syntax: input_parameter (datatype) - (default_value) definition

config parameters for this building block:

* **retrieve_by** (*str*) - configuration params to pass for the retrieval of the association on the rest api (**disease, diseaseName, source, mappings, similarity**).
* **diseaseName** (*str*) - Disease name recognized by the database.
* **disease_id** (*str*) - number identification for a gene or a list of genes separated by commas recognized by the database.
* **variant_id** (*str*) - List of variants (dbSNP Identifiers) separated by "," up to 100.
* **source** (*str*) - source of the associations (curated, inferred, animal_models, all, befree, cgi, clingen, clinvar, ctd_human, ctd_mouse, ctd_rat, genomics_england, gwascat, gwasdb, hpo, lhgdn, mgd, orphanet, psygenet, rgd, uniprot).
* **max_dsi** (*str*) - max value of dsi range for the gene.
* **min_dsi** (*str*)  - min value of dsi range for the gene.
* **max_pli** (*str*) -  max value of pli range for the gene.
* **min_pli** (*str*) -  min value of pli range for the gene.
* **format** (*str*) - format output file.
* **limit** (*str*) - number of gas to retrieve.



#### [common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.yml)
```python
properties:
    retrieve_by: 'disease'
    disease_id: 'C00002352'
    max_dsi: 0.7
```
#### command line
```python
da_disgenet: --config config.yml --input_file_path /path/to/working/dir --output_file_path da_results.json
```
### JSON
#### [Common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.json)
```python
{
  "properties": {
        "retrieve_by": "disease",
        "disease_id": 'C00002352',
        "max_dsi": 0.7,
  }
}
```
#### Command line
```python
da_disgenet --config config.json --input_file_path /path/to/working/dir --output_file_path da_results.csv
```

## Parse HIPPIE
biobb_netprop Parse HIPPIE database wrapper.
### Get help
Command:
```python
parsehippie -h
```
    usage: parsehippie [-h] [--config CONFIG] --input_file_path1 INPUT_FILE_PATH1 --input_file_path2 INPUT_FILE_PATH2 --output_sif_path OUTPUT_SIF_PATH

    Parsing the HIPPIE database using the Human genome as reference.

    optional arguments:
      -h, --help            show this help message and exit
      --config config       configuration file

    required arguments:
      --input_file_path1 input_file_path
                            Path for the HIPPIE database downloaded in a specific dir, **mandatory to download on its own**.
      --input_file_path2 input_file_path
                            Path for the HIPPIE genes to be parsed, **mandatory to download on its own**.
      --output_sif_path output_sif_path
                            Path for the resulting panda dataframe from the HIPPIE PPi parsing, in sif format. accepted formats: sif.
### i / o arguments
syntax: input_argument (datatype) : definition

config input / output arguments for this building block:
* **input_file_path1** (*string*): Path for the HIPPIE database downloaded locally.
* **input_file_path2** (*string*): Path for the HIPPIE genes to be parsed in the HIPPIE PPi database.
* **output_sif_path** (*string*): Path for the resulting panda dataframe from the HIPPIE PPi parsing. File type: csv, json, tsv, xml. [sample file](https://urlto.sample). Accepted formats: sif.
### config
syntax: input_parameter (datatype) - (default_value) definition

config parameters for this building block:

* **hippie_score** (*str*) - HIPPIE score used as filter, based on the number of studies, experimental techniques and their quality to measure the interaction detected.
* **disgenet_score** (*str*) - DisGenet score used as a filter, gene-disease/variant-disease/disease-disease range scores to consider as minimal value of quality from the DisGenet retrieval. 

#### [common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.yml)
```python
properties:
	hippie_score: 0.2 
	disgenet_score: 0.8
```
#### command line
```python
parsehippie --config config.yml --input_file_path1 /path/to/hippieDatabase.txt --input_file_path2 /path/to/hippieHumanGenes.txt --output_file_path interactome.sif
```



## Making Nodes
biobb_netprop Making Nodes using NetworkX wrapper.
### Get help
Command:
```python
maknodes -h
```
    usage: maknodes [-h] [--config CONFIG] --input_file_path1 INPUT_FILE_PATH1 --input_file_path2 INPUT_FILE_PATH2 --input_file_dataset INPUT_FILE_DATASET --output_sif_path OUTPUT_SIF_PATH

    Parsing the HIPPIE database using the Human genome as reference.

    optional arguments:
      -h, --help            show this help message and exit
      --config config       configuration file

    required arguments:
      --input_file_path1 input_file_path
                            Path for the panda dataframe, coming out of the **Parse Hippie** wrapped function.
      --input_file_path2 input_file_path
                            Path for the GDA/VDA retrieval attributes and genes, coming out of the DisGenet wrapped functions.
      --input_file_dataset input_file_dataset
                            Path for the DisGenet database, curated or not, **downloaded locally on its own**.
      --output_sif_path output_sif_path
                            Path for the resulting panda dataframe from the HIPPIE PPi and DisGenet genes coupling, in sif format. Accepted formats: sif.
### i / o arguments
syntax: input_argument (datatype) : definition

config input / output arguments for this building block:
* **input_file_path1** (*string*): Path for the panda dataframe, coming out of the **Parse Hippie** wrapped function.
* **input_file_path2** (*string*): Path for the GDA/VDA retrieval attributes and genes, coming out of the DisGenet wrapped functions.
* **input_file_dataset** (*string*): Path for the DisGenet database, curated or not, **downloaded locally on its own**.
* **output_sif_path** (*string*): Path for the resulting panda dataframe from the HIPPIE PPi and DisGenet geens coupling. File type: sif. [sample file](https://urlto.sample). Accepted formats: sif.
### config
syntax: input_parameter (datatype) - (default_value) definition

config parameters for this building block:

* **curated** (*bool*) - (True) Choosing the curated or not database version
* **disease_id** (*str*) - ("sample") Disease ID used in DisGenet retrieval.
* **disgenet_score** (*str*) - (0.0) Score that was used in the DiGenet retrieval.
* **scoring_mode** (*str*) - ("sample") Defining the Scoring system to be used to rate the PPI Network, can be **dis** (considering the DisGenet Score), **norm_dis** (considering the normalized DisGenet Score), **binary**.


#### [common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.yml)
```python
properties:
        curated: True
	disease_id: C0002352
        disgenet_score: 0.8
	scoring_mode: dis
```
#### command line
```python
maknodes --config config.yml --input_file_path1 /path/to/interactome.sif --input_file_path2 /path/to/GDAVDAGenes.txt --input_file_dataset /path/to/disgenetDatabase --output_sif_path interactome.sif
```

## Call NetProp
biobb_netprop GUILD wrappper, for network-based prioritization framework to unveil genes associated with a disease phenotype (disease-genes).
### Get help
Command:
```python
call_netprop -h
```
    usage: call_netprop [-h] [--config CONFIG] --input_file_path1 INPUT_FILE_PATH1 --input_file_path2 INPUT_FILE_PATH2 --input_netprop_dir INPUT_NETPROP_DIR --output_file_path OUTPUT_FILE_PATH

    Parsing the HIPPIE database using the Human genome as reference.

    optional arguments:
      -h, --help            show this help message and exit
      --config config       configuration file

    required arguments:
      --input_file_path1 input_file_path
                            Path for the HIPPIE PPi and DisGenet genes parsed, coming out of the NetworkX wrapper function.
      --input_file_path2 input_file_path
                            Path for the HIPPIE PPi dataframe, coming out of the **maknodes** wrapped function.
      --input_netprop_dir input_netprop_dir
                            Path for the GUILD dir.
      --output_file_path output_file_path
                            Path for the resulting TXT column file the GUILD PPi algorithm. Accepted formats: txt.
### i / o arguments
syntax: input_argument (datatype) : definition

config input / output arguments for this building block:
* **input_file_path1** (*string*): Path for HIPPIE PPi and DisGenet genes parsed, coming out of the **NetworkX** wrapper function.
* **input_file_path2** (*string*): Path for the HIPPIE PPi dataframe, coming out of the **maknodes** wrapped function.
* **input_netprop_dir** (*string*): Path for the GUILD dir, **dowloaded locally**.
* **output_file_path** (*string*): Path for the resulting panda dataframe from the HIPPIE PPi and DisGenet geens coupling. File type: sif. [sample file](https://urlto.sample). Accepted formats: sif.
### config
syntax: input_parameter (datatype) - (default_value) definition

config parameters for this building block:

* **algorithm** (*string*) - Choosing the reference algorithm for GUILD to be used, can be **s** for NetScore, or **z** for NetZScore.

#### [common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_container.yml)
```python
properties:
        algorithm: 's'
```
#### command line
```python
call_netprop --config config.yml --input_file_path1 /path/to/interactome.sif --input_file_path2 /path/to/GDAVDAGenes.txt --input_file_dataset /path/to/disgenetDatabase --output_sif_path interactome.sif
```
