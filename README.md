
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

### Windows（ウィンドウ配置）

Windows 用 Hyper レイヤーは、AutoHotkey を使わず標準ショートカットを直接送信します。
そのため、RDP 全画面内のウィンドウにも使えます。

| 操作 | 送信キー | 動作 |
| --- | --- | --- |
| Hyper + I | Win + ← | 左 1/2 |
| Hyper + - | Win + → | 右 1/2 |
| Hyper + A | Win + ↑ | 最大化 |
| Hyper + O | Win + ↓ | 復元／最小化（現在の状態による） |

最大化と復元は従来のトグルではなく、別々の操作です。
従来の 1/3・2/3 配置は廃止しました。通常の `Win + 矢印` もそのまま使えます。
