# assembly-pipeline-vm

## Fenced code blocks inside ordered and unordered lists

1. This is a numbered list.
2. I'm going to include a fenced code block as part of this bullet:

    ```
    Code
    More Code
    ```

3. We can put fenced code blocks inside nested bullets, too.
   1. Like this:

        ```c
        printf("Hello, World!");
        ```

   2. The key is to indent your fenced block by **(4 * bullet_indent_level)** spaces.
   3. Also need to put a separating newline above and below the fenced block.


# Installation guide

The steps given here show how to install the genome assembly pipeline (developed by the Vertebrate Resequencing group at the Sanger Institute) on a Ubuntu 12.04.03 LTS machine.

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
* prokka, 
* smalt, 
* SSPACE, 
* SGA, 
* khmer, 
* QUASR, 
* and GapFiller 

This can be done either manually by installing them from their original software repositories, or
alternativally you can download and install a bundle of all of the required bioinformatics software as follows:

1. Download `BioSoftware-vol1.tar.gz` () and `BioSoftware-vol2.tar.gz` () .
2. Extract both files to `~/Documents/`
3. Set environment variables by running the following command in termial:
```bash
   gedit ~/.bashrc
```
4. Scroll to the end of the file
5. Copy the following line
```
export PATH="$PATH:/home/ubuntu/Documents/software/bin"
```
6. Save and close the file.
7. Reload the environment variables by running the following command in termial:
```bash
   source ~/.bashrc
```
8. Verify that binary files are installed by running the following command in termial:
```bash
   which 
```
9. The previous command should output the follows:
```bash
    
```


## Install vr-codebase

1. Download vr-codebase from https://github.com/sanger-pathogens/vr-codebase/archive/master.zip
2. Extract to `~/vr-codebase`
3. Build vr-codebase by running the following command in terminal:
```
cd ~/vr-codebase
cpan DateTime
perl Build.PL
./Build installdeps
cpan Inline Inline::C Inline::Filters Bio::AssemblyImprovement::Scaffold::Descaffold
```


## Download assembly pipeline wrapper

1. Download assembly-pipeline-wrapper from https://github.com/...
2. Extract to `~/assembly-pipeline-wrapper`


## Set environment variables

1. Run the following command in termial:
```bash
   gedit ~/.profile
```
2. Scroll to the end of the file
3. Copy the following lines
```
export PATH="$PATH:$HOME/Documents/assembly-pipeline-wrapper"
export PATH="$PATH:$HOME/Documents/assembly-pipeline-wrapper/software/pathogen/external/apps/usr/bin"
export PATH="$PATH:$HOME/Documents/assembly-pipeline-wrapper/software/pathogen/external/apps/usr/local/bin"
export PATH="$PATH:$HOME/Documents/assembly-pipeline-wrapper/software/pathogen/internal/prod/bin"
```

