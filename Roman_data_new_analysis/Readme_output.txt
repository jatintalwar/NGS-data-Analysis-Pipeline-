 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/C20_1.fastq(B[m
    fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/C20_1.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/CR2Wo1_1.fastq(B[m
    fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/CR2Wo1_1.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/HP10_1.fastq(B[m
    fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/HP10_1.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/C20_2.fastq(B[m
     fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/C20_2.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/CR2Wo1_2.fastq(B[m
     fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/CR2Wo1_2.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/HP10_2.fastq(B[m
     fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/HP10_2.fastq
 
[1mthe FastQC outputs are at : ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ (B[m
   [1mchecking for illumina adapter('AGATCGGAAGAGC') in : PAIR1(B[m
 
    [1mC20_1.fastq(B[m
    [1mCR2Wo1_1.fastq(B[m
    [1mHP10_1.fastq(B[m
    [1mchecking for illumina adapter('AGATCGGAAGAGC') in : PAIR2(B[m
 
    [1mC20_2.fastq(B[m
    [1mCR2Wo1_2.fastq(B[m
    [1mHP10_2.fastq(B[m
 
    [1mquality trimming will now begin!(B[m
 
    [1mchecking for parameter file now(B[m
    [1mparameters file found!(B[m
 
 
    [1mRunning Cutadapt for PE Mates:(B[m
    [1mQuality cutoff value is: 28(B[m
 
    cutadapt -q 28 -o ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/C20_1.fastq\_trimmed.fastq -p ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/C20_2.fastq\_trimmed.fastq /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/C20_1.fastq ~/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/C20_2.fastq
    [1mQuality cutoff value is: 28(B[m
 
    cutadapt -q 28 -o ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/CR2Wo1_1.fastq\_trimmed.fastq -p ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/CR2Wo1_2.fastq\_trimmed.fastq /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/CR2Wo1_1.fastq ~/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/CR2Wo1_2.fastq
    [1mQuality cutoff value is: 28(B[m
 
    cutadapt -q 28 -o ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/HP10_1.fastq\_trimmed.fastq -p ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/HP10_2.fastq\_trimmed.fastq /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/HP10_1.fastq ~/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/HP10_2.fastq
    [1mparameters file found!(B[m
 
    [1mMapping with Tophat will now begin :(B[m
 
    [1mMaximum multihits value is: 3(B[m
    [1mRunning Tophat for C20(B[m
 
    tophat2 -o ~/pool-talwar/RNA-Seq_pipeline/Mapping/C20\_tophat_out/ -p 13 -g 3 -G ~/Masters_Thesis_Project/Genomes/Mus_musculus/GRCm38/Sequence/Bowtie2Index/genome.gtf ~/Masters_Thesis_Project/Genomes/Mus_musculus/GRCm38/Sequence/Bowtie2Index/genome /home/talwar/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/Pair1/C20_1_trimmed.fastq ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/Pair2/C20_2_trimmed.fastq
 
                                             [1mRunning HTSeq-counts now (B[m
 
    htseq-count -f 'bam' -q ~/pool-talwar/RNA-Seq_pipeline/Mapping/C20\_tophat_out/accepted_hits.bam ~/Masters_Thesis_Project/Genomes/Mus_musculus/GRCm38/Sequence/Bowtie2Index/genome.gtf > ~/pool-talwar/RNA-Seq_pipeline/Mapping/C20\_tophat_out/C20\_count.txt
   cp ~/pool-talwar/RNA-Seq_pipeline/Mapping/C20\_tophat_out/C20\_count.txt ~/pool-talwar/RNA-Seq_pipeline/Mapping/HT-Seq_counts/
    mv ~/pool-talwar/RNA-Seq_pipeline/Mapping/C20\_tophat_out/accepted_hits.bam ~/pool-talwar/RNA-Seq_pipeline/Mapping/C20\_tophat_out/C20\_accepted_hits.bam
    ln -s ~/pool-talwar/RNA-Seq_pipeline/Mapping/C20\_tophat_out/C20\_accepted_hits.bam ~/pool-talwar/RNA-Seq_pipeline/Mapping/featurecounts/
 
    [1mMaximum multihits value is: 3(B[m
    [1mRunning Tophat for CR2Wo1(B[m
 
    tophat2 -o ~/pool-talwar/RNA-Seq_pipeline/Mapping/CR2Wo1\_tophat_out/ -p 13 -g 3 -G ~/Masters_Thesis_Project/Genomes/Mus_musculus/GRCm38/Sequence/Bowtie2Index/genome.gtf ~/Masters_Thesis_Project/Genomes/Mus_musculus/GRCm38/Sequence/Bowtie2Index/genome /home/talwar/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/Pair1/CR2Wo1_1_trimmed.fastq ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/Pair2/CR2Wo1_2_trimmed.fastq
 
                                             [1mRunning HTSeq-counts now (B[m
 
    htseq-count -f 'bam' -q ~/pool-talwar/RNA-Seq_pipeline/Mapping/CR2Wo1\_tophat_out/accepted_hits.bam ~/Masters_Thesis_Project/Genomes/Mus_musculus/GRCm38/Sequence/Bowtie2Index/genome.gtf > ~/pool-talwar/RNA-Seq_pipeline/Mapping/CR2Wo1\_tophat_out/CR2Wo1\_count.txt
   cp ~/pool-talwar/RNA-Seq_pipeline/Mapping/CR2Wo1\_tophat_out/CR2Wo1\_count.txt ~/pool-talwar/RNA-Seq_pipeline/Mapping/HT-Seq_counts/
    mv ~/pool-talwar/RNA-Seq_pipeline/Mapping/CR2Wo1\_tophat_out/accepted_hits.bam ~/pool-talwar/RNA-Seq_pipeline/Mapping/CR2Wo1\_tophat_out/CR2Wo1\_accepted_hits.bam
    ln -s ~/pool-talwar/RNA-Seq_pipeline/Mapping/CR2Wo1\_tophat_out/CR2Wo1\_accepted_hits.bam ~/pool-talwar/RNA-Seq_pipeline/Mapping/featurecounts/
 
    [1mMaximum multihits value is: 3(B[m
    [1mRunning Tophat for HP10(B[m
 
    tophat2 -o ~/pool-talwar/RNA-Seq_pipeline/Mapping/HP10\_tophat_out/ -p 13 -g 3 -G ~/Masters_Thesis_Project/Genomes/Mus_musculus/GRCm38/Sequence/Bowtie2Index/genome.gtf ~/Masters_Thesis_Project/Genomes/Mus_musculus/GRCm38/Sequence/Bowtie2Index/genome /home/talwar/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/Pair1/HP10_1_trimmed.fastq ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/Pair2/HP10_2_trimmed.fastq
 
                                             [1mRunning HTSeq-counts now (B[m
 
    htseq-count -f 'bam' -q ~/pool-talwar/RNA-Seq_pipeline/Mapping/HP10\_tophat_out/accepted_hits.bam ~/Masters_Thesis_Project/Genomes/Mus_musculus/GRCm38/Sequence/Bowtie2Index/genome.gtf > ~/pool-talwar/RNA-Seq_pipeline/Mapping/HP10\_tophat_out/HP10\_count.txt
   cp ~/pool-talwar/RNA-Seq_pipeline/Mapping/HP10\_tophat_out/HP10\_count.txt ~/pool-talwar/RNA-Seq_pipeline/Mapping/HT-Seq_counts/
    mv ~/pool-talwar/RNA-Seq_pipeline/Mapping/HP10\_tophat_out/accepted_hits.bam ~/pool-talwar/RNA-Seq_pipeline/Mapping/HP10\_tophat_out/HP10\_accepted_hits.bam
    ln -s ~/pool-talwar/RNA-Seq_pipeline/Mapping/HP10\_tophat_out/HP10\_accepted_hits.bam ~/pool-talwar/RNA-Seq_pipeline/Mapping/featurecounts/
 
    [1mMapping is now complete!, the output files can be found at : ~/pool-talwar/RNA-Seq_pipeline/Mapping/
     HT-Seq count is also complete! files are at: ~/pool-talwar/RNA-Seq_pipeline/Mapping/HT-Seq_counts/
 
                                             [1mRunning Feature-count now (B[m
 
 taking these fiels for feature count as input : 
    featureCounts -a ~/Masters_Thesis_Project/Genomes/Mus_musculus/mm10/Sequence/Bowtie2Index/genome.gtf -o ~/pool-talwar/RNA-Seq_pipeline/Mapping/featurecounts/Complete_featurecounts.txt -T 13 -P -C 
     [1mFeature count is also complete! files are at: ~/pool-talwar/RNA-Seq_pipeline/Mapping/featurecounts/(B[m
 
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/C20_1.fastq(B[m
    fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/C20_1.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/CR2Wo1_1.fastq(B[m
    fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/CR2Wo1_1.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/HP10_1.fastq(B[m
    fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/HP10_1.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/C20_2.fastq(B[m
     fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/C20_2.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/CR2Wo1_2.fastq(B[m
     fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/CR2Wo1_2.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/HP10_2.fastq(B[m
     fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/HP10_2.fastq
 
[1mthe FastQC outputs are at : ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ (B[m
   [1mchecking for illumina adapter('AGATCGGAAGAGC') in : PAIR1(B[m
 
    [1mC20_1.fastq(B[m
    [1mCR2Wo1_1.fastq(B[m
    [1mHP10_1.fastq(B[m
    [1mchecking for illumina adapter('AGATCGGAAGAGC') in : PAIR2(B[m
 
    [1mC20_2.fastq(B[m
    [1mCR2Wo1_2.fastq(B[m
    [1mHP10_2.fastq(B[m
 
    [1mquality trimming will now begin!(B[m
 
    [1mchecking for parameter file now(B[m
    [1mparameters file found!(B[m
 
 
    [1mRunning Cutadapt for PE Mates:(B[m
    [1mQuality cutoff value is: 28(B[m
 
    C20_1.fastq
    C20_2.fastq
    [1mQuality cutoff value is: 28(B[m
 
    CR2Wo1_1.fastq
    CR2Wo1_2.fastq
    [1mQuality cutoff value is: 28(B[m
 
    HP10_1.fastq
    HP10_2.fastq
    [1mparameters file found!(B[m
 
    [1mMapping with Tophat will now begin :(B[m
 
    [1mMaximum multihits value is: 3(B[m
    [1mRunning Tophat for C20(B[m
 
 
                                             [1mRunning HTSeq-counts now (B[m
 
 
    [1mMaximum multihits value is: 3(B[m
    [1mRunning Tophat for CR2Wo1(B[m
 
 
                                             [1mRunning HTSeq-counts now (B[m
 
 
    [1mMaximum multihits value is: 3(B[m
    [1mRunning Tophat for HP10(B[m
 
 
                                             [1mRunning HTSeq-counts now (B[m
 
 
     HT-Seq count is now complete! files are at: ~/pool-talwar/RNA-Seq_pipeline/Mapping/HT-Seq_counts/
 
                                             [1mRunning Feature-count now (B[m
 
    taking these files for feature count as input : 
    
 
    [1mMapping is now complete!, the output files can be found at : ~/pool-talwar/RNA-Seq_pipeline/Mapping/
 
     [1mFeature count is also complete! files are at: ~/pool-talwar/RNA-Seq_pipeline/Mapping/featurecounts/(B[m
 
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/C20_1.fastq(B[m
    fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/C20_1.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/CR2Wo1_1.fastq(B[m
    fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/CR2Wo1_1.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/HP10_1.fastq(B[m
    fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/HP10_1.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/C20_2.fastq(B[m
     fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/C20_2.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/CR2Wo1_2.fastq(B[m
     fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/CR2Wo1_2.fastq
 
    [1mRunning fastqc for: /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/HP10_2.fastq(B[m
     fastqc -o ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ -t 13 -q /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/HP10_2.fastq
 
[1mthe FastQC outputs are at : ~/pool-talwar/RNA-Seq_pipeline/Quality_control/fastqc/ (B[m
   [1mchecking for illumina adapter('AGATCGGAAGAGC') in : PAIR1(B[m
 
    [1mC20_1.fastq(B[m
    [1mCR2Wo1_1.fastq(B[m
    [1mHP10_1.fastq(B[m
    [1mchecking for illumina adapter('AGATCGGAAGAGC') in : PAIR2(B[m
 
    [1mC20_2.fastq(B[m
    [1mCR2Wo1_2.fastq(B[m
    [1mHP10_2.fastq(B[m
 
    [1mquality trimming will now begin!(B[m
 
    [1mchecking for parameter file now(B[m
    [1mparameters file found!(B[m
 
 
    [1mRunning Cutadapt for PE Mates:(B[m
    [1mQuality cutoff value is: 28(B[m
 
    C20_1.fastq
    C20_2.fastq
cutadapt -q 28 -m 25 -o ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/C20_1.fastq\_trimmed.fastq -p ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/C20_2.fastq\_trimmed.fastq /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/C20_1.fastq ~/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/C20_2.fastq
    [1mQuality cutoff value is: 28(B[m
 
    CR2Wo1_1.fastq
    CR2Wo1_2.fastq
cutadapt -q 28 -m 25 -o ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/CR2Wo1_1.fastq\_trimmed.fastq -p ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/CR2Wo1_2.fastq\_trimmed.fastq /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/CR2Wo1_1.fastq ~/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/CR2Wo1_2.fastq
    [1mQuality cutoff value is: 28(B[m
 
    HP10_1.fastq
    HP10_2.fastq
cutadapt -q 28 -m 25 -o ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/HP10_1.fastq\_trimmed.fastq -p ~/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/HP10_2.fastq\_trimmed.fastq /home/talwar/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair1/HP10_1.fastq ~/pool-talwar/RNA-Seq_pipeline/Raw_data_files/pair2/HP10_2.fastq
    [1mparameters file found!(B[m
 
    [1mMapping with 'STAR' will now begin :(B[m
 
    [1mMaximum multihits value is: 3(B[m
    [1mRunning STAR for C20, C20_2_trimmed.fastq(B[m
 
    C20
    STAR --genomeDir ~/Masters_Thesis_Project/Genomes/Mus_musculus/STAR_genome/ --readFilesIn /home/talwar/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/Pair1/C20_1_trimmed.fastq /home/talwar/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/C20_2_trimmed.fastq --runThreadN 13 --outFileNamePrefix ~/pool-talwar/RNA-Seq_pipeline/Mapping/C20\_STAR_out/ --outReadsUnmapped Fastx
 
                                                                                    [1mRunning HTSeq-counts now (B[m
 
    htseq-count -q ~/pool-talwar/RNA-Seq_pipeline/Mapping/C20\_STAR_out/Aligned.out.sam ~/Masters_Thesis_Project/Genomes/Mus_musculus/GRCm38/Sequence/Bowtie2Index/genome.gtf > ~/pool-talwar/RNA-Seq_pipeline/Mapping/C20\_STAR_out/C20\_count.txt
    cp ~/pool-talwar/RNA-Seq_pipeline/Mapping/C20\_STAR_out/C20\_count.txt ~/pool-talwar/RNA-Seq_pipeline/Mapping/HT-Seq_counts/
    mv ~/pool-talwar/RNA-Seq_pipeline/Mapping/C20\_STAR_out/Aligned.out.sam ~/pool-talwar/RNA-Seq_pipeline/Mapping/C20\_STAR_out/C20\_Aligned.out.sam
    ln -s ~/pool-talwar/RNA-Seq_pipeline/C20\_STAR_out/C20\_Aligned.out.sam ~/pool-talwar/RNA-Seq_pipeline/Mapping/featurecounts/
 
    [1mMaximum multihits value is: 3(B[m
    [1mRunning STAR for CR2Wo1, CR2Wo1_2_trimmed.fastq(B[m
 
    CR2Wo1
    STAR --genomeDir ~/Masters_Thesis_Project/Genomes/Mus_musculus/STAR_genome/ --readFilesIn /home/talwar/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/Pair1/CR2Wo1_1_trimmed.fastq /home/talwar/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/CR2Wo1_2_trimmed.fastq --runThreadN 13 --outFileNamePrefix ~/pool-talwar/RNA-Seq_pipeline/Mapping/CR2Wo1\_STAR_out/ --outReadsUnmapped Fastx
 
                                                                                    [1mRunning HTSeq-counts now (B[m
 
    htseq-count -q ~/pool-talwar/RNA-Seq_pipeline/Mapping/CR2Wo1\_STAR_out/Aligned.out.sam ~/Masters_Thesis_Project/Genomes/Mus_musculus/GRCm38/Sequence/Bowtie2Index/genome.gtf > ~/pool-talwar/RNA-Seq_pipeline/Mapping/CR2Wo1\_STAR_out/CR2Wo1\_count.txt
    cp ~/pool-talwar/RNA-Seq_pipeline/Mapping/CR2Wo1\_STAR_out/CR2Wo1\_count.txt ~/pool-talwar/RNA-Seq_pipeline/Mapping/HT-Seq_counts/
    mv ~/pool-talwar/RNA-Seq_pipeline/Mapping/CR2Wo1\_STAR_out/Aligned.out.sam ~/pool-talwar/RNA-Seq_pipeline/Mapping/CR2Wo1\_STAR_out/CR2Wo1\_Aligned.out.sam
    ln -s ~/pool-talwar/RNA-Seq_pipeline/CR2Wo1\_STAR_out/CR2Wo1\_Aligned.out.sam ~/pool-talwar/RNA-Seq_pipeline/Mapping/featurecounts/
 
    [1mMaximum multihits value is: 3(B[m
    [1mRunning STAR for HP10, HP10_2_trimmed.fastq(B[m
 
    HP10
    STAR --genomeDir ~/Masters_Thesis_Project/Genomes/Mus_musculus/STAR_genome/ --readFilesIn /home/talwar/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/Pair1/HP10_1_trimmed.fastq /home/talwar/pool-talwar/RNA-Seq_pipeline/Quality_trimmed_files/HP10_2_trimmed.fastq --runThreadN 13 --outFileNamePrefix ~/pool-talwar/RNA-Seq_pipeline/Mapping/HP10\_STAR_out/ --outReadsUnmapped Fastx
 
                                                                                    [1mRunning HTSeq-counts now (B[m
 
    htseq-count -q ~/pool-talwar/RNA-Seq_pipeline/Mapping/HP10\_STAR_out/Aligned.out.sam ~/Masters_Thesis_Project/Genomes/Mus_musculus/GRCm38/Sequence/Bowtie2Index/genome.gtf > ~/pool-talwar/RNA-Seq_pipeline/Mapping/HP10\_STAR_out/HP10\_count.txt
    cp ~/pool-talwar/RNA-Seq_pipeline/Mapping/HP10\_STAR_out/HP10\_count.txt ~/pool-talwar/RNA-Seq_pipeline/Mapping/HT-Seq_counts/
    mv ~/pool-talwar/RNA-Seq_pipeline/Mapping/HP10\_STAR_out/Aligned.out.sam ~/pool-talwar/RNA-Seq_pipeline/Mapping/HP10\_STAR_out/HP10\_Aligned.out.sam
    ln -s ~/pool-talwar/RNA-Seq_pipeline/HP10\_STAR_out/HP10\_Aligned.out.sam ~/pool-talwar/RNA-Seq_pipeline/Mapping/featurecounts/
    [1mMapping is now complete!, the output files can be found at : ~/pool-talwar/RNA-Seq_pipeline/Mapping/
     HT-Seq count is also complete! files are at: ~/pool-talwar/RNA-Seq_pipeline/Mapping/HT-Seq_counts/(B[m
 
 
                                                                                     [1mRunning Feature-count now (B[m
 
 taking these fiels for feature count as input : 
    featureCounts -a ~/Masters_Thesis_Project/Genomes/Mus_musculus/mm10/Sequence/Bowtie2Index/genome.gtf -o ~/pool-talwar/RNA-Seq_pipeline/Mapping/featurecounts/Complete_featurecounts_STAR.txt -T 13 -P -C ~/pool-talwar/RNA-Seq_pipeline/Mapping/featurecounts/*.sam
     [1mFeature count is also complete! files are at: ~/pool-talwar/RNA-Seq_pipeline/Mapping/featurecounts/(B[m
 
