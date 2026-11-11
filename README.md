
[torabo-tsuki LP](https://github.com/sekigon-gonnoc/torabo-tsuki-lp)用のZMKファームウェア

* _centralがついているuf2をトラックボールがついている方に、_peripheralを反対側に書き込んでください
* キーマップはkeymap-editorおよびzmk-studioで編集できます

### zmk studioマッピング
| 記号 | zmk      |
| --- | ------- |
| ^   | Keyboard Equals and Plus |
| \   | Keyboard International3 |
| @   | Keyboard Left Brace |
| ;   | Keyboard SemiColon and Colon |
| :   | Keyboard Left Apos and Double |
| _   | Keyboard International1 |
| [   | Keyboard Right Brace |
| ]   | Keyboard Backslash and Pipe |
| /   | Keyboard ForwardSlash and QuestionMark |

### Windows（RDP 仮想デスクトップ）

Windows 用の Hyper レイヤーで、全画面 RDP とローカルの仮想デスクトップを切り替えます。

| 操作 | 動作 |
| --- | --- |
| Hyper + C | 左の仮想デスクトップへ移動 |
| Hyper + V | 右の仮想デスクトップへ移動 |

各キーは、**Ctrl → Alt → Home の順に押すマクロ**を実行してから、`Win + Ctrl + ←/→` を送信します。Ctrl・Alt・Homeを一括送信する方式では、RDPの接続バーにフォーカスが移らないことがあったため、キー操作を分離しました。
前半の順次入力は診断用ファームウェアで短押し成功を確認済みです。後半を含む連続操作は実機未確認のため、操作間の待機時間150msを維持しています。

ウィンドウ配置は Windows 標準の `Win + 矢印` を使用します。Hyper キーへの重複割り当てはありません。

### 診断用（RDP後半の待機時間）

このブランチだけで、前半の `Ctrl → Alt → Home` と後半の `Win + Ctrl + ←` を同じ方式に統一し、その間の待機時間を比較する。前半と後半のキー送信方法や、各キーの押下時間（40ms）は全パターン共通。

| キー | 前半終了後の待機 |
| --- | --- |
| Hyper + I | 0ms |
| Hyper + A | 20ms |
| Hyper + O | 40ms |
| Hyper + - | 80ms |
| Hyper + E | 150ms（成功済みの基準） |

`Hyper + C/V` は従来のマクロのまま（未変更）。

RDP全画面またはローカルで、**右側の仮想デスクトップから**各キーを短押しして左へ切り替わるか確認する。成功した場合は右へ戻してから次のパターンを試す。0msなど短い設定では、Bluetoothによるキー状態の送信がまとめられて結果が不安定になる可能性があるため、各値を複数回試す。通常版 `master` は変更していない。
