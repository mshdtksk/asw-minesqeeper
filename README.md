# 巡回セールスマン問題クイズ

## 概要
巡回セールスマン問題（TSP: Traveling Salesman Problem）を使ったインタラクティブなクイズゲームです。複数の都市を効率的に巡回する最短ルートを視覚的に選択して学習できます。

## 特徴

### 🎯 教育的価値
- 組み合わせ最適化問題の理解
- 視覚的学習による直感的な理解
- 厳密解と近似解の違いを体験

### 🔢 解法アルゴリズム
- **10都市以下**: 厳密解（全順列探索）
- **11都市以上**: 近似解（最近傍法 + 2-opt改善）

### 🎮 ゲーム機能
- 4つの選択肢から最短ルートを選択
- 上位4位の競合ルートで高難易度を実現
- リアルタイムでルートを視覚化
- 詳細な解答解説付き

## 使い方

### 1. 都市の設定
#### ランダム生成
```
都市の数: 3-15都市（デフォルト: 10都市）
座標の最大値: 10-1000（デフォルト: 100）
```

#### 手動入力
- 各都市のX,Y座標を個別に設定可能
- より具体的な問題設定が可能

### 2. クイズの進行
1. **問題表示**: 都市の配置を確認
2. **選択肢選択**: 4つのルート候補から最短を選択
3. **結果確認**: 正解発表と詳細分析

### 3. 結果画面の見方
- **順位表示**: 全選択肢を距離順で表示
- **計算方法**: 厳密解/近似解の区別
- **難易度判定**: 距離差による難易度評価
  - 1%未満: 非常に高難易度
  - 1-3%: 高難易度
  - 3-5%: 中難易度
  - 5%以上: 初級レベル

## 技術仕様

### 使用技術
- **HTML5**: 構造とマークアップ
- **CSS3**: スタイリングとレスポンシブデザイン
- **JavaScript**: ロジックとアルゴリズム実装
- **Canvas API**: ルートの視覚化

### アルゴリズム詳細

#### 厳密解（10都市以下）
```javascript
// 全順列生成: O((n-1)!)
function generateAllRoutes(cityList)
// 最短ルート保証
```

#### 近似解（11都市以上）
```javascript
// 最近傍法: O(n²)
function nearestNeighbor(cityList, startCity)

// 2-opt改善: O(n²)
function twoOpt(cityList, initialTour, maxIterations)
```

### 計算量
| 都市数 | 厳密解の計算量 | 近似解の精度 |
|--------|---------------|--------------|
| 3都市  | 2! = 2        | 100%         |
| 5都市  | 4! = 24       | 100%         |
| 10都市 | 9! = 362,880  | 100%         |
| 15都市 | -             | 95-98%       |

## ファイル構成
```
tsp-quiz/
├── index.html          # メインアプリケーション
├── README.md          # このファイル
└── docs/              # ドキュメント（オプション）
    ├── screenshots/   # スクリーンショット
    └── algorithm.md   # アルゴリズム詳細説明
```

## 動作環境
- **ブラウザ**: Chrome, Firefox, Safari, Edge（最新版）
- **JavaScript**: ES6+対応
- **Canvas**: HTML5対応
- **インターネット接続**: 不要（スタンドアロン動作）

## インストール・実行方法

### 方法1: 直接実行
```bash
# ファイルをダウンロード
wget https://example.com/tsp-quiz.html

# ブラウザで開く
open tsp-quiz.html
```

### 方法2: ローカルサーバー
```bash
# Python 3の場合
python -m http.server 8000

# Node.jsの場合
npx http-server

# ブラウザでアクセス
http://localhost:8000
```

## 学習目標

### 初級レベル
- [ ] TSPの基本概念理解
- [ ] 最短ルートの視覚的認識
- [ ] 組み合わせ爆発の体感

### 中級レベル
- [ ] 最近傍法アルゴリズムの理解
- [ ] 局所最適解と大域最適解の違い
- [ ] ヒューリスティック手法の必要性

### 上級レベル
- [ ] 2-opt改善法の仕組み
- [ ] 計算量と実用性のトレードオフ
- [ ] 他の最適化アルゴリズムとの比較

## 教育現場での活用例

### 数学教育
- **組み合わせ論**: 順列・組み合わせの実践的理解
- **グラフ理論**: 最短路問題の導入
- **統計学**: 最適化と確率的手法

### 情報科学教育
- **アルゴリズム**: 計算量解析の実例
- **データ構造**: グラフとその応用
- **AI・機械学習**: 最適化問題の基礎

### 実用例
- **物流最適化**: 配送ルート設計
- **製造業**: 生産スケジューリング
- **都市計画**: 交通網設計

## トラブルシューティング

### よくある問題

#### 1. 選択肢が生成されない
```
原因: 都市の配置が特殊（直線状など）
解決: 「新しいクイズ」で都市を再生成
```

#### 2. 計算時間が長い
```
原因: 都市数が多すぎる（12都市以上）
解決: 都市数を10以下に減らす
```

#### 3. ブラウザでの表示崩れ
```
原因: 古いブラウザの使用
解決: 最新版ブラウザへのアップデート
```

## カスタマイズ

### 難易度調整
```javascript
// 選択肢の数を変更
const NUM_OPTIONS = 4; // デフォルト値

// 厳密解の都市数上限を変更
const EXACT_SOLUTION_LIMIT = 10; // デフォルト値
```

### 視覚設定
```css
/* キャンバスサイズ */
.quiz-main-canvas { width: 500px; height: 400px; }
.option-canvas { width: 200px; height: 150px; }

/* カラーテーマ */
:root {
  --primary-color: #3498db;
  --success-color: #2ecc71;
  --danger-color: #e74c3c;
}
```

## ライセンス
このプロジェクトはMITライセンスの下で公開されています。教育目的での自由な利用・改変が可能です。

## 貢献

### バグ報告
- Issueでの報告をお願いします
- 再現手順の詳細な記載をお願いします

### 機能要望
- 教育現場での具体的なニーズ
- アルゴリズムの改善案
- UI/UXの改善提案

### 開発参加
1. Fork this repository
2. Create feature branch
3. Commit your changes
4. Push to the branch
5. Create Pull Request

## 更新履歴

### v1.0.0 (2024-12-XX)
- 初回リリース
- 基本的なTSPクイズ機能
- 厳密解・近似解の自動切り替え
- 視覚的ルート表示

### 今後の予定
- [ ] 複数の最適化アルゴリズム対応
- [ ] 統計情報の記録・表示
- [ ] チューニング可能なパラメータ
- [ ] 多言語対応
- [ ] モバイル対応の改善

## 参考文献
- Applegate, D. L., et al. "The traveling salesman problem: a computational study" (2007)
- Lawler, E. L., et al. "The Traveling Salesman Problem" (1985)
- Lin, S., & Kernighan, B. W. "An effective heuristic algorithm for the traveling-salesman problem" (1973)
