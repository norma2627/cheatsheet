# パケットフィルタリング
- IPパケットの内容によりネットワーク通信の許可/拒否を行う
- ファイアウォール実装方法の一種

## フィルタリング
フィルタリングを行う際の基準
- IPヘッダ: 送信元IP,宛先IP,プロトコル
- TCPヘッダ: 送信元ポート番号，宛先ポート番号 ,コントロールビット(SYN等のフラグ)
- UDPヘッダ: 送信元ポート番号, 宛先ポート番号
- ICMPメッセージ: TYPE, CODE

## パケットフィルタリングの種類
ステートレス・パケットフィルタリング（静的フィルタリング）
  - 個々のIPパケットをそれぞ単独でルールと比較し、通過させるかどうかを判断
  - ルータやスイッチのフィルタリング機能に多い

ステートレス・パケットフィルタリング(動的フィルタリング)
  - 通信の接続に関する状態（ステート）を考慮しながら通過パケットを決定
  - 通常のファイアウォール製品はこのタイプ


## iptablesを使用したパケットフィルタ
 ```
iptabes -P FOWARD DROP
-> デフォルトですべてのパケットを拒否
 ```
iptablesコマンドを使用することでパケットのフィルタリングを行うことができる

