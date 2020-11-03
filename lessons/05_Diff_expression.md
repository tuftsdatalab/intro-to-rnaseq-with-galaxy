## Run DESeq2 to test for differential expression between Mock and HIV at 12 hr

### In preparation to run DESeq2, create separate collections for the counts files for Mock 12 hr and HIV 12 hr.
- In the **Tools** panel search bar, type **Apply Rule to Collection**
- Choose **125:featureCounts on collection 85: Counts**
- Click **Edit**
- Click Filter, then **Using a Regular Expression**
- Under **Regular Expression?**, type HIV_12 (Do not put any extra spaces following the expression). This is a regular expression which will match any file that contains the string **HIV_12**
- Click Apply and the list of files in column A should show three samples:

<img src="../img/HIV_12.png" width="300">

- Click **Rules**, and then **Add/Modify Column Definitions** 
- Click **Add** Definition, then **List Identifier(s)**, select **A**, click Apply
- Click **Save**
- Click **Execute**
- Rename the collection by clicking to expand the collection, then clicking on the title, typing **HIV_12** , and pressing enter.

<img src="../img/HIV_12_rename.png" width="300">

- Do the same for Mock 12 hour samples, and modify the regular expression appropriately.
- The two collections should appear in the history (you may have to refresh history in order to see the names)

<img src="../img/rename_collection.png" width="300">

### Test for Differential Expression using DESeq2using the datasets we created in step 14.
- In the **Tools** panel search bar, type **DESeq2** and select **DESeq2** under **RNA-seq**
- Under **1: Factor** , specify the factor name **Condition**
- Under **1: FactorLevel**, specify the base factor level **Mock**
- Under **Counts file(s)** select the folder icon and select the **Mock_12** collection
- Set the **2: FactorLevel** to **HIV**
- Under **Counts file(s)** select the folder icon and select the **HIV_12** collection
- Set **Output normalized counts table** to **Yes**
- Scroll down and click **Execute**
- **DESeq2** will produce three output files: A normalized counts table, a plots file, and a results file.

<img src="../img/deseq2_output.png" width="300">

### View and interpret DESeq2 output files
- Results file: View the results table by clicking on the history item **DESeq2 result file on data ... and others** and clicking on the eye icon.

<details>
<summary><b> Question 10: What are the top two most significant genes </b></summary>
<br>
</details>

- Plots: View the plots by clicking on the history item **DESeq2 plots on data ... and others** and clicking the eye icon.

<details>
<summary><b> Question 11: What observations can you make from the PCA plot? Do samples cluster as expected?</b></summary>
<br>
</details>

The p-value plot shows a histogram of p-values for all the genes that were examined. P-values give the probability of getting a logFC as extreme as observed if the true logFC = 0 for that gene (null hypothesis).  Random P-values are expected to be uniform, if you have true positives you should see a peak close to zero.

<img src="../img/pval.png" width="300">  

[Image Source](http://varianceexplained.org/statistics/interpreting-pvalue-histogram/)

<details>
<summary><b> Question 12: What observation can you make about the pvalue distribution, does it look like there are many true significant results? Note that the published dataset has been downsampled for instructional purposes. </b></summary>
<br>
</details>

[Previous: Gene quantification](04_Gene_quantification.md)