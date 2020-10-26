## Check raw read quality with FastQC
- In the **Tools** panel (left most panel) search bar, type **FastQC**
- Select **FastQC** under **FASTQ Quality Control**
- In the middle panel, under **Short read data from your current history** select the folder icon and **chang_2011** should appear as an option

<img src="../img/fastqc1.png" width="700">

- Scroll down and click **Execute**.The job should first appear orange and then green after a minute or so.
- The result will be two lists, one containing the raw data and one the webpage (html) results.

<img src="../img/fastqc2.png" width="200">

- Click to expand the list **FastQCon collection 12: Webpage** and click on the **eye icon** next to the first file for sample **HIV_12hr_rep1**.Read the table for **Basic Statistics**.

<details>
<summary><b>Question 2: Were you right about your guess of quality encoding? </b></summary>
<br>
Answer: yes
</details>


## Aggregate QC data with **MultiQC**
- In the **Tools** panel search bar, type **MultiQC**
- Select **MultiQC** under **FASTQ Quality Control**
- In the middle panel, under **Which tool was used generate logs?** select **FastQC**
- Under **FastQC output** click the <img src="../img/download.png" width="70"> and select the collection **14: FastQC on collection 12: Raw Data** (note that the numbers 14 and 12 are tracking the dataset number in your history and might vary if you have not followed the exact sequence in this document)
- Enter the **Report Title** “Raw data QC”
- Scroll down and click **Execute**.
- The result will again be two collections (you may have to click "back to rnaseq day 1" on the top of the History panel). Select the collection titled **MultiQC on data 36, data 34, and others: Webpage** and click the eye icon to view.

<details>
<summary><b>Question 3: Using what we learned in lecture, which metrics show one or more failed samples?</b></summary>
<br>
Answer: GC content and Adapters</details>

## Trim adapters and low quality read ends with Trim Galore!
- In the **Tools** panel search bar, type **Trim Galore!**
- Select **Trim Galore!** under **FASTQ Quality Control**
- Under **Reads in FASTQ format** click the folder icon and select **chang_2011**
- Scroll down and click **Execute**.
- The result will be a single collection titled **Trim Galore! on collection 12: trimmed reads**.Next, we’llrerun FastQC in order to see how the trimming performed

## Rerun FastQC and MultiQC
- Follow the steps in 5 and 6 above, except select the trimmed reads generated in step 7as the input to **FastQC**

<details>
<summary><b>Question 4: Were any reads completely removed from the samples?</b></summary>
<br>
Answer: no
</details>

<details>
<summary><b>Question 5: Is the adapter problem solved?What about the GC content?</b></summary>
<br>
Answer: The adapter problem is solved, but not the GC problem. The HIV 24 hour samples still failed the GC content check. Both Human and HIV are GC-poor genomes (Human reference genome is AT (60%) and GC(40%), much like HIV-1 genomes (strain HXB2: 57% AT, 43%GC)).These could be low quality samples.
</details>


[Next: Read Alignment](04_Read_alignment.md)

[Previous: Setup](02_Setup.md)
