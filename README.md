# Michigan Data Interface

The [Michigan Data Interface](https://midataint.github.io/) (MDI) 
is a framework for developing, installing and running a variety of 
HPC data analysis pipelines and interactive R Shiny data visualization 
applications within a standardized design and implementation interface.

Data analysis in the MDI is separated into 
[two stages of code execution](https://midataint.github.io/docs/analysis-flow/) 
called Stage 1 HPC **pipelines** and Stage 2 web applications (i.e., **apps**).
Collectively, pipelines and apps are referred to as **tools**.

## Repository contents

This repository carries a template to create a folder
intended to carry a **collection of Stage 1 Pipeline data scripts**, 
i.e., <code>\<data\>.yml</code> files, a.k.a. job configuration scripts. 

The template 
has no specificity regarding the kind of scripts the folder will carry, 
i.e., it has no connection to any specific tool suite.  Its purpose is to 
provide a properly constructed <code>.gitignore</code> file that will
allow you to back up your data scripts to GitHub while excluding the 
potentially large files found in hidden <code>.\<data\>.yml</code>
folders that carry certain job status and log files.

Thus, a repository maintained after copying this template can track the
state of scripts that were called to do work, but will not itself have 
a record of any output from the jobs run with those scripts. Importantly, 
such information can be found in the log file subfolder of the 
OUTPUT_DIR/DATA_NAME folder for each job (or in the server directory
where the data scripts folder is located).

## Template usage

### Create a new repository from this template

**To get started quickly**, 
[click here to create a new data script repository from this template](https://github.com/MiDataInt/mdi-data-scripts-template/generate).

You will be prompted for the user and name of the repository you would like 
to create. We recommend that you use **NAME-data-scripts** as the name of your 
repository, replacing 'NAME' with a specific, informative name of your choosing.
That name could reflect whatever organization makes sense to you for coordinating
some collection of related data scripts. For example, you might make a folder/repo
to hold all data scripts for a publication, for a single pipeline, etc.

### Clone the new repository to your HPC server

```bash
git clone https://github.com/GIT_USER/NAME-data-scripts
```

## Repository usage

### Backup up your data scripts to GitHub

After populating the directory with data scripts, executing them, etc., simply
use git as you would for any repository, e.g.

```bash
cd NAME-data-scripts
git add .
git commit -m 'commit message'
git push
```

### Folder contents

You can use whatever substructure you would like to organize a specific 
data scripts folder/repository, they will all be included. Just remember
that all hidden folders and files starting with a dot, e.g., '.xxx' will
be excluded from the repository on GitHub.

### Transferring data scripts

Once your data scripts are on GitHub, it is a simple matter to transfer
them to another server, file location, etc. by recloning the repo into
the new location. You may then execute your data scripts again in that new 
context.  For more limited transfers, a simple "copy and paste" works too!
