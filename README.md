
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

各キーは `Ctrl + Alt + Home` の後に `Win + Ctrl + ←/→` を送信します（間隔 150ms）。
RDP の全画面表示中でもローカル側に切り替えられる想定です。実機での連続送信の動作は未確認です。

ウィンドウ配置は Windows 標準の `Win + 矢印` を使用します。Hyper キーへの重複割り当てはありません。

### 診断用：RDPの Ctrl + Alt + Home 比較

この節は `diagnostic/rdp-home-only-20261112` ブランチでの検証専用。通常の `master` には含めない。

| キー | 診断内容 |
| --- | --- |
| Hyper + A | `&kp LC(LA(HOME))`：マクロを使わず3キーをまとめて送信 |
| Hyper + E | Ctrlを押す → Altを押す → Homeを40ms押す → Alt・Ctrlを離す |
| Hyper + C | 従来の300ms保持マクロ（比較用） |
| Hyper + I | Ctrl + Home |
| Hyper + O | Alt + Home |
| Hyper + - | Ctrl + Alt |
| Hyper + V | 元のRDP仮想デスクトップ切り替えマクロ |

`Hyper + E` のみ、キー操作の間隔として `wait-ms = <40>` を使う。RDP全画面で各キーを**短く押し**、接続バーにフォーカスが移るか、続けてTabキーで確認する。
