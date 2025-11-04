# Fruit Matching Puzzle Game

これは Unity を用いて開発された、かわいらしいグラフィックとアニメーションが特徴の 3D フルーツパズルゲームです。プレイヤーは目標のフルーツを揃えてステージをクリアしていきます。

## 🧭 背景

- 既存の 3D オブジェクト Match 系 Asset を使用して開発効率を高めました
- アセットを読み解きつつ、ゲーム性の拡張やビジュアル面の強化を目的としています
- Match3D 系の既存ゲームとは異なり、女の子要素（キャラクターや演出）を加えた独自性のある展開を行います

## 🎯 目的

- 女性要素の追加（キャラクターやビジュアル）
- ゲーム性の再構成（ゴール提示、マッチ制御）
- 全体クオリティの向上（UI、アニメーション、SE）

## 🚧 開発上の課題と対策

### ✨ 見た目のクオリティ向上
- アイコンを高解像度の 3D モデルに差し替え（AI生成画像などを活用）
- UI ボタンすべてにアクション（押下アニメ・サウンド）を設定
- 選択されたオブジェクトをハイライト表示
  - Shader による枠線追加（参考: [Unity ShaderLab Outline by Zenn](https://zenn.dev/r_ngtm/articles/shaderlab-outline)）
  - オブジェクトのサイズに応じて枠の太さを調整

### 📦 アプリサイズ削減
- 音声データは必要な品質まで圧縮して使用
- 不要なアセットはビルド対象外へ除外

### 🌀 アニメーション調整
- 一時的にオブジェクトの重力や Drag 値を変更して、ふわっとした浮遊感を演出
- DOTween や Rigidbody 設定で加速度・落下感を制御

### 🎯 ゴールオブジェクトのUI表示
- 3Dモデルの表示枠からのはみ出しを回避するため、イラスト画像に差し替え
- イラストは生成AIで事前生成・登録し、見た目と収まりのよい表示に対応

## 🎮 ゲーム概要

- ステージごとに指定されたフルーツアイテムを 3 つ揃えるとスコア獲得
- 一定数のアイテムを揃えるとステージクリア
- 制限時間内にクリアできなければゲームオーバー
- チュートリアル完備（初回のみ表示）
- コンボシステムあり

## 🏗️ 構成ファイルとクラス

### GameManager.cs
- ゲーム全体の進行を管理する中核クラス

### StageManager.cs
- ステージの初期化と盤面生成を行うクラス

### ItemSlotManager.cs
- アイテムスロットの管理を担当

### TimeManager.cs
- ゲーム内の制限時間を管理

### SoundManager.cs
- 効果音およびBGMの再生を担当

### TutorialManager.cs
- 初回プレイ時のチュートリアル制御

## 📦 使用ライブラリ

- [UniTask](https://github.com/Cysharp/UniTask)
- [DOTween](http://dotween.demigiant.com/)
- [TextMeshPro](https://docs.unity3d.com/Packages/com.unity.textmeshpro@latest)

## 🚀 実行方法

1. Unity（推奨バージョン：2021.3 以降）でプロジェクトを開く
2. GameManager をシーンに配置
3. プレハブ／UI／サウンドのリンク設定
4. 実行するとタイトル画面が表示され、ゲームが開始できます

## 📁 リソース構造（例）

```
Assets/
├── Scripts/
├── Prefabs/
├── Scenes/
└── Resources/
    └── GameData/Stages/*.asset
```

## 💬 補足

- ステージデータは `Resources/GameData/Stages` から読み込み
- `SaveData` は外部の GirlGameToolkit により管理

---



<p>
  <img src="https://github.com/user-attachments/assets/1f4917af-d119-44a3-a621-ed37c285c966" alt="Image 1" height="500" />
  <img src="https://github.com/user-attachments/assets/902b1053-9fa5-422b-b7cb-d9032ff04a50" alt="Image 2" height="500" />
  <img src="https://github.com/user-attachments/assets/2ef99fd7-3ced-4a61-9fe9-d62959a2a76d" alt="Image 3" height="500" />
  <img src="https://github.com/user-attachments/assets/e452a7c7-425e-4124-82ef-0e30709ad4de" alt="Image 4" height="500" />
  <img src="https://github.com/user-attachments/assets/f42cd2a1-f97a-4c06-93bc-3216dd926bbe" alt="Image 5" height="500" />
  <img src="https://github.com/user-attachments/assets/42565084-542a-45e8-8e2f-0bae8dab6bc6" alt="Image 6" height="500" />
  <img src="https://github.com/user-attachments/assets/a642452b-5629-41f9-8fc5-6333e08fd2f8" alt="Image 7" height="500" />
</p>
