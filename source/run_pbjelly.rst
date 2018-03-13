**run_pbjelly.py** Quick Start
**run_pbjelly.py** Quick Start
====================================
run_pbjelly.py, do the gapcloser with long reads sequencings.
Firstly, it will filtered out reads which are not related to 
This script is used to generate shell for 

(A) run MECAT, do the alignment for all the reads; 

(B) pick reads, keep reads that are related to gap regions; 

(C) mask genome, masked 1bp gap to more than 100bp gaps; 

(D) run PBJelly, use only picked reads to run PBJelly.


Installation
-------------
Download
^^^^^^^^^^^^^^^^^^^^^
You can download or get the code through the URL

Unzip
^^^^^^^^^^^^^^^^^^^^^
tar -zxvf run_pbjelly.*.tar.gz

Examples
-------------
Prepared the input
^^^^^^^^^^^^^^^^^^^^^
(A) the scaffolds name with 'fasta' as ending

(B) the reads.list file containing all the raw reads

(C) write all the information and parameters into the config.cfg

Generate the shell
^^^^^^^^^^^^^^^^^^^^^

/NJPROJ1/RAD/software/anaconda2/bin/python YourDir/run_pbjelly.py config.cfg

then:

(A) the program build four dir: 0-shells, 1-data, 2-results, 3-reports, and 4-logs

(B) all the script were under the 0-shells

(C) the filted reads were under the 1-data

(D) the alignment and picked reads were under the 2-results

(E) the statistics and the reports were under the 3-reports

(F) and the log and template files were under the 4-logs

Resources
-------------

Contact author Liji by this email liji@novogene.com

