Gene scores, annotations and disease heritability analysis results for Jagadeesh*, Dey* et al (2020) bioRxiv
titled
"Identifying disease-critical cell types and cellular processes across the human body by integration of single-cell profiles and human genetics"

##############################################################################################
Description of each folder and subfolder
##############################################################################################

.
|-- scdata
   All Processsed scRNA-seq data with annotated cell types 
   - singlecell_datasets.xlsx: Description of all scRNA-seq datasets used to construct gene programs
   - *.h5ad: HDF5 files corresponding to each scRNA-seq with annotated cell types  

|-- gene_scores 
    - Contains all gene scores data for the three types of programs 
    |-- cell_type_programs : All cell type programs from different tissues
    annotated_celltypes.xlsc: Annotation of each cell type program 

    |-- disease_progression_programs: All diseae progression programs from UC, MS, Alzheimers, Asthma, COVID-19 and Fibrosis 
    |-- cellular_process_programs:
    annotated_nmf.xlsx: Annotation of each NMF program using top pathway from pathway enrichment analysis.
    	|-- nmf : All cellular process programs from different tissues 
	    	  (*_annotated represents subsets of * which have distinct annotation)
	|-- nmf_disease_healthy: All cellular process programs from disease + healthy tissues 
         	  (*_annotated represents subsets of * which have distinct annotation) 

|-- annotations 
    - Contains all annotations linking genes in gene score with RoadmapUABC enhancer-gene linking strategy.
    |-- cell_type_programs : Annotations for all cell type gene programs
    |-- disease_progression_programs: Annotations for all disease progression programs 
    |-- cellular_process_programs 
    	|-- nmf: Annotations for all cellular process programs for a tissue 
	|-- nmf_disease_healthy: Annotations for all cellular process programs for disease +healthy tissue

-- sclinker_results 
   - Contains heritability analysis results for each annotation in the 'annotations' directory.
   |-- cell_type_programs : Heritability analysis results for annotations in annotations/cell_type_programs
   |-- disease_progression_programs: Heritability analysis results for annotations in annotations/disease_progression_programs
   |-- cellular_process_programs
       |-- nmf: Heritability analysis results for annotations in annotations/cellular_process_programs/nmf
       |-- nmf_disease_healthy: Heritability analysis results for annotations in annotations/cellular_process_programs/nmf_disease_healthy

##############################################################################################
How to use these annotations?
##############################################################################################

How to use it?

1) Download the LDSC from git (https://github.com/bulik/ldsc/wiki/Partitioned-Heritability)
2) Download the baselineLD_v2.1 annotations from Broad webpage (https://data.broadinstitute.org/alkesgroup/LDSCORE/)
3) Download all sc-linker annotations from (see above) from https://data.broadinstitute.org/alkesgroup/LDSCORE/Jagadeesh_Dey_sclinker
4) Use your GWAS summary statistics formatted in LDSC details is available (https://github.com/bulik/ldsc/wiki/Summary-Statistics-File-Format)
5) Download the baseline frq file and weights for 1000G available (https://data.broadinstitute.org/alkesgroup/LDSCORE/)
6) Run S-LDSC with these annotations conditional on baselineLD_v2.1 (see https://github.com/bulik/ldsc/)

###################
ANNOT FILE header (*.annot):
##################

###################
ANNOT FILE header (*.annot):
##################

CHR -- chromosome
BP -- physical position (base pairs)
SNP -- SNP identifier (rs number)
CM -- genetic position (centimorgans)
all additional columns -- Annotations

NOTE: Although one would expect the genetic position to be non-negative for all 1000G SNPs, we have checked that
in fact the genetic position is negative for a handful of 1000G SNPs that have a physical position that is smaller
than the smallest physical position in the genetic map. The genetic positions were obtained by running PLINK on
the Oxford genetic map (http://www.shapeit.fr/files/genetic_map_b37.tar.gz).

MORE DETAIL CAN BE OBTAINED FROM https://github.com/bulik/ldsc/wiki/LD-File-Formats


###################
LD SCORE FILE header (*.l2.ldscore):
##################

CHR -- chromosome
BP -- physical position (base pairs)
SNP -- SNP identifier (rs number)
all additional columns -- LD Scores

##################


