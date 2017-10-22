# BioTransformer's README

**********************************************************************************
This is version 1.0.1 of BioTransformer. BioTransformer is a software tool that 
predicts small molecule metabolism in mammals, their gut microbiota, 
as well as the soil/aquatic microbiota.
Please make sure to download the folder database and supportfiles, and save them 
in the same folder as the .jar file.
**********************************************************************************

usage:
java -jar biotransformer-1.0.1 -b <BioTransformer Type> -f <Input format>
       [-h] -i <Input> [-o <Output>] [-s <Number of steps>]

This is the version 1.0.1 of BioTransformer. BioTransformer is a software
tool that predicts small molecule metabolism in mammals, their gut
microbiota, as well as the soil/aquatic microbiota.

 -b,--btType <BioTransformer Type>   The type of description: Type of
                                     biotransformer - EC-based  (ecbased),
                                     CYP450 (cyp450), Phase II (phaseII),
                                     Human gut microbial (hgut),
                                     Environmental microbial (envimicro),
                                     human super transformer* (superbio,
                                     or allHuman).
                                     
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
                                     
* While the superbio option runs a set number of transformation steps in a
pre-defined order (e.g. deconjugation first, then Oxidation/reduction,
etc.), the allHuman option predicts all possible metabolites from any
applicable reaction(Oxidation, reduction, (de-)conjudation) at each step.


E.g.: To predict the biotransformation of a molecule from an SDF input using the human super transformer, use
java -jar biotransformer-1-0-1.jar -b superbio -f sdf -i #{input file name} -o #{output folder}.


To report issues, provide feedback, or ask questions, please send an
e-mail the following address: djoumbou@ualberta.ca

