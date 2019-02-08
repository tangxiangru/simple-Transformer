## Requirements
  * NumPy >= 1.11.1
  * TensorFlow >= 1.2 (Probably 1.1 should work, too, though I didn't test it)
  * regex
  * nltk
  * tqdm
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
* STEP 1. 下载数据：举个例子如翻译数据 
```sh
wget https://wit3.fbk.eu/archive/2016-01//texts/de/en/de-en.tgz ; tar zxvf de-en.tgz; mv de-en corpora
```
* STEP 2. 调整参数和数据目录 `hyperparams.py` 
* STEP 3. `python prepro.py` 构建的词表在 `preprocessed` 文件夹
* STEP 4. `python train.py` or [pretrained files](https://www.dropbox.com/s/fo5wqgnbmvalwwq/logdir.zip?dl=0).

## Evaluation
  * `python eval.py`.

