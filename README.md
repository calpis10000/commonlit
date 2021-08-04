# CommonLit Readability Prize

## このリポジトリは
[CommonLit Readability Prize](https://www.kaggle.com/c/commonlitreadabilityprize)コンペに参加した際の、作業用リポジトリです。

## 結果
- [Public 143 / Private 395]
- shake downでメダル圏外。それでも前を向く。

## フォルダ構成
- 実質的なコードは、`02_nb`フォルダに全部入ってます。
- 実験記録は、Issuesに書かれています。
- notebookの番号は、022まではIssuesの添字と対応しており、それ以降はIssue numberと対応します。
- 番号030まではlocalで実行し、それ以降はGoogle Colabで実行しています。

## 最終モデル
- 以下3つのアンサンブル(※ 最終subでは、公開notebookもアンサンブル)
  - [02_nb/058-train-02.ipynb](https://github.com/calpis10000/commonlit/blob/0e77caa364cce8ef112a0112bb081595c4035d6e/02_nb/058-train-02.ipynb): roberta-large, batch size 12, epoch 5, kl_divergence loss, 単語カウントの特徴追加
  - [02_nb/060-train-01.ipynb](https://github.com/calpis10000/commonlit/blob/0e77caa364cce8ef112a0112bb081595c4035d6e/02_nb/060-train-01.ipynb): 058-02 + TfidfVectorizer特徴
  - [02_nb/060-train-02.ipynb](https://github.com/calpis10000/commonlit/blob/0e77caa364cce8ef112a0112bb081595c4035d6e/02_nb/060-train-02.ipynb): 058-02 + CountVectorizer特徴



## 主に参考にしたnotebook
- https://www.kaggle.com/andretugan/lightweight-roberta-solution-in-pytorch
  - こちらをベースに改修を加えました
- https://www.kaggle.com/maunish/clrp-pytorch-roberta-pretrain
  - こちらのベースモデルをroberta-largeに変更したものを、pre-trainedモデルとして使用しました。
- https://www.kaggle.com/andretugan/pre-trained-roberta-solution-in-pytorch
- https://www.kaggle.com/rhtsingh/commonlit-readability-prize-roberta-torch-infer-3
  - 最終subは、自前のモデルと上記2つをアンサンブルしたものと、自前モデルのみのアンサンブルを選択しました。
  - 上記2つとのアンサンブルは、こちらを参考にしました → https://www.kaggle.com/andretugan/commonlit-two-models
