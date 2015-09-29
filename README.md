# assembly-pipeline-vm

# Install dependencies

## Install Perl 5

Check is Perl is already installed by running the follwoing command in termial:

```bash
   which perl
```

The previous command should return the path of the perl execuable in case perl is already installed (e.g. `/usr/bin/perl`). If it does not return anything, then run the following command in termial:

```bash
   sudo apt-get install perl
```

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

