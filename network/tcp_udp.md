# TCP/IP

## IP
- IPヘッダの構造: [RFC791](https://datatracker.ietf.org/doc/html/rfc791)で規定されている

![IPパケットのヘッダ構造](https://milestone-of-se.nesuke.com/wp-content/uploads/2016/12/ip-format.png)

## TCPとUDP
TCP<br>
- フロー制御や再送処理機能を持つため通信の信頼性が高い
- オーバーヘッドがあるため速度は遅い

UDP<br>
- 単純な通信プロトコルえ速度は速い
- 通信性は低い

### TCP/UDPのサービス
TCP<br>
| ポート番号 | サービス |
| ---- | ---- |
| 22 | SSH |
| 23 | Telnet |
| 25 | SMTP |
| 80 | HTTP |
| 139 | NetBIOSセッションサービス |
| 443 | HTTPS |
| 445 | SMB |

UDP<br>
| ポート番号 | サービス |
| ---- | ---- |
| 53 | DNS名前解決サービス |
| 137 | NetBIOSデータグラムサービス |
| 161 | SNMP |


### TCPの3ウェイハンドシェイク
```
1. 送信元    SYN->    送信先
2. 送信元  <-SYN/ACK  送信先
3. 送信元    ACK->    送信先
->TCPコネクションができる
```

### TCPポートの振る舞い
- オープンポートに対してSYNパケットを送った場合
```
元  -> SYN      先(TCP80)
元  <- SYN/ACK  先(TCP80)
```
<br>

- クローズドポートに対してSYNパケットを送った場合
```
元  -> SYN      先(TCP81)
元  <- RST/ACK  先(TCP81)
```
<br>

- オープンまたはクローズドポートに対してACKパケットを送った場合
```
元  -> SYN  先(TCP81)
元  <- RST  先(TCP81)
```
<br>

### UDPの振る舞い
- オープンポートに対して適当なUDPパケットを送った場合
```
送信元    -> UDPパケット       送信先
送信元    <- 応答なし(エラー)  送信先
```
<br>

- クローズドポートに対して適当なUDPパケットを送った場合
```
送信元    -> UDPパケット       送信先
送信元    <- ICMP  送信先
```
<br>

## ICMP
- Internet Contorol Message Protocol
- IPの中に実装される通信エラーやプロトコル制御のためのメッセージプロトコル
<br>

| ICMPのタイプ | 意味 |
| ---- | ---- |
| タイプ0 | エコーリプライメッセージ(pingの応答パケット) |
| タイプ3 | 到達不能メッセージ |
| タイプ8 | エコーメッセージ(pingコマンドで発信されるパケット) |
| タイプ11 | 時間超過メッセージ |
<br>

### 参考
[3分間NetWorking](https://www5e.biglobe.ne.jp/aji/3min/)<br>