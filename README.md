# Personalized Real-time Flaming Risk Prediction

IIAI AAI 2025 Winterに採録された、文章の炎上リスクをリアルタイムで予測する手法の実装です。

## 🌟 プロジェクト概要
SNS等における「炎上」や「不快感」の基準は、人それぞれの価値観によって異なります。本プロジェクトでは、判定基準となるデータセットを入れ替えるだけで、ユーザー個人の基準に最適化したリスク判定をリアルタイムで行うモデルを提案しました。

## 🚀 特徴
- **パーソナライズ判定**: 固定の学習モデルではなく、比較対象のデータ（Safe/Out）を差し替えることで、個別の基準に対応可能です。
- **BERT + Mean Pooling**: BERTの最終層から得られるトークン埋め込みを平均化し、文全体の高精度なベクトル（分散表現）を抽出します。
- **高速な類似度判定**: コサイン類似度を用いたk-NN的なアプローチにより、未知の文章に対してリアルタイムでのリスク算出を実現します。

## 📂 ディレクトリ構成
- `01_data_preprocessing.ipynb`: テキストデータのクレンジングと、BERTによるベクトル化（特徴量抽出）を行います。
- `02_model_evaluation.ipynb`: 抽出したベクトルを用いて、コサイン類似度に基づいた成功率（精度）の計算と評価を行います。

## 🛠 技術スタック
- **Language**: Python 3.x
- **Library**: PyTorch, Hugging Face Transformers, Scikit-learn, Pandas, Matplotlib
- **Model**: `bert-base-uncased` (BERT)

## 📈 実績
- **IIAI AAI 2025 Winter Full Paper Accepted**
- 実験データにおける高い分類精度を達成（詳細はノートブック内の評価結果を参照）。

## 📖 使い方
1. `data/` フォルダに判定基準としたいCSVファイルを配置します。
2. `01_data_preprocessing.ipynb` を実行し、データをクレンジング・ベクトル化します。
3. `02_model_evaluation.ipynb` を実行することで、精度の検証とリスク予測が実行されます。
