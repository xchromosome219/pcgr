Annotation resources
--------------------

Basic variant consequence annotation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  `VEP v90 <http://www.ensembl.org/info/docs/tools/vep/index.html>`__ -
   Variant Effect Predictor release 90 (`GENCODE
   v27 <https://www.gencodegenes.org/releases/27.html>`__ as gene
   reference database)

*Insilico* predictions of effect of coding variants
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  `dBNSFP v3.4 <https://sites.google.com/site/jpopgen/dbNSFP>`__ -
   database of non-synonymous functional predictions (March 2017)
-  `IntOGen catalogs of driver
   mutations/genes <https://www.intogen.org/downloads>`__ - (May 2016)

Variant frequency databases
~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  *COSMIC - Deprecated in 0.5.0 due to COSMIC licensing restrictions*
-  `gnomAD r1 <http://exac.broadinstitute.org/>`__ - germline variant
   frequencies exome-wide (March 2017)
-  `dbSNP b147 <http://www.ncbi.nlm.nih.gov/SNP/>`__ - database of short
   genetic variants (April 2016)
-  `1000Genomes
   phase3 <ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/release/20130502/>`__
   - germline variant frequencies genome-wide (May 2013)
-  `Cancer Hotspots <http://cancerhotspots.org>`__ - a resource for
   statistically significant mutations in cancer (2016)
-  `TCGA release 9.0 <https://portal.gdc.cancer.gov/>`__ - somatic
   mutations discovered across 33 tumor type cohorts (The Cancer Genome
   Atlas)

Variant databases of clinical utility
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  `ClinVar <http://www.ncbi.nlm.nih.gov/clinvar/>`__ - database of
   clinically related variants (November 2017)
-  `DoCM <http://docm.genome.wustl.edu>`__ - database of curated
   mutations (v3.2, April 2016)
-  `CIViC <http://civic.genome.wustl.edu>`__ - clinical interpretations
   of variants in cancer (November 11th 2017)
-  `CBMDB <http://www.cancergenomeinterpreter.org/biomarkers>`__ -
   Cancer BioMarkers database (November 11th 2017)
-  `DGIdb <http://dgidb.genome.wustl.edu>`__ - database of targeted
   antineoplastic drugs (v3.0, September 2017)

Protein domains/functional features
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  `UniProt/SwissProt KnowledgeBase 2017\_10 <http://www.uniprot.org>`__
   - resource on protein sequence and functional information (October
   2017)
-  `Pfam v31 <http://pfam.xfam.org>`__ - database of protein families
   and domains (March 2017)

Cancer gene knowledge bases
~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  `TSGene v2.0 <http://bioinfo.mc.vanderbilt.edu/TSGene/>`__ - tumor
   suppressor/oncogene database (November 2015)
-  *Cancer Gene Census - Deprecated in 0.5.0 due to COSMIC licensing
   restrictions*
-  `DisGeNET v5.0 <http://www.disgenet.org>`__ - curated associations
   between human genes and different tumor types

Pathway databases
~~~~~~~~~~~~~~~~~

-  `KEGG PATHWAY Database <http://www.genome.jp/kegg/pathway.htm>`__ -
   September 29th 2017

Notes on variant annotation datasets
------------------------------------

Genome mapping
~~~~~~~~~~~~~~

A requirement for PCGR variant annotation datasets is that variants have
been mapped unambiguously to the reference human genome (GRCh37 is
currently the only supported build). For most datasets this requirement
is not an issue (i.e. dbSNP, ClinVar etc.). A fraction of variants in
the annotation datasets related to clinical interpretation, CIViC and
CBMDB, has however not been mapped to the genome. Whenever possible, we
have utilized
`TransVar <http://bioinformatics.mdanderson.org/transvarweb/>`__ to
identify the actual genomic variants (e.g. *g.chr7:140453136A>T*) that
correspond to variants reported at the amino acid level or with other
HGVS nomenclature (e.g. *p.V600E*).

Data quality
~~~~~~~~~~~~

**Clinical biomarkers**

Clinical biomarkers included in PCGR are limited to the following:

-  Markers reported at the variant level (e.g. **BRAF p.V600E**)
-  Markers reported at the codon level (e.g. **KRAS p.G12**)
-  Markers reported at the exon level (e.g. **KIT exon 11 mutation**)
-  Within the `Cancer bioMarkers database
   (CBMDB) <https://www.cancergenomeinterpreter.org/biomarkers>`__, only
   markers collected from FDA/NCCN guidelines, scientific literature,
   and clinical trials are included (markers collected from conference
   abstracts etc. are not included)

**Antineoplastic drugs**

-  For drugs extracted from `DGIdb <http://dgidb.genome.wustl.edu>`__,
   we only include antineoplastic drugs subject to direct interaction
   with a target (i.e. as found in ChEMBL)

**Gene-disease associations**

-  For gene-disease associations extracted from DisGeNET 5.0, we require
   a `score <http://www.disgenet.org/web/DisGeNET/menu/dbinfo#score>`__
   greater than 0.2 and that the association is suppported by at least
   one PMID (PubMed article). Associations involving non-cancer type of
   diseases are not included.

**TCGA somatic calls**

-  TCGA employs four different variant callers for detection of somatic
   variants (SNVs/InDels), *mutect2, varscan2, somaticsniper and muse*.
   In the TCGA dataset bundled with PCGR, somatic SNVs are restricted to
   those that are detected by at least two independent callers (i.e.
   calls found by a single algorithm are considered low-confident and
   disregarded)

.. raw:: html

   <!--__COSMIC variants__

   The COSMIC dataset that is part of the PCGR annotation bundle is the subset of variants that satisfy the following criteria:

   * __Mutation somatic status__ is either '_confirmed_somatic_' or '_reported_in_another_cancer_sample_as_somatic_'.
   * __Site/histology__ must be known and the sample must come from a malignant tumor (i.e. not polyps/adenomas, which are also found in COSMIC)-->
