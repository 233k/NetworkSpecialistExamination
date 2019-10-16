# STP（Spanning Tree Protocol）
-  IEEE802.1Dで標準化
- ループ状に形成されたレイヤ2ネットワークにおいてデータトラフィックが永続的に流れ続けることを防止するプロトコル
- ブロードキャストフレームをループ状に接続されたスイッチ同士が送信しあい続けることを `ブロードキャストストーム` という
- STPを使用すると、あるポートが自動的にブロッキング状態になるが、障害発生時は自動的にそのポートが有効化される
- ブロックするポートの決定は `STA (Spanning Tree Algorithm)` で行われる
- これらの制御は `BPDU` によって行われる

## BPDU (Bridge Protocol Data Unit)
- STPが有効なスイッチでは、定期的にBPDUをマルチキャストアドレス（0180.C200.0000）で送信する
- BPDUフォーマットには、ブリッジIDとパスコストをもつ

### ブリッジID
- スイッチに割り当てられるID
- ブリッジIDはブリッジプライオリティとMACアドレスで構成
- 最も小さいブリッジIDのスイッチがルートブリッジに決定

### パスコスト
- ルートブリッジに至るまでの距離を示す情報
- パスコスト値はリンクの帯域幅から自動的に計算
- パスコストが同じだった場合は、ブリッジIDの小さい方を採用

## STP構築手順
1. ルートブリッジを決定
2. 最上流であるルートブリッジから下流スイッチに BPDU を流していく
3. 各スイッチが BPDU を受信したポートが UpLink、BPDU を送信するポートが DownLink と判断する
4. UpLink について Path Cost が最小の1ポート(Root Port)のみを開放し、他のポート(RSTP でのAlternate Port, 代替ポートのこと)をブロックする
5. DownLink のポート(Designated Port)については基本的にすべて開放するが、例外的に自分のスイッチ内でループする場合は片方をブロックする(RSTP でのBackup Port)

## ポート状態遷移
```
     +------------------------------------+
     |                                    |
     v                                    |
+----------+      +-----------+      +----------+     +------------+
| Blocking | ---> | Listening | ---> | Learning |---> | Forwarding |
+----------+      +-----------+      +----------+     +------------+
```

- Disable: ポートがshutdownされている状態。何も転送されない。
- Blocking: データフレームを転送せずに、BPDUの受信のみ行う状態。全てのポートの初期状態。
- Listening: BPDUを送受信し合い、ルートブリッジ、ルートポート、指定ポートの選出を行っている状態。
- Learning: BPDUを送受信し合う。非指定ポートになれば即座にブロッキング状態へ移行。
- Forwading: ポートが、最終的にルートポートまたは指定ポートになった状態。この状態のみユーザデータの転送可能

Learning と Forwading のみ 受信したフレームの送信元MACアドレスを学習している。

# Ref
- https://www.infraexpert.com/study/stpz1.html
- https://www.infraexpert.com/study/stpz2.html
- https://www.infraexpert.com/study/stpz3.html
- https://milestone-of-se.nesuke.com/nw-basic/stp/stp-summary/