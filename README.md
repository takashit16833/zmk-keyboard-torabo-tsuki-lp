
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
診断用ファームウェアの `Hyper + I`（後半の追加待機0ms）が実機で安定動作したため、`Hyper + C/V` に同じ送信順序・待機設定を適用しています。各キー操作間の標準待機（40ms）は維持し、追加の150ms待機は廃止しました。右方向の連続動作は最終版ファームウェアで要確認です。

ウィンドウ配置は Windows 標準の `Win + 矢印` を使用します。Hyper キーへの重複割り当てはありません。
