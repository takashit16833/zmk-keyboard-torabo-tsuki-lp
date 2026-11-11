
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

### 診断用（RDP後半の操作）

このブランチのみ、キー操作間の待機位置と後半のキー送信方式を比較する。

| キー | 操作 |
| --- | --- |
| Hyper + C | 従来版（比較用、未変更） |
| Hyper + E | Ctrl・Alt・Home を順次送信し、Ctrl解放後に150ms待ち、Win+Ctrl+左矢印を一括送信 |
| Hyper + A | Hyper+Eと同じだが、後半はWinを押す→Ctrlを押す→左矢印を押して離す→Ctrl・Winを離す |
| Hyper + V | 従来版の右方向（変更なし） |

`wait-ms` は各操作の**後**に適用されるため、最後のCtrl解放イベントに150msの待機を付けている。
短押しで比較すること。左端のデスクトップでは切り替わらないので、右側のデスクトップから試す。
通常版の `master` は変更しない。
