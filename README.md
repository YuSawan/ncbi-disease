# NCBI disease

NCBI disease corpus - related stuff

Original data available from
<http://www.ncbi.nlm.nih.gov/CBBresearch/Dogan/DISEASE/>

## Conversion

### Original data to `.ann` standoff

    python tools/ncbidisease2ann.py original-data/train/NCBItrainset_corpus.txt standoff/train
    python tools/ncbidisease2ann.py original-data/devel/NCBIdevelopset_corpus.txt standoff/devel
    python tools/ncbidisease2ann.py original-data/test/NCBItestset_corpus.txt standoff/test

### Standoff to CoNLL

    git clone git@github.com:spyysalo/standoff2conll.git
    for i in train devel test; do
        python standoff2conll/standoff2conll.py -1 Disease standoff/$i > conll/$i.tsv
    done
