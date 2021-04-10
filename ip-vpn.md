# IP-VPN

- レイヤ3サービス
  - ネットワーク層プロトコルにIPを使用するため、それ以外のプロトコルを使用するためにはカプセル化が必要
- VPN通信
  - MPLSを用いてパケットを転送する

## MPLS (Multi-Protocol Label Switching)

**ラベル**と呼ばれる利用者を識別す固有のVPN情報が、IP-VPN網に入るときにパケットに付与され、出るときに除去される。IP-VPN網内では、このVPN情報に基づきルーティングされる。

 IP-VPN網と利用者ネットワークの境界で、利用者のネットワーク側ルータを CE (Customer Edge)、IP-VPN網側ルータをPE (Provider Edge) と呼ぶ。

 IP-VPN網に接続している全拠点は、仮想敵にフルメッシュ接続される。
