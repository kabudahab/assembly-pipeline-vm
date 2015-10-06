# assembly-pipeline-vm


# Installation guide

The steps given here show how to install the [genome assembly pipeline](https://github.com/sanger-pathogens/vr-codebase) (developed by the Vertebrate Resequencing group at the Sanger Institute) on a Ubuntu 12.04.03 LTS machine.

## Install software dependencies

1. Perl 5, run the following command in termial if Perl is not installed:

    ```bash
    sudo apt-get install perl
    ```
    
2. Java, run the following command in termial if Java is not installed:

    ```bash
    sudo apt-get install openjdk-7-jre
    ```
    
3. Install awk command by running the following command in terminal:

    ```
    sudo apt-get install gawk 
    ```

## Install bioinformatics software

This pipeline requires the following software to be installed:
* Samtools,
* velvet, 
* smalt, 
* SSPACE, 
* SGA, 
* khmer, and
* QUASR

This can be done either manually by installing them from their original software repositories, or
alternativally you can download and install a bundle of all of the required bioinformatics software as follows:

1. Download [BioSoftware-vol1.tar.gz](BioSoftware-1.tar.gz),  [BioSoftware-vol2.tar.gz](BioSoftware-2.tar.gz), and [BioSoftware-vol3.tar.gz](BioSoftware-3.tar.gz).
2. Extract all three files to `~/Documents/`
3. Set environment variables by running the following command in termial:

    ```bash
   gedit ~/.bashrc
    ```
    
4. Scroll to the end of the file
5. Copy the following lines

    ```
    # Set bioinformatics software environment variables 
    export PATH="$PATH:$HOME/Documents/software/bin"
    export SAMTOOLS="/home/ubuntu/Documents/software/samtools/samtools-0.1.19"
    export PICARD="/home/ubuntu/Documents/software/picard/picard-tools-1.92"
    export G1K=""
    export PYTHONPATH="$PYTHONPATH:/home/ubuntu/Documents/software/khmer/python"
    ```

6. Save and close the file.
7. Reload the environment variables by running the following command in termial:

    ```bash
    source ~/.bashrc
    ```
8. Verify that binary files are installed by running the following command in termial:

    ```bash
    which assembly_stats  bamcheck  fastqcheck  samtools  sga  smalt  velvetg  velveth 
    ```
9. The previous command should output the path of each of the binary files:

    ```bash
    /home/ubuntu/Documents/software/bin/assembly_stats
    /home/ubuntu/Documents/software/bin/bamcheck
    /home/ubuntu/Documents/software/bin/fastqcheck
    /home/ubuntu/Documents/software/bin/samtools
    /home/ubuntu/Documents/software/bin/sga
    /home/ubuntu/Documents/software/bin/smalt
    /home/ubuntu/Documents/software/bin/velvetg
    /home/ubuntu/Documents/software/bin/velveth
    
    ```


## Install Sanger Vertebrate Resequencing codebase

1. Download vr-codebase from [https://github.com/sanger-pathogens/vr-codebase/archive/master.zip](https://github.com/sanger-pathogens/vr-codebase/archive/master.zip)
2. Extract the ZIP file to `~/vr-codebase`
3. Build vr-codebase by running the following command in terminal:

    ```
    cd ~/vr-codebase
    cpan DateTime
    perl Build.PL
    ./Build installdeps
    cpan Inline Inline::C Inline::Filters Bio::AssemblyImprovement::Scaffold::Descaffold
    ```
4. To set environment variables, run the following command in termial:

    ```bash
    gedit ~/.bashrc
    ```
5. Scroll to the end of the file
6. Copy the following lines

    ```
    # Add vr-codebase modules to Perl lib path environment variable
    export PERL5LIB="$PERL5LIB:/home/ubuntu/Documents/vr-codebase/modules"
    export PERL5LIB="$PERL5LIB:$HOME/perl5/lib/perl5"
    ```

7. Save and close the file.
8. Reload the environment variables by running the following command in termial:

    ```bash
    source ~/.bashrc
    ```
9. Verify that environment variables are set by running the following command in termial:

    ```bash
    echo $PERL5LIB 
    ```
9. The previous command output should include the path of vr-codebase modules folder:

    ```bash
    :/home/ubuntu/Documents/vr-codebase/modules:/home/ubuntu/perl5/lib/perl5
    ```

## Download assembly pipeline 

1. Download assembly-pipeline from https://github.com/...
2. Extract the ZIP file to `~/assembly-pipeline`
3. To set environment variables, run the following command in termial:

    ```bash
    gedit ~/.bashrc
    ```
4. Scroll to the end of the file
5. Copy the following lines

    ```
    # Add assembly pipeline to PATH environment variable
    export PATH="$PATH:$HOME/Documents/assembly-pipeline"
    
    ```

6. Save and close the file.
7. Reload the environment variables by running the following command in termial:

    ```bash
    source ~/.bashrc
    ```
8. Verify that the environment variables are set by running the following command in termial:

    ```bash
    which run-assembly-pipeline.pl 
    ```
9. The previous command should output the path of the assembly pipeline wrapper script:

    ```bash
    /home/ubuntu/Documents/assembly-pipeline/run-assembly-pipeline.pl
    ```







