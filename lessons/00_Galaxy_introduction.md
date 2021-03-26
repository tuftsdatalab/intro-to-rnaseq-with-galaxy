## Introduction to Galaxy

We will spend some time getting familiar with the Galaxy interface and layout and key functions that can be performed using Galaxy. We will be using a small subset of the data we will be using for the RNA-Seq workflow to better understand how Galaxy works with an individual dataset.

### Galaxy UI

The Galaxy User Interface has a top menu bar and three panels: Tools, Main, and History.

<img src="../img/ui1.png" width="700">

## Key Galaxy actions to be familiar with (cite galaxy training materials here)

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
3. Paste in the address of a file: https://zenodo.org/record/582600/files/mutant_R1.fastq
4. Click **Start**
5. Click **Close**
6. Your uploaded file is now in your current history. When the file has uploaded to Galaxy, it will turn green.

### 3. Viewing your data
1. Click on the eye icon next to the dataset name, to look at the file content

<img src="../img/eye-icon.png" width="200">

The contents of the file will be displayed in the central Galaxy panel.
This file contains DNA sequencing reads from a bacteria, in FASTQ format:

<img src="../img/fastq.png" width="500">

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

<img src="../img/fastqc-out.png" width="500">

This tool has summarised information about all of the reads in our FASTQ file.

[Next: Setup](01_Introduction_and_Setup.md)
[Previous: Repository Home](../README.md)
