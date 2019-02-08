## Requirements
  * NumPy >= 1.11.1
  * TensorFlow >= 1.2 (Probably 1.1 should work, too, though I didn't test it)
  * regex
  * nltk
  * 直接对word构建词表(没有采用bpe 或者 word-piece)if you want.
  * 记得调learning rate


## File description
  * `hyperparams.py` 参数flag
  * `prepro.py` 对source和target构建词表
  * `data_load.py` load和batch
  * `modules.py` encoder/decoder
  * `train.py` 训练
  * `eval.py` 测试

## Training
* STEP 1. Download [IWSLT 2016 German–English parallel corpus](https://wit3.fbk.eu/download.php?release=2016-01&type=texts&slang=de&tlang=en) and extract it to `corpora/` folder.
```sh
wget -qO- --show-progress https://wit3.fbk.eu/archive/2016-01//texts/de/en/de-en.tgz | tar xz; mv de-en corpora
```
* STEP 2. Adjust hyper parameters in `hyperparams.py` if necessary.
* STEP 3. Run `prepro.py` to generate vocabulary files to the `preprocessed` folder.
* STEP 4. Run `train.py` or download the [pretrained files](https://www.dropbox.com/s/fo5wqgnbmvalwwq/logdir.zip?dl=0).

## Evaluation
  * Run `eval.py`.

