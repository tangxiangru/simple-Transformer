

# Requirement
- python 3.4+
- pytorch 0.4.1+
- tqdm
- numpy


# Usage

## Some  tools:



```bash
wget https://raw.githubusercontent.com/moses-smt/mosesdecoder/master/scripts/tokenizer/tokenizer.perl
wget https://raw.githubusercontent.com/moses-smt/mosesdecoder/master/scripts/share/nonbreaking_prefixes/nonbreaking_prefix.de
wget https://raw.githubusercontent.com/moses-smt/mosesdecoder/master/scripts/share/nonbreaking_prefixes/nonbreaking_prefix.en
sed -i "s/$RealBin\/..\/share\/nonbreaking_prefixes//" tokenizer.perl
wget https://raw.githubusercontent.com/moses-smt/mosesdecoder/master/scripts/generic/multi-bleu.perl
```



### 1) Preprocess the data.
```bash

python preprocess.py -train_src data/train.src -train_tgt data/train.tgt -valid_src data/val.src -valid_tgt data/val.tgt -save_data data/multi.low.pt
```

### 2) Train the model
```bash
python train.py -data data/multi.low.pt -save_model trained -save_mode best -proj_share_weight -label_smoothing
```
> use the `-embs_share_weight` flag to share source/target word embedding

### 3) Test the model
```bash
python translate.py -model trained.chkpt -vocab data/multi.low.pt -src data/test.en.src
```