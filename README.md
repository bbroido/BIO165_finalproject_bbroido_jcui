Inflammation-Related Gene Expression Responses to Fear Exposure: Tagap Upregulation in the Mouse Medial Prefrontal Cortex\
Jason Cui and Blythe Broido

Background:
- Chen, M.B. et al 2020 include four conditions of mice, each of which receives a different set of fear conditioning stages. The fear conditioning procedure used in Chen, M.B. et al 2020 was as follows: mice are removed from their home cage and placed into a fear cage, where they receive a foot shock and hear a tone. Mice are placed back into their home cage, and 16 days later, are reintroduced to the fear cage (recall stage).
- 4 Fear Conditions:
    - Homecage: mice that were only exposed to their home cage
    - Recall Only: mice that were moved into the fear cage, but did not receive the shock
    - Fear Only: mice that were moved into the fear cage and received the shock, but were not put through the recall context
    - Fear Conditioned: mice that underwent the full fear conditioning model, including the shock and recall phases

For our purposes, we are interested in only the fear variable. As such, we classified the four conditions into two categories.
  - Fear: Fear Conditioned and Fear Only
  - No fear: Recall Only and Homecage

We used DESeq2 to conduct differential gene expression analysis.
Threshold:
  - log2 fold-change of ±1
  - Benjamini-Hochberg adjusted p-value with an alpha of 0.005

Specifically identified genes that are upregulated in fear exposure conditions (Homecage/Recall versus Fear Only/Fear Conditioned) **and** were not differentially expressed between Homecage and Recall Only mice.

Data:
- The raw data (normalized gene count data pulled directly from Chen, M.B. et al. 2020) is uploaded under the file name neuronal_transcriptomic.csv
- Segmentation of the raw dataset into the relevant samples for each of the 4 fear conditions was performed. The results of these are four dataframes, one for each fear condition.
      - Homecage_Genes.csv (Homecage only)
      - Context_Genes.csv (Recall Only)
      - Fearonly_Genes.csv (Fear Only)
      - FearConditioned_Genes.csv (Fear Conditioned)
  
Code:
- data_analysis_structuring.ipynb: To segment the raw dataset into the relevant samples for each of the 4 fear conditions. Also transposes the data to put genes as columns and samples as rows.
- data_visualization.ipynb: Code to run differential gene analysis, and create volcano plots and violin plot
