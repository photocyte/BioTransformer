# BioTransformer's README

**********************************************************************************
This is version 1.0.0 of BioTransformer. BioTransformer is a software tool that 
predicts small molecule metabolism in mammals, their gut microbiota, 
as well as the soil/aquatic microbiota.
Please make sure to download the folder database and supportfiles, and save them 
in the same folder as the .jar file.
**********************************************************************************

Usage:

 -b,--btType <BioTransformer Type>   The type of description: Type of
                                     biotransformer - EC-based, CYP450,
                                     Phase II, Human gut microbial,
                                     Environmental microbial, or human
                                     super transformer.
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
									 
To report issues, provide feedback, or ask questions, please send an
e-mail the following address: djoumbou@ualberta.ca

E.g.: To predict the biotransformation of a molecule from an SDF input using the human super transformer, use
java -jar biotransformer-1-0-0.jar -b superbio -f sdf -i #{input file name} -o #{output folder}.
To report issues, provide feedback, or ask questions, please send an e-mail the following address: djoumbou@ualberta.ca