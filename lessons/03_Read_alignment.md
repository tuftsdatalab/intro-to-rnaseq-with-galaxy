# Read Alignment


- RNAseq data originates from spliced mRNA (no introns)
- When aligning to the genome, our aligner must find a spliced alignment for reads
- We use a tool called STAR (Spliced Transcripts Alignment to a Reference) that has a exon-aware mapping algorithm.

<img src="../img/spliced_alignment.png" width="300">

[Image Source](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3530905/)


## SAM format
STAR produces a file in Sequence Alignment Map (SAM) format

<img src="../img/sam_format.jpeg" width="800">

[Image Source](www.samformat.info)


## Genome Annotation Standards
- STAR can use an annotation file gives the location and structure of genes in order to improve alignment in known splice junctions 
- Annotation is dynamic and there are at least three major sources of annotation 
- The intersection among RefGene, UCSC, and Ensembl annotations shows high overlap. RefGene has the fewest unique genes, while more than 50% of genes in Ensembl are unique 
- Be consistent with your choice of annotation source! 

<img src="../img/annotation_source.png" width="500">

[Image Source](https://bmcgenomics.biomedcentral.com/articles/10.1186/s12864-015-1308-8)


## Align the reads to the human genome using STAR aligner
- In the **Tools** panel search bar, type **STAR**
- Scroll down and select **RNA STAR** under **RNA-seq**
- Under **RNA-Seq FASTQ/FASTA file** click the <img src="../img/download.png" width="15"> and select the trimmed reads **42: Trim Galore! on collection 12: trimmed reads**
- **STAR** gives us the option of using a genome that includes a database of known splice junction locations or providing a gtf file so that STAR can create the database. We’ll select a reference genome on our server that includes the splice junctions. Under **Reference genome with or without an annotation** select **use genome reference with built-in gene-model**.
- Under **Select reference genome** select **hg38-with-genes**.
- The final configuration should look like this: 

<img src="../img/STARconfig.png" width="800">

- Scroll down and click **Execute**
- The result will be three collections, giving the bam, splice junctions and log files for the alignments

<img src="../img/STARresult.png" width="200">

## Run MultiQC on the STAR log files to check the result of the alignment

- Follow the steps from the [previous section](03_Process_raw_reads.md) to run MultiQC except: 
	- Under **Which tool was used generate logs?**  select **STAR**
	- Under **STAR log output** click the <img src="../img/download.png" width="15"> and select the collection **83: RNA STAR on collection 42:log**
- After the job finished, click the <img src="../img/download.png" width="15"> to view the webpage.

<details>
<summary><b>Question 6: In RNAseq, the percentages of uniquely aligned reads are typically lower than for DNAseq, but are expected to be above 75%. Are the percent alignments reasonable for RNAseq? You can optionally check to see which percentage of the reads align to the HIV genome by re-running STAR using the HIV genome with built-in gene model hiv_nc001802 </b></summary>
<br>
</details> 

[Next: Gene Quantification](04_Gene_quantification.md)

[Previous: Process Raw Reads](02_Process_raw_reads.md)
