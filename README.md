# SNIPSA

A small project experimenting with SNP genome data and python.

## haploy_find.py

This small tool reads a raw SNP data file and lists Y chromosome haplogroup information. You must first initialize the mutation
database with `haploy_db_import.py`. The tool lists all the haplogroup related mutations found in the database, sorted roughly
by age of the mutation.

```
./haploy_find.py <file>
```

The tool accepts also multiple files. This can be used to search haplogroups among the files, using the common haplogroup name
(separated by comma) or mutation name as the search key.

```
./haploy_find.py N1a1,I2,L287 <files>...
```

## haploy_db_import.py

This script imports the ISOGG database to the internal format that is used by haploy_find.py. It needs
CrossMap (`pip3 install CrossMap`), conversion chain file (`crossmap/GRCh38_to_NCBI36.chain.gz`) and
the ISOGG spreadsheet in csv format (`'SNP Index - Human.csv'`). Outputs a `haploy_map.txt`
file which is used by haploy_find.py. See haploy.py for details.

## haplomt_find.py

This small tool reads a raw SNP data file and lists MT chromosome haplogroup information. You must first initialize the mutation
database with `haplomt_db_import.py`. The tool finds paths in the mutation tree and displays best matches.

```
./haplomt_find.py <file>
```

The tool accepts also multiple files. This can be used to search haplogroups among the files, using the common haplogroup name
(separated by comma) or mutation name as the search key.

```
./haplomt_find.py 0 <files>...
```

## haplomt_db_import.py

This script imports the PhyloTree.org mtDNA database file in (`https://www.phylotree.org/builds/mtDNA_tree_Build_17.zip`) to the internal format.
Experimental support for yfull.com mtree import. Outputs a `haplomt_map.txt` file which is used by haplomt_find.py. See haplomt.py for
details.

