# TCPro
TCPro
TCPro – The T Cell Proliferator

The US FDA, Center for Biologics Evaluation and Research
2019
TCPro – The T Cell Proliferator - 2019
Most immune responses to biotherapeutic proteins involve the development of anti-drug antibodies (ADAs). New drugs must undergo immunogenicity assessments to identify potential risks at early stages in the drug development process. This immune response is T cell-dependent. Ex vivo assays that monitor T cell proliferation often are used to assess immunogenicity risk. Such assays can be expensive and time-consuming to carry out. Furthermore, T cell proliferation requires presentation of the immunogenic epitope by major histocompatibility complex class II (MHCII) proteins on antigen-presenting cells. The MHC proteins are the most diverse in the human genome. Thus, obtaining cells from subjects that reflect the distribution of the different MHCII proteins in the human population can be challenging. The allelic frequencies of MHCII proteins differ among subpopulations, and understanding the potential immunogenicity risks would thus require generation of datasets for specific subpopulations involving complex subject recruitment. We developed TCPro, a computational tool that predicts the temporal dynamics of T cell counts in common ex vivo assays for drug immunogenicity. Using TCPro, we can test virtual pools of subjects based on MHCII frequencies and estimate immunogenicity risks for different populations. It also provides rapid and inexpensive initial screens for new biotherapeutics and can be used to determine the potential immunogenicity risk of new sequences introduced while bioengineering proteins. We validated TCPro using an experimental immunogenicity dataset, making predictions on the population-based immunogenicity risk of 15 protein-based biotherapeutics. Immunogenicity rankings generated using TCPro are consistent with the reported clinical experience with these therapeutics.

TCPro Dependencies

•	MATLAB Toolboxes: Bioinformatics and Optimization

•	TCPro was written on MATLAB v2017b and tested on v2019b

•	NetMHCIIPan – can be obtained for free from DTU Bioinformatics-Danmark

•	TCPro was tested on v3.2

•	BLAST+

•	TCPro was tested on v2.7.1


•	Current version of TCPro can only be run on Unix-based machines. Please contact Osman Yogurtcu for a discussion of a development of a Windows compatible version.

Notes on TCPro

•	TCPro is written in Matlab R2017b

•	TCPro uses Blast+ to identify sequence similarity of a query product against the known set of antigens posted on the IEDB database

•	Our published results are based on Blast v2.7.1 and it can be obtained from https://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/2.7.1/ 

•	TCPro uses NetMHCIIPan v3.2 to evaluate the binding of 15-mer peptides to the MHCII molecules.

•	NetMHCIIPan can be run on UNIX based machines using the source code available from http://www.cbs.dtu.dk/services/NetMHCIIpan/ 

•	Alternatively, users of Windows machines may automatize the query NetMHCIIPan by connecting TCPro with the following IEDB API: http://tools.iedb.org/main/tools-api/ 

How to Run TCPro

•	In the SIMULATION_ENVIRONMENT folder, we provide 15 example biotherapeutic proteins. Results of those proteins are already stored under the output folders of each drug. Users may repeat our simulations or based on our examples, they may run TCPro on a drug that they are interested in.

•	TCPro simulations can be performed on those proteins with runTCPro() command in Matlab. This will read the names of the drugs in folders.dat and simulations will be performed on each drug one by one.

•	Each example drug folder should contain 

•	options.dat: Drug-specific simulation options file

•	sequence.fasta: Protein sequence of the product in FASTA format

•	A comma separated list of HLA-DRB1s of the cohort members (e.g. UniqueWorldCohort.csv)

•	The users need to customize the above three files and folders.dat and run runTCPro(), to test their own products on select donor cohorts.

Details of an example options.dat file

ADALIMUMAB %antigenname Name of the antigen

WORLD %cohortname Name of the cohort

UniqueWorldCohort.csv %cohorthlafilename Filename for cohort HLAs - filetype: .csv

sequence.fasta %fastaseq Filename for antigen sequence - filetype: .fasta

100 %Nrun Number of runs

1 %FLAGpopulationdrugfreqavail Use 0 if you want to use antigen specific CD4+ T-cell frequency (per million CD4+) from this option.dat file, else 1 and we will read the literature values in 12248_2019_368_MOESM4_ESM.xlsx 

0.61 %MeanFp Mean antigen specific CD4+ T-cell frequency (per million CD4+)

0.13 %StdFp Standard deviation of antigen specific CD4+ T-cell frequency (per million CD4+)

1.9 %SIcutoff Stimulation index cutoff

0.05 %sigcutoff p-value for significance in SI

/home/Documents/NetMHCIIPanVersions/netMHCIIpan-3.2/ %NetMHCIIPanlocation location of NetMHCIIPan

/home/Downloads/ncbi-blast-2.7.1+/bin/ %locBLASTbin local folder path Blast

/home/Downloads/ncbi-blast-2.7.1+/IEDB_Epitopes_TCell/ %locEpitopeDB local folder path for epitopes (15-mer)
IEDB_Epitopes_TCell %EpitopeDB Name of EpitopeDB for BLAST



TCPro Work Flow – The Matlab Files

Contact Information

•	Osman N Yogurtcu, osman.yogurtcu@fda.hhs.gov

•	Hong Yang, hong.yang@fda.hhs.gov 
