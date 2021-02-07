# VLAN (Virtual Local Area Network)

- VLANはL2スイッチ内部で論理的にLANセグメントを分割するために使用
- VLANごとにVLAN ID(12bit: 最大 2^12= 4096 個)が割り当てられる

## トランクポート

- 複数のVLANのトラフィックを転送可能なポート
- 複数のVLAN IDが割り当てられたポート
- 逆に、1つだけのVLAN IDが割り当てられたポートは `アクセスポート` と呼ばれる

## IEEE802.1Q

- トランクポートにてVLANを識別する識別情報を付加するためのプロトコル
- 送信されてきたイーサネットフレームに以下を追加し、FCSを再計算
  - TPID: 0x8100 固定値
  - TCI : VLAN ID
- タギングVLANとも

# Ref

- https://www.infraexpert.com/study/vlanz1.html
- http://www.n-study.com/network/newvlan4.htm