# U-Net-by-Python2.7
医療画像のセグメンテーションに使えます

Overview
-
網膜の毛細血管のセグメンテーションを行ったhttps://github.com/orobix/retina-unet</br>
を応用して医用画像のセグメンテーションを行います。
医用画像に向いている点としては、局所的特徴と全体の位置情報を同時に学習できる点と、パッチ処理により、少ない画像枚数でも高精度なセグメンテーションができる点にあります。実装に苦労をしたので、手順等詳しく説明します。

- Environment
OS:ubuntu16.04</br>
Python:2.7</br>
GPU:GTX1050ti(学習に1日ぐらいかかります、できれば複数枚使いたいです)</br>

CondaでPython2.7の仮想環境を作成し、仮想環境内で実行します。</br>
- 仮想環境作成</br>
$conda create -n 環境名 python=2.7</br>
- 起動と終了</br>
$conda activate 環境名</br>
$conda deactivate</br>

- 仮想環境に追加(GPUを使用するため)</br>
tensorflow:最新版をインストール，CPUは使用しないため，tensorboardは残してtensorflowはアンインストール</br>
tensorflow-gpu:1.4.1をインストール</br>
keras:2.0.2</br>

- 以下バージョン指定でインストール</br>
numpy:最新</br>
matplotlib:最新</br>
opencv-python:最新</br>
pillow:最新</br>
h5py:2.8.0</br>
scikit-learn:0.19.2</br>
chainer:最新</br>
Configparser 3.5.0</br>
pip 10.0.1</br>

Procedure
-
1. DRIVEフォルダにテストデータと学習データを入れる
1. $python prepare_datasets_DRIVE.py でデータセットの読み込みを行う
1. $python run_training.py で学習が始まる
1. $python run_testing.py でテスト開始
1. 結果がtestフォルダに出力されます

- エラーが出た場合はインストールしたパッケージのバージョンがあっているか確かめてください</br>
  経験上、殆どのエラーがバージョンの事に関するエラーでした。
