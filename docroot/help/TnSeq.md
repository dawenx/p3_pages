# Tn-Seq Analysis

## Parameters

### Strategy
This parameter determines whether the genes are determined to be
essential in a single condition or by comparison to a control.

#### Essential
Runs the
[TRANSIT](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1004401)
software. With this strategy selected TRANSIT will calculate the
probability of being essential using the Gumbel or Extreme Value
distribution.

#### Conditionally Essential
Runs the
[TRANSIT](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1004401)
software. With this strategy selected TRANSIT will operate in
"resampling" mode and use the difference between the sum of read-counts
in each condition to calculate the probability of being essential.

### Output Folder
The workspace folder where results will be placed.

### Output Name
Name used to uniquely identify results.

## Paired read library

### Read File 1 & 2
Many paired read libraries are given as file pairs,
with each file containing half of each read pair. Paired read files are
expected to be sorted such that each read in a pair occurs in the same
Nth position as its mate in their respective files. These files are
specified as READ FILE 1 and READ FILE 2. For a given file pair, the
selection of which file is READ 1 and which is READ 2 does not matter.

### Condition
The group/condition specified will be used to determine contrasts in the
conditionally essential mode. Reads assigned to the same group will be
used as replicates. Choose whether the sample is a treatment or control.

## Selected Libraries
Read files placed here will contribute to a single Tn-Seq analysis.
Read files placed into this table under the same condition will be considered replicates.
