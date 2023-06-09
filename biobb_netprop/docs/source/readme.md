[![](https://readthedocs.org/projects/biobb-netprop/badge/?version=latest)](https://biobb-netprop.readthedocs.io/en/latest/?badge=latest)

# biobb_netprop

## Introduction
Biobb_NetProp is a complete code containing singular function for the DisGenet retrieval, the HIPPIE PPi database and the NetworkX for producing a prioritize PPi network, based on the gene/variants/disease attributes coming out of DisGenet.
Biobb (BioExcel building blocks) packages are Python building blocks that create new layer of compatibility and interoperability over popular bioinformatics tools.
The latest documentation of this package can be found in our readthedocs site:
[latest API documentation](http://biobb_netprop.readthedocs.io/en/latest/).

## Version
v1.0.0 2022.4

## Installation

If you have no experience with anaconda, please first take a look to the [New with anaconda?](https://biobb-documentation.readthedocs.io/en/latest/first_steps.html#new-with-anaconda) section of the [official documentation](https://biobb-documentation.readthedocs.io/en/latest/).

### Download repository

Although the biobb_netprop repository is available at GitHub and thus you can clone it, we strongly recommend you to [**download it compressed**](https://github.com/bioexcel/biobb_netprop/archive/master.zip) and start your new project from scratch. 

### Create new conda environment

Once you have the project unzipped in your computer, please follow the next steps to create a new conda environment:

```console
cd biobb_netprop
conda env create -f conda_env/environment.yml
```

### Update environment paths

Edit **conda_env/biobb_netprop.pth** with the paths to your *biobb_netprop* folder. Example:

```console
/home/user_name/projects/biobb_netprop/
/home/user_name/projects/biobb_netprop/biobb_netprop/biobb_netprop
```

Copy the edited **conda_env/biobb_netprop.pth** file to the site-packages folder of your environment. This folder is in */[anaconda-path]/envs/biobb_netprop/lib/python3.7/site-packages*, where */[anaconda-path]* is usually */anaconda3* or */opt/conda*.

```console
cp conda_env/biobb_netprop.pth /[anaconda-path]/envs/biobb_netprop/lib/python3.7/site-packages
```

### Activate environment

Then, activate the recently created *biobb_netprop* conda environment:

```console
conda activate biobb_netprop
```

### Create repository

This directory includes some folders not standard for a biobb, such as **biobb_netprop/adapters/**, **biobb_netprop/notebooks/** or **conda_env/**. For the sake of having a pure biobb structure, you should uncomment the three last lines of the **.gitignore** file before creating a new git repository:

```console
biobb_netprop/adapters
biobb_netprop/notebooks
conda_env
```
Then, inialitize repository:

```console
git init
```

### Binary paths configuration

Additionally, it's recommendable to configure binary paths in your environment in order to ease the command line execution. More info about this subject in the [Binary path configuration](https://biobb-documentation.readthedocs.io/en/latest/execution.html#binary-path-configuration) section of the [official documentation](https://biobb-documentation.readthedocs.io/en/latest/).

## Documentation

[Click here to find the API Documentation example](https://biobb-netprop.readthedocs.io/en/latest/netprop.html) for this netprop and [here for Command Line documentation](http://biobb_netprop.readthedocs.io/en/latest/command_line.html).

And here you can find [the full documentation](https://biobb-documentation.readthedocs.io/en/latest/) about how to build a new **BioExcel building block** from scratch.

## Copyright & Licensing
This software has been developed in the [MMB group](http://mmb.irbbarcelona.org) at the [BSC](http://www.bsc.es/) & [IRB](https://www.irbbarcelona.org/) for the [European BioExcel](http://bioexcel.eu/), funded by the European Commission (EU H2020 [823830](http://cordis.europa.eu/projects/823830), EU H2020 [675728](http://cordis.europa.eu/projects/675728), ITN Disc4All [955735](http://cordis.europa.eu/projects/675728)).
* (c) 2015-2020 [Barcelona Supercomputing Center](https://www.bsc.es/)
* (c) 2015-2020 [Institute for Research in Biomedicine](https://www.irbbarcelona.org/)

Licensed under the
[Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0), see the file LICENSE for details.

![](https://bioexcel.eu/wp-content/uploads/2019/04/Bioexcell_logo_1080px_transp.png "Bioexcel")
