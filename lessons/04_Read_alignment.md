## Align the reads to the human genome (version hg38) using STAR aligner
- In the **Tools** panel search bar, type **STAR**
- Scroll down and select **RNA STAR** under **RNA-seq**
- Under **RNA-Seq FASTQ/FASTA file** click the folder icon and select the trimmed reads **42: Trim Galore! on collection 12: trimmed reads**
- **STAR** gives us the option of using a genome that includes a database of known splice junctionlocationsor providing a gtf file so that STAR can create the database. We’ll select a reference genome on our server that includes the splice junctions. Under **Reference genome with or without an annotation** select **use genome reference with built-in gene-model**.
- Under **Select reference genome** select **hg38-with-genes**.
- The final configuration should look like this: 

<img src="../img/STARconfig.png" width="800">

- Scroll down and click **Execute**
- The result will be three collections, giving the bam, splice junctions and log files for the alignments

<img src="../img/STARresult.png" width="200">

## Run MultiQC on the STAR log files to check the result of the alignment
- Follow the steps from the previous run of MultiQC except: 
- Under **Which tool was used generate logs?**  select **STAR**
- Under **STAR log output** click the folder icon and select the collection **83: RNA STAR on collection 42:log**
- After the job finished, view the webpage.

<details>
<summary><b>Question 6: RNAseq unique alignment percentages are typically lower than for DNAseq but are expected to be above 75%. Are the percent alignments reasonable for RNAseq?</b></summary>
<br>
Answer: The HIV 24 hour samples don’t pass this threshold. This could potentially be due to HIV replication in the cells which we will check in the next lab.
</details> 

[Next: Gene Quantification](05_Gene_quantification.md)

[Previous: Process Raw Reads](03_Process_raw_reads.md)
