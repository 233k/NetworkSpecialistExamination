# IEEE802.1X
IEEE802.1Xとは、有線・無線LANにおけるユーザ認証の規格

## IEEE802.1Xの構成要素
|構成要素|説明|
|:-:|:-:|
|サプリカント <br> (supplicant)|IEEE802.1Xにおけるクライアントまたはクライアントにインストールするソフトウェア。最近のPCには標準搭載。|
|認証装置 <br> (Authenticator) | サプリカントと認証サーバの仲介役のネットワーク機器。 <br> 認証結果を受けてアクセス制御を行う主体。|
|認証サーバ <br> (Authentication Server)|ユーザ認証を行うサーバのこと。IEEE802.1X/EAPに対応したRadiusサーバを使用する。|

また、これら3つの構成要素以外に、クライアント認証の際に「証明書」を使用する場合、証明書を発行するためのCA（認証局）が必要。

```
+----------+     EAPOL Packet     +-------------+ Radius Packet +--------------+
|Supplicant|----------------------|Authenticator|---------------|Authentication|
|          |                      |             |               |     Server   |
+----------+ IEEE802.3/IEEE802.11 +-------------+               +--------------+
```

### EAP（PPP Extensible Authentication Protocol）
- 様々な認証方式をカプセル化する
- PPP, IEEE802.1X (EAP over LAN) など

#### サポート認証方式
- TLS
- PEAP

#### EAP パケット種別
- 要求 Request
- 応答 Response
- 成功 Success
- 失敗 Failure

### EAP 認証シーケンス
1. Supplicant は、通信を開始するためにプローブ信号を送信する。ここで、実行したい認証方式を要求
2. Authenticator から指定された認証方式で Request が送信される。

# Ref
- https://www.infraexpert.com/study/wireless51.html