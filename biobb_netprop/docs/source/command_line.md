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

* **retrieve_by** (*str*) - Configuration params to pass for the retrieval of the association on the REST API (gene, uniprot_entry, disease, source, evidences_gene, evidences_disease).            
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

* **retrieve_by** (*str*) - Configuration params to pass for the retrieval of the association on the REST API (gene, uniprot_entry, disease, source, evidences_gene, evidences_disease).
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
vda_disgenet --config config.yml --input_file_path /path/to/working/dir --output_file_path vda_results.file
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
vda_disgenet --config config.json --input_file_path /path/to/working/dir --output_file_path vda_results.file
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

* **retrieve_by** (*str*) - Configuration params to pass for the retrieval of the association on the REST API (gene, uniprot_entry, disease, source, evidences_gene, evidences_disease).
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
dda_disgenet --config config.yml --input_file_path /path/to/working/dir --output_file_path dda_results.file
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
dda_disgenet --config config.json --input_file_path /path/to/working/dir --output_file_path dda_results.file
```





























## Template
Short description for the template module in Restructured Text (reST) syntax. Mandatory.
### Get help
Command:
```python
template -h
```
    usage: template [-h] [--config CONFIG] --input_file_path1 INPUT_FILE_PATH1 [--input_file_path2 INPUT_FILE_PATH2] --output_file_path OUTPUT_FILE_PATH
    
    Description for the template module.
    
    optional arguments:
      -h, --help            show this help message and exit
      --config CONFIG       Configuration file
      --input_file_path2 INPUT_FILE_PATH2
                            Description for the second input file path (optional). Accepted formats: dcd.
    
    required arguments:
      --input_file_path1 INPUT_FILE_PATH1
                            Description for the first input file path. Accepted formats: top.
      --output_file_path OUTPUT_FILE_PATH
                            Description for the output file path. Accepted formats: zip.
### I / O Arguments
Syntax: input_argument (datatype) : Definition

Config input / output arguments for this building block:
* **input_file_path1** (*string*): Description for the first input file path. File type: input. [Sample file](https://urlto.sample). Accepted formats: TOP
* **input_file_path2** (*string*): Description for the second input file path (optional). File type: input. [Sample file](https://urlto.sample). Accepted formats: DCD
* **output_file_path** (*string*): Description for the output file path. File type: output. [Sample file](https://urlto.sample). Accepted formats: ZIP
### Config
Syntax: input_parameter (datatype) - (default_value) Definition

Config parameters for this building block:
* **boolean_property** (*boolean*): (True) Example of boolean property..
* **executable_binary_property** (*string*): (zip) Example of executable binary property..
* **remove_tmp** (*boolean*): (True) Remove temporal files..
* **restart** (*boolean*): (False) Do not execute if output files exist..
### YAML
#### [Common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template.yml)
```python
properties:
  boolean_property: false
  remove_tmp: true

```
#### [Singularity config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_singularity.yml)
```python
properties:
  boolean_property: false
  container_image: bioexcel-zip_container-master-latest.simg
  container_path: singularity
  container_volume_path: /tmp
  executable_binary_property: /opt/conda/bin/zip
  remove_tmp: false

```
#### Command line
```python
template --config config_template.yml --input_file_path1 urlto.sample --input_file_path2 urlto.sample --output_file_path urlto.sample
```
### JSON
#### [Common config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template.json)
```python
{
  "properties": {
    "boolean_property": false,
    "remove_tmp": true
  }
}
```
#### [Singularity config file](https://github.com/bioexcel/biobb_template/blob/master/biobb_template/test/data/config/config_template_singularity.json)
```python
{
  "properties": {
    "boolean_property": false,
    "remove_tmp": false,
    "executable_binary_property": "/opt/conda/bin/zip",
    "container_path": "singularity",
    "container_image": "bioexcel-zip_container-master-latest.simg",
    "container_volume_path": "/tmp"
  }
}
```
#### Command line
```python
template --config config_template.json --input_file_path1 urlto.sample --input_file_path2 urlto.sample --output_file_path urlto.sample
```
