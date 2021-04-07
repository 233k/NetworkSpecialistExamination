# SSL-VPN

SSL-VPNは、TLSプロトコルを利用したVPN技術である。
主に3つの動作方式が存在する。

|動作方式|専用モジュール|利用できるアプリケーションの制限|暗号化区間|
|:-:|:-:|:-:|:-:|
|リバースプロキシ|不要|ブラウザ上のみ|ブラウザ <---> VPN装置|
|ポートフォワーディング|必要|ポート番号が静的なもののみ|専用モジュール <---> VPN装置|
|L2フォワーディング|必要|制限なし|仮想NIC <---> VPN装置
|

# Ref

- https://www.infraexpert.com/study/security8.html
- https://qiita.com/yuyasat/items/81c32d7e235af97515c0
