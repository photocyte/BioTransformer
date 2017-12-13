# BioTransformer's README

***************************************************************************************************
This is version 1.0.4 of BioTransformer. BioTransformer is a software tool that 
predicts small molecule metabolism in mammals, their gut microbiota, 
as well as the soil/aquatic microbiota.
Please make sure to download the folder database and supportfiles, and save them 
in the same folder as the .jar file.


Cite: Djoumbou Feunang, Yannick; Cheminformatics Tools for Enabling Metabolomics; 2017; PhD Thesis
***************************************************************************************************

usage:
java -jar biotransformer-1.0.4 -b <BioTransformer Type> -f <Input format>
       [-h] -i <Input> [-o <Output>] [-s <Number of steps>]

This is the version 1.0.4 of BioTransformer. BioTransformer is a software
tool that predicts small molecule metabolism in mammals, their gut
microbiota, as well as the soil/aquatic microbiota.

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
                                     biotransformers.
                                     
(* ) While the 'superbio' option runs a set number of transformation steps in a
pre-defined order (e.g. deconjugation first, then Oxidation/reduction,
etc.), the 'allHuman' option predicts all possible metabolites from any
applicable reaction(Oxidation, reduction, (de-)conjudation) at each step.


(** ) For the environmental microbial biodegradation, all reactions (aerobic and anaerobic) 
are reported, and not only the aerobic biotransformations (as per default in the EAWAG BBD/PPS system).


*********
Examples:
*********

1) To predict the biotransformation of a molecule from an SDF input using the human super transformer (option superbio) and annotate the metabolites with names and database IDs (from PubChem), run

java -jar biotransformer-1-0-4.jar -b superbio -f sdf -i #{input file name} -o #{output folder} -a.
      
      - For each of the query molecule in the input file, an outputfile will be created with the list of corresponding metabolites.

2) To predict the 2-step biotransformation of Thymol (a monoterpene) using the human super transformer (option allHuman) using the SMILES input, run

java -jar biotransformer-1-0-4.jar -b allHuman -f smiles -i "CC(C)C1=CC=C(C)C=C1O" -o #{replace with output file name} -s 2

Currently, the outputfile is SDF per default.


To report issues, provide feedback, or ask questions, please send an
e-mail the following address: djoumbou@ualberta.ca

