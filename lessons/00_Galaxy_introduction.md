# Introduction to Galaxy

Galaxy is a web-based platform for running data analysis and integration, geared towards bioinformatics.
- Open-source, public servers
- Developed at Penn State, Johns Hopkins, OHSU and Cleveland Clinic with many more outside contributions
- Large and extremely responsive community 


## Galaxy on the Tufts University High Performance Compute (HPC) Cluster

- Our Galaxy server runs on the HPC cluster, storing data on HPC drives and using compute nodes and Slurm scheduler to run user jobs
- In practice, this means that Tufts users have more resources on Tufts' Galaxy compared to public servers
- More information on getting access to Tufts Galaxy can be found on the [Research Technology website](https://it.tufts.edu/research-technology/bioinformatics/tufts-galaxy)

<img src="../img/galaxy_hpc.png" width="700">


## Galaxy UI

- We'll spend some time getting familiar with the Galaxy interface, layout, and key functions that can be performed using Galaxy 
- The Galaxy User Interface has a top menu bar and three panels: Tools, Main, and History

<img src="../img/ui1.png" width="700">

### Histories

- Histories are where a dataset and a set of analysis are stored
- Similar to a "working directory".
- You can have multiple histories under the same account and you can view them all by clicking the **+** as shown below

<img src="../img/viewhistory.png" width="700">


- Here you can view all your histories, switch to another history, and drag and drop data between histories.

<img src="../img/histories.png" width="700">


### Uploading Data

- Data can be uploaded to Galaxy in a number of ways by clisking the "Upload" icon on the top of the Tools panel.

<img src="../img/upload.png" width="700">

- "Choose local File" will select a file from your local computer, and "Choose FTP File" will select from your user drive on the HPC cluster, which has an extension "/cluster/tufts/galaxy/xfer/username" 
<img src="../img/upload2.png" width="700">


### Uploading Data

When it comes time to use a tool, either search or click the category the tool you need would fall under.

<img src="../img/tools.png" width="700">


Click the name of the tool you would like to use and it's customizable parameters will appear in the center area.

<img src="../img/featurecounts.png" width="700">

### 3. Page logistics

You can expand and shrink any of the panels by clicking the small arrows and dragging the three small lines in the bottom left and right corners of the page. To get back to the home page click the logo next to **Galaxy Tufts** on the top left of the page or the **Analyze Data** tab on the top of the page. 

<img src="../img/bottomarrows.png" width="700">

## Key Galaxy actions to be familiar with 

For these activities we will be using a single file from the larger dataset that we will use later on in the workshop. Some of the training material in this section was borrowed from [this](https://training.galaxyproject.org/training-material/topics/introduction/tutorials/galaxy-intro-short/tutorial.html#citing-this-tutorial) webpage.

### 1. Naming your current history
1. Go to the **History** panel (on the right)
2. Click on the history name (which by default is “Unnamed history”)

<img src="../img/rename_history.png" width="200">

3. Type in a new name, for example, “My-Analysis”
4. Press **Enter** on your keyboard to save it

### 2. Upload a file
1. At the top of the **Tools** panel (on the left), click **galaxy-upload** Upload

<img src="../img/upload-data2.png" width="200">

This brings up a box:


<img src="../img/upload-box.png" width="500">

2. Click **Paste/Fetch data**. Files can also be uploaded from your local machine or through the Tufts Cluster using the FTP option.
3. Paste in the address of a file: https://zenodo.org/record/4666785/files/HIV_12hr_rep1_pass_subsample.fastq.gz.fastqsanger?download=1
4. Click **Start**
5. Click **Close**
6. Your uploaded file is now in your current history. When the file has uploaded to Galaxy, it will turn green.

### 3. Viewing your data
1. Click on the eye icon next to the dataset name, to look at the file content

<img src="../img/eye-icon.png" width="200">

The contents of the file will be displayed in the central Galaxy panel.
This file contains DNA sequencing reads from HIV infects CD4+ T cells, in FASTQ format:

<img src="../img/HIV_12hr_rep1_pass_subsample.fastq.gz.png" width="500">

### 4. Use a tool
1. Type **FastQC** in the tools panel search box (top)
2. Click on the **Fastqc** tool
        The tool will be displayed in the central Galaxy panel.
3. Select the following parameters:
        - “Short read data from your current history”: the FASTQ dataset that we uploaded
        - No change in the other parameters
4. Click **Execute**

This tool will run and two new output datasets will appear at the top of your history panel.
### 5. View results
We will look at the output dataset called *FastQC on data 1: Webpage*.

1. Click on the eye icon next to the “Webpage” output dataset.
The information is displayed in the central panel

<img src="../img/fastqc_out.png" width="500">

This tool has summarised information about all of the reads in our FASTQ file.

[Next: Setup](01_Introduction_and_Setup.md)

[Previous: Repository Home](../README.md)
