# assembly-pipeline-vm

# Install dependencies

## Perl 5

Check is Perl is already installed by running the follwoing command in termial:

```bash
   which perl
```

The previous command should return the path of the perl execuable in case perl is already installed (e.g. `/usr/bin/perl`). If it does not return anything, then run the following command in termial:

```bash
   sudo apt-get install perl
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

* DateTime
* 

* Net::FTP::Robust
* Filesys::DfPortable
* Filesys::DiskUsage
* File::Rsync
* Time::Format
* IO::Capture::Stderr
* DBI


# Install files

## Download Perl modules

1. Download assembly-pipeline-perl5-modules from https://github.com/...
2. Extract to `~/perl5`

## Download vr-codebase

1. Download vr-codebase from https://github.com/sanger-pathogens/vr-codebase/archive/master.zip
2. Extract to `~/vr-codebase`

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

