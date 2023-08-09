# shell_assembler_bacterial_plant_fungal_genomes
A pure shell assembler that takes only the directory path and does all the cleaning of the reads, mapping, remapping and assembly. From start to finish everything by providing a simple directory path. You dont have to provide anything else just the directory path of the fastq files.It works with MiSeq, NextSeq, NovaSeq

```
shell_command
hi there i am a denovo assembler script which will check your fastq files, \
clean then and assemble them coming from the illumina platform. I take MiSeq, NextSeq,\
NovaSeq reads, you can just clean, or clean and map or clean and assemble.As of the \
current it supports the cleaning through the fastp, mapping through the bowtie2 and \
assembly using the spades I will add more assembler to this interface and also multiple \
assembly configurations. Currently, it supports 45, 55, 65 kmers you can change the \
kmer according to the assembly preferences.\
# if from cleaning only 
main ✗ $ sh genome_cleaner.sh
enter the name of the directory: /Users/gauravsablok/Desktop/GitHub/shell_builder \
do you want to clean the reads:yes \
enter the number of the threads:1 \
do you want to map the reads:no \
enter the name of the bowtie index:no \
do you want to assemble the reads:no \
Processing the cleaning of the reads file from the sequencing runs
fastp --in1 /Users/gauravsablok/Desktop/GitHub/shell_builder/text.txt \
        --out1 /Users/gauravsablok/Desktop/GitHub/shell_builder/text.txt.cleaned.R1 \
        --in2 /Users/gauravsablok/Desktop/GitHub/shell_builder/text1 \
        --out2 /Users/gauravsablok/Desktop/GitHub/shell_builder/text.txt.cleaned.R2 --threads 1 \
# if cleaning to remapping files 
enter the name of the directory: /Users/gauravsablok/Desktop/GitHub/shell_builder \
do you want to clean the reads:yes \
enter the number of the threads:1 \
do you want to map the reads:yes \
enter the name of the bowtie index:gaurav \
do you want to assemble the reads:no \
Processing the cleaning of the reads file from the sequencing runs \
fastp --in1 /Users/gauravsablok/Desktop/GitHub/shell_builder/text.txt \
        --out1 /Users/gauravsablok/Desktop/GitHub/shell_builder/text.txt.cleaned.R1 \
        --in2 /Users/gauravsablok/Desktop/GitHub/shell_builder/text1 \
        --out2 /Users/gauravsablok/Desktop/GitHub/shell_builder/text.txt.cleaned.R2 --threads 1 \
bowtie2-build gaurav gaurav \
bowtie2 -t -x gaurav -p 1 --very-sensitive-local -1 \
       /Users/gauravsablok/Desktop/GitHub/shell_builder/text.txt.cleaned.R1 \
         -2 /Users/gauravsablok/Desktop/GitHub/shell_builder/text3.txt.cleaned.R2 \
                 -S gaurav.sam --no-unal --al-conc gaurav.aligned.fastq \                          
# if from cleaning to assembly configuration \
enter the name of the directory: /Users/gauravsablok/Desktop/GitHub/shell_builder \
do you want to clean the reads:yes \
enter the number of the threads:1 \
do you want to map the reads:yes \
enter the name of the bowtie index:gaurav \
do you want to assemble the reads:yes \
Processing the cleaning of the reads file from the sequencing runs \
fastp --in1 /Users/gauravsablok/Desktop/GitHub/shell_builder/text.txt \
        --out1 /Users/gauravsablok/Desktop/GitHub/shell_builder/text.txt.cleaned.R1 \
        --in2 /Users/gauravsablok/Desktop/GitHub/shell_builder/text1 \
        --out2 /Users/gauravsablok/Desktop/GitHub/shell_builder/text.txt.cleaned.R2 --threads 1 \
bowtie2-build gaurav gaurav \
bowtie2 -t -x gaurav -p 1 --very-sensitive-local -1 \
       /Users/gauravsablok/Desktop/GitHub/shell_builder/text.txt.cleaned.R1 \
         -2 /Users/gauravsablok/Desktop/GitHub/shell_builder/text3.txt.cleaned.R2 \
                 -S gaurav.sam --no-unal --al-conc gaurav.aligned.fastq \
spades.py -1 /Users/gauravsablok/Desktop/GitHub/shell_builder/text.aligned.R1.fastq \
       -2 /Users/gauravsablok/Desktop/GitHub/shell_builder/*.aligned.R2.fastq \
                 --careful --threads 1 --tmp-dir  -k 45,55,65,75 \
                                 -o /Users/gauravsablok/Desktop/GitHub/shell_builder/ \
```
Gaurav Sablok \
Senior Postdoctoral Fellow \
Faculty of Natural and Agricultural Sciences Room 7-35, \
Agricultural Sciences Building University of Pretoria, \
Private Bag X20 Hatfield 0028, South Africa \
Academia : https://up-za.academia.edu/GauravSablok \
Frontiers: https://loop.frontiersin.org/people/33293/overview \
ORCID: https://orcid.org/0000-0002-4157-9405 \
WOS: https://www.webofscience.com/wos/author/record/C-5940-2014 \
Github:https://github.com/sablokgaurav \
Linkedin: https://www.linkedin.com/in/sablokgaurav/ \
ResearchGate: https://www.researchgate.net/profile/Gaurav-Sablok
