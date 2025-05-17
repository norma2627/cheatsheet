# Wireshark
[Wiresharkダウンロード先](https://www.wireshark.org/download.html)<br>
- ネットワークモニタリングおよびプロトコル解析GUIソース
- オープンソース化されている
- フィルタリングをかけながら検索するとパケットが読みやすくなる

## 参考
- [Wireshark：フィルタチートシート](https://www.oresamalabo.net/entry/2024/11/12/181431)


## パケット送出
## hping3
- IPパケットクラフティグツール
- pingの拡張版みたいなもの
- 任意のIPパケットをターゲットに送出し、そのリプライの情報を表示する

### パケットの送付例
- TCPパケット連続送出
```
$hping3 -n [ipアドレス]
```
<br>

- 特定のポートに対して、SYNパケットをn回送出
```
$hping3 -n [ipアドレス] -c [数字] -S -p [ポート番号]
```
-c [数字]: 数字回パケットを送出<br>
-S: SYNフラグを立てる<br>
-p [ポート番号]<br>