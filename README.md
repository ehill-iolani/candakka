# candakka

The candakka pipeline was made to assembly small bacterial genomes using fast-basecalled ONT reads:
1) Canu error corrects the fastq's and generates a draft assembly
2) Medaka polishes the draft assembly
3) Prokka annotates the polished assembly
5) Ropro then summarizes the Prokka annotation search to identify completion and tentative BLAST identification

Important: candakka assumes all the fastq files live in a directory called "fastq_sup_demultiplexed". Please place all your fastqs in a directory with this name before running the pipeline.

Example input:
```
candakka -i bl84_all -s 5.7 -c 56
```

A docker container is available here:
```
docker pull ethill/genome_assembly:candakka
```

Help message:
```
  -h    help (prints this message)
  -v    version
  -x    maximum sample coverage; default is 100
  -n    minimum sample coverage; default is 5
  -c    number of cores to use; default is 4
  -i    name of fastq file w/o file ending
  -s    estimated size of the genome +/- 500kb
```
