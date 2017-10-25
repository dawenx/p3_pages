# Genome Assembly

## Selected libraries
Read files placed here will contribute to a single assembly.

## Paired read library

### Read File 1 & 2
Many paired read libraries are given as file pairs, with each file containing half of each read pair. Paired read files are expected to be sorted such that each read in a pair occurs in the same Nth position as its mate in their respective files. These files are specified as READ FILE 1 and READ FILE 2. For a given file pair, the selection of which file is READ 1 and which is READ 2 does not matter.

### Advanced Parameters

#### File 1 Interleaved
Some paired libaries are available in a single file where each read in a pair occurs in succession. To specify such a file set this parameter to 'True'.

#### Mean Insert Size
This refers to the mean insert size between paired reads. If you have this information you may provide it. If not the assembly algorithm will make an attempt to determine this value.

#### Std. Insert Size
This refers to the standard deviation of the insert size between paired reads. If you have this information you may provide it. If not the assembly algorithm will make an attempt to determine this value.

#### Mate Paired
Defines the orientation of read pairs. Setting Mate Paired to true indicates that the sequencing direction of the two reads in each pair is outward facing.

#### Platform
The sequencing platform used for each library.
  - infer: Infer sequencing platform from read files
  - illumina: Illumina short reads
  - pacbio: PacBio long reads
  - nanopore: MinION long reads

## Parameters

### Benchmark Contigs

This parameter can be used to specify a FASTA contigs file to evaluate the assembly against.

### Output Folder

The workspace folder where results will be placed.

### Output Name

Name used to uniquely identify results.

### Assembly Strategy

#### auto
  * For short reads:
    1. Runs BayesHammer on reads
    2. Assembles with Velvet, IDBA and SPAdes
    3. Sorts assemblies by ARAST quality score

  * For long reads (PacBio or Nanopore):
    1. Assembles with MiniASM

#### fast
  1. Assembles with MEGAHIT and Velvet.
  2. Results are sorted by ARAST quality score.

#### full_spades
1. Runs BayesHammer on reads
2. Assembles with SPAdes.

#### kiki
1. Runs the Kiki assembler

#### miseq
1. Runs Velvet with hash length 35.
2. Runs BayesHammer on reads and assembles with SPAdes with k up to 99.
3. Results are sorted by ARAST quality score.
4. Works for Illumina MiSeq reads.

#### plasmid
1. Runs BayesHammer on reads and assembles with plasmidSPAdes.

#### smart
- For short reads:
  1. Runs BayesHammer on reads, Kmergenie to choose hash-length for Velvet
  2. Assembles with Velvet, IDBA and SPAdes
  3. Sorts assemblies by ALE score
  4. Merges the two best assemblies with GAM-NGS

- For long reads (PacBio or Nanopore):
  1. Assembles with MiniASM
