
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

### Windows（ウィンドウ配置）

Windows 用 Hyper レイヤー（layer_15）から F19〜F22 を送信し、PC 側の `dotfiles-win/autohotkey/cycle-window.ahk` が読み込む `window-layout.ahk` で位置・サイズを変更する。キーボード単体では配置は行わない。

| 操作 | ZMK の送信 | Windows の動作 |
| --- | --- | --- |
| Hyper + I | F19 | 左側（幅2400以上なら1/3、未満なら1/2） |
| Hyper + O | F20 | 中央1/3 |
| Hyper + - | F21 | 右側（幅2400以上なら1/3、未満なら1/2） |
| Shift + Hyper + I | Shift + F19 | 左2/3 |
| Shift + Hyper + - | Shift + F21 | 右2/3 |
| Hyper + A | F22 | 最大化と元の位置への復帰 |
| Hyper + Tab | Ctrl + Win + Alt + Tab | 次のモニターに移動 |
| Shift + Hyper + Tab | Ctrl + Win + Alt + Shift + Tab | 前のモニターに移動 |

Hyper + C/V の RDP 仮想デスクトップ移動と、Hyper + 数字の Win+数字は変更していない。配置キーの動作確認には、Windows 側で `dotfiles-win/install.ps1` により AutoHotkey v2 を起動し、更新したZMKファームウェアを実機に書き込む必要がある。
