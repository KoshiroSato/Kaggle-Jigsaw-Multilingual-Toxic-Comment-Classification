# Jigsaw Multilingual Toxic Comment Classification
https://www.kaggle.com/c/jigsaw-multilingual-toxic-comment-classification

このリポジトリでは、Kaggle Jigsaw Multilingual Toxic Comment Classificationにて、157位(銅メダル)を獲得した際に使用したノートブックを公開しています。私は、Dezso Ribli氏が公開していた2つのノートブック(xlm-roBERTaのファインチューニングとトレーニング)をスターターとしてコンペティションを始めました。

https://www.kaggle.com/riblidezso/finetune-xlm-roberta-on-jigsaw-test-data-with-mlm

https://www.kaggle.com/riblidezso/train-from-mlm-finetuned-xlm-roberta-large

## ファインチューニング
コンペティショントレーニングデータ(英語)をYandexAPIを使用して、6ヶ国語に翻訳された外部データセットとコンペティションテストデータを使用しています。

#### ./src/finetune-xlm-roberta-on-jigsaw-test-data-with-mlm.ipynb


## トレーニング

・コンペティショントレーニングデータ(英語)をGoogleAPIを使用して6ヶ国語に翻訳された外部データセットを使用し、トレーニングしたモデル(Public Score: 0.9425, Private Score: 0.9409)

#### ./src/mlm-finetuned-xlm-r-large.ipynb

・イタリア語のTweetとFacebookコメントのデータセット(前処理で絵文字と英数字以外の記号類を除去)を追加し、拡張されたデータセットでトレーニングしたモデル(Public Score: 0.9431, Private Score: 0.9428)

#### ./src/mlm-finetuned-xlm-r-large_with-extended-datasets.ipynb

の2種類があります。

提出に当たってはそれら2つのモデルの推論と合わせて、the1owl氏の公開ノートブックとハードコーディングによる重み付けをし、アンサンブル後に提出しています。
(Public Score: 0.9474, Private Score: 0.9462)

the1owl氏の公開ノートブック

https://www.kaggle.com/jazivxt/howling-with-wolf-on-l-genpresse

環境は、KaggleNotebooksで、すべてTPUを使ってトレーニングされています。
