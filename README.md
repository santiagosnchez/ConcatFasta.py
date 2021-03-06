# ConcatFasta.py

**note**: `ConcatFasta` has now been updated for Python3

Concatenates FASTA files, imputes dummy sequences, and prints a partition table

This is a Python version of [concat_fasta.pl](https://github.com/santiagosnchez/concat_fasta). It is more portable and expandable than its Perl predecessor and will be updated more regularly.

Concatenates FASTA files given a suffix present in all target files (e.g. "XXX.fasta"). Labels for the same "taxon" should be the same on all FASTA files, but can be unordered. The number of sequences on each file can also be different. In this case, an empty sequence will be added (e.g. "???.."). It will also print a layout of the partitions to the screen with the `-p/--part` flag. Sequences can be wrapped at 100 characters with the `-w/--wrap` option.

The program now can export as NEXUS or PHYLIP formats by switching the `--nexus/-n` or `--phylip/-p` arguments. Partition blocks will be added to the NEXUS file or a file written for PHYLIP with the `--part/-q` argument.

## Downloading the program

    wget https://raw.githubusercontent.com/santiagosnchez/ConcatFasta/master/ConcatFasta.py

## Running the code

Use the `-h` flag for more details:

    
    python ConcatFasta.py -h
    usage: ConcatFasta.py [-h] [--files [FASTA_FILE [FASTA_FILE ...]]]
                      [--dir [DIR]] [--suffix [SUFFIX]] [--outfile [OUTFILE]]
                      [--part ] [--wrap ] [--nexus ] [--phylip ]
    
    Concatenates FASTA files into a single file.
    
    optional arguments:
      -h, --help            show this help message and exit
      --files [FASTA_FILE [FASTA_FILE ...]], -f [FASTA_FILE [FASTA_FILE ...]]
                            file to concatenate in FASTA format.
      --dir [DIR], -d [DIR]
                            directory where FASTA files to concatenate are
                            (default: .).
      --suffix [SUFFIX], -s [SUFFIX]
                        suffix for FASTA files.
      --outfile [OUTFILE], -o [OUTFILE]
                        name for output file (default: concat.fasta).
      --part [], -q []      will print a partition table.
      --wrap [], -w []      sequences will be wrapped every 100 characters.
      --nexus [], -n []     export in NEXUS format.
      --phylip [], -p []    export in PHYLIP format.
    
    Files can be sepcified one by one with --files or by specifying a directory
    --dir with the files. Additionally, a --suffix suffix can be combined with
    --dir to filter out other files.
