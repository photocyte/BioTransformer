# BioTransformer's README

***************************************************************************************************
This is version 1.0.4 of BioTransformer. BioTransformer is a software tool that predicts small molecule metabolism in mammals, their gut microbiota, 
as well as the soil/aquatic microbiota. BioTransformer also assists scientists in metabolite identification, based on the metabolism prediction. Please make sure to download the folders database and supportfiles, and save them in the same folder as the .jar file.

BioTransformer is offered to the public as a freely acessible software package. Beside the prediction software, a manually curated database called BioTransformerDB is also available. Use and re-distribution of the these resources, in whole or in part, for commercial purposes requires explicit permission of the authors and explicit acknowledgment of the source material (BioTransformer) and the original publication (see citation). We ask that all users of the BioTransformer software tool or BioTransformerDB to cite the BioTransformer reference in any resulting publications.

Cite: Djoumbou Feunang, Yannick; Cheminformatics Tools for Enabling Metabolomics; 2017; PhD Thesis
***************************************************************************************************

usage:
java -jar biotransformer-1.0.4 -b <BioTransformer Type> -f <Input format>
       [-h] -i <Input> [-o <Output>] [-s <Number of steps>]

This is the version 1.0.4 of BioTransformer. BioTransformer is a software
tool that predicts small molecule metabolism in mammals, their gut
microbiota, as well as the soil/aquatic microbiota. BioTransformer also assists scientists in metabolite identification, based on the metabolism prediction.

 -a,--annotate                       Search PuChem for each product, and
                                     annotate with CID and synonyms
 -b,--btType <BioTransformer Type>   The type of description: Type of
                                     biotransformer - EC-based  (ecbased),
                                     CYP450 (cyp450), Phase II (phaseII),
                                     Human gut microbial (hgut),
                                     human super transformer** (superbio,
                                     or allHuman), Environmental microbial (envimicro)*.
                                     
 -f,--format <Input format>          The format of the input: SMILES
                                     (smi), MDL Mol file (mol), or
                                     Structure data file (sdf).
                                     
 -h,--help                           Prints the usage.
 
 -i,--input <Input>                  The input, which can be a SMILES
                                     string, a Mol file, or SDF file.

-m,--mList                          Given the starting comound(s), Find
                                     all their metabolites with the
                                     specified masses, and show a
                                     metabolism pathway. A
                                     whitespace-separated list of masses
                                     is expected.
                                     
 -o,--ioutput <Output>               The output file name (which must be a
                                     SDF file) for single input queries,
                                     or the output folder for multiple
                                     input queries.
                                     When submitting a mutiple input
                                     query, an output folder must be
                                     provided.
                                     
 -s,--nsteps <Number of steps>       The number of steps for the
                                     prediction. This option can be set by
                                     the user for the EC-based, CYP450,
                                     Phase II, and Environmental microbial
                                     biotransformers. The default value is 1.

 -t,--mTolerance                     Mass tolerance for metabolite
                                     identification (default is 0.0).                                     
(* ) While the 'superbio' option runs a set number of transformation steps in a
pre-defined order (e.g. deconjugation first, then Oxidation/reduction,
etc.), the 'allHuman' option predicts all possible metabolites from any
applicable reaction(Oxidation, reduction, (de-)conjugation) at each step.


(** ) For the environmental microbial biodegradation, all reactions (aerobic and anaerobic) are reported, and not only the aerobic biotransformations (as per default in the EAWAG BBD/PPS system).


*********
Examples:
*********

1) To predict the biotransformation of a molecule from an SDF input using the human super transformer (option superbio) and annotate the metabolites with names and database IDs (from PubChem), run

java -jar biotransformer-1-0-4.jar -b superbio -f sdf -i #{input file name} -o #{output folder} -a.
      
      - For each of the query molecule in the input file, an outputfile will be created with the list of corresponding metabolites.

2) To predict the 2-step biotransformation of Thymol (a monoterpene) using the human super transformer (option allHuman) using the SMILES input, run

java -jar biotransformer-1-0-4.jar -b allHuman -f smiles -i "CC(C)C1=CC=C(C)C=C1O" -o #{replace with output file name} -s 2

Currently, the outputfile is SDF per default.

3) Identify all human metabolites (max depth = 2) of Epicatechin ("O[C@@H]1CC2=C(O)C=C(O)C=C2O[C@@H]1C1=CC=C(O)C(O)=C1") with masses 292.0946 Da and 304.0946 Da, with a mass tolerance of 0.01 Da. Provide an annotation (Common name).

java -jar biotransformer-1-0-4.jar -b allHuman -f smiles -i "O[C@@H]1CC2=C(O)C=C(O)C=C2O[C@@H]1C1=CC=C(O)C(O)=C1" -o #{replace with output file name} -s 2 -m "292.0946;304.0946" -t 0.01 -a
    
    - DO NOT forget the quotes around the SMILES string or the list of masses.

To report issues, provide feedback, or ask questions, please send an
e-mail the following address: djoumbou@ualberta.ca

