# Jigsaw Multilingual Toxic Comment Classification
https://www.kaggle.com/c/jigsaw-multilingual-toxic-comment-classification

このリポジトリでは、Kaggle Jigsaw Multilingual Toxic Comment Classificationにて、157位(銅メダル)を獲得した際に使用したノートブックを公開しています。私は、Dezso Ribli氏が公開していた2つのノートブック(roBERTaのファインチューニングとトレーニング)をスターターとしてコンペティションを始めました。

https://www.kaggle.com/riblidezso/finetune-xlm-roberta-on-jigsaw-test-data-with-mlm
https://www.kaggle.com/riblidezso/train-from-mlm-finetuned-xlm-roberta-large

ファインチューニングでは、元の競技トレーニングデータ(英語)をYandexAPIを使用して6ヶ国語に翻訳された外部データセットと競技テストデータを使用しています。ファインチューニングされたモデルは、input/fine-tuned-modelディレクトリに格納されています。
トレーニングでは、元の競技トレーニングデータ(英語)をGoogleAPIを使用して6ヶ国語に翻訳された外部データセットを使用しモデルをトレーニングしたもの(Private Score: 0.9409, Public Score: 0.9425)と、それにイタリア語のヘイトスピーチ検出のデータセットを追加し、拡張されたデータセットでトレーニングしたモデル(Private Score: 0.9428, Public Score: 0.9431)の2種類があります。

使用した外部データセット
https://www.kaggle.com/miklgr500/jigsaw-train-multilingual-coments-google-api
https://www.kaggle.com/ma7555/jigsaw-train-translated-yandex-api
https://www.kaggle.com/alansun17904/toxic-comment-detection-multilingual-extended

提出に当たってはそれら2つのモデルの推論と合わせて、the1owl氏の公開ノートブックとハードコーディングによる重み付けをし、アンサンブル後に提出しています。
(Private Score: 0.9462, Public Score: 0.9474)

the1owl氏の公開ノートブック
https://www.kaggle.com/jazivxt/howling-with-wolf-on-l-genpresse

環境は、KaggleNotebooksで、すべてTPUを使ってトレーニングされています。