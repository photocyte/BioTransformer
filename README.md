# BioTransformer's README

***************************************************************************************************
This is version 1.0.2 of BioTransformer. BioTransformer is a software tool that 
predicts small molecule metabolism in mammals, their gut microbiota, 
as well as the soil/aquatic microbiota.
Please make sure to download the folder database and supportfiles, and save them 
in the same folder as the .jar file.
Cite: Djoumbou Feunang, Yannick; Cheminformatics Tools for Enabling Metabolomics; 2017; PhD Thesis
***************************************************************************************************

usage:
java -jar biotransformer-1.0.2 -b <BioTransformer Type> -f <Input format>
       [-h] -i <Input> [-o <Output>] [-s <Number of steps>]

This is the version 1.0.2 of BioTransformer. BioTransformer is a software
tool that predicts small molecule metabolism in mammals, their gut
microbiota, as well as the soil/aquatic microbiota.

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

1) To predict the biotransformation of a molecule from an SDF input using the human super transformer (option superbio), run

java -jar biotransformer-1-0-2.jar -b superbio -f sdf -i #{input file name} -o #{output folder}.
      
      - For each of the query molecule in the input file, an outputfile will be created with the list of corresponding metabolites.

2) To predict the 2-step biotransformation of 17-ethinylestradiol using the human super transformer (option allHuman) using the SMILES input, run

java -jar biotransformer-1-0-2.jar -b allHuman -f smiles -i "C[C@]12CC[C@H]3[C@@H](CCC4=CC(O)=CC=C34)[C@@H]1CC[C@@]2(O)C#C" -o #{output file name} -s 2

Currently, the outputfile is SDF per default.


To report issues, provide feedback, or ask questions, please send an
e-mail the following address: djoumbou@ualberta.ca

