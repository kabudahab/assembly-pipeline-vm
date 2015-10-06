# assembly-pipeline-vm



# Checking 

Check if Perl is already installed by running the follwoing command in termial:
```bash
   which perl
```
The previous command returns the path of perl execuable in case it is already installed (e.g. `/usr/bin/perl`). 


Check if Java is already installed by running the follwoing command in termial:
```bash
   which java
```

The previous command should return the path of the java execuable in case it is already installed (e.g. `/usr/bin/java`). If it does not return anything, then 



# Installation guide

The steps given here show how to install the genome assembly pipeline  (developed by the Vertebrate Resequencing group at the Sanger Institute) on a Ubuntu 12.04.03 LTS machine.

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

1. Download BioSoftware-vol1.tar.gz () and BioSoftware-vol2.tar.gz () .
2. Extract both files to ~/Documents/
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


## Samtools

1. Install required packages by running the following command in terminal:
```
sudo apt-get install zlib1g-dev libncurses5-dev 
```
2. Download Samtools from https://github.com/samtools/samtools (e.g. https://github.com/samtools/samtools/archive/1.1.zip)
3. Extract the downloaded samtools ZIP file to ~/Downloads/samtools-1.1
4. Download HTSlib from https://codeload.github.com/samtools/htslib/zip/1.1
5. Extract htslib-1.1.zip to  ~/Downloads/samtools-1.1
6. Open the file ~/Downloads/samtools-1.1/MAKEFILE in a text editor (e.g. gedit)
7. Edit line number 85 so it points to the folder where you extarcted htslib-1.1.zip
```
# Adjust $(HTSDIR) to point to your top-level htslib directory
HTSDIR = /home/ubuntu/Downloads/samtools-1.1/htslib-1.1
include $(HTSDIR)/htslib.mk
HTSLIB = $(HTSDIR)/libhts.a
BGZIP  = $(HTSDIR)/bgzip
'''
8. Run the following commands in terminal:
```
cd ~/Downloads/samtools-1.1
make
sudo make install
```
9. Verify that samtools has been installed by running the following command in terminal:
```
which samtools
```
6. Copy samtools header files by running the following command in terminal:
7. ```
sudo mkdir /usr/include/samtools

```


## Install Perl modules

* Net::FTP::Robust
* Filesys::DfPortable
* Filesys::DiskUsage
* File::Rsync
* Time::Format
* IO::Capture::Stderr
* DBI


## Install 

1. 


## Download Perl modules

1. Download assembly-pipeline-perl5-modules from https://github.com/...
2. Extract to `~/perl5`

## Download vr-codebase

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

