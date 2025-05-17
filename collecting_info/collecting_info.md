# 情報取集

## Whois
- IPアドレスやドメインに関する情報を収集

収集方法
- [JPRS](https://whois.jprs.jp/)からの収集
- Whoisコマンドを使用する方法もある

### 疑問
Q. Whois情報がなんで公開されているか
A. whoisの[歴史](https://jprs.jp/about/dom-search/whois/)に記載

## Dig
- DNSサーバからの情報を取集する
- DNSサーバを支えている技術に[BIND](https://www.isc.org/bind/)がある(現行のバージョンはBIND9)

### Digの使い方
Digコマンド形式
'''
$ dig [オプション] @[DNSサーバのIPアドレス]　[対象ドメイン名]　[クエリタイプ]
'''

クエリタイプ
- A: ホストのIPアドレス
- NS: 対象のネームサーバの情報
- MX: 対象のメールサーバの情報
- SOA: 多少のゾーンの設定情報
- ANY: 対象の全ての情報

出力の読み方
[DNSのチュートリアル](https://www.janog.gr.jp/meeting/janog35/download_file/view/83/175/index.pdf)(JANOG35 Meetingより)が参考になりそう


## Webでの調査
Googleを使用した調査
- [The Google Hacker's Guide](http://pdf.textfiles.com/security/googlehackers.pdf)
- [Google Hacing for Penetration Testers](https://www.blackhat.com/presentations/bh-europe-05/BH_EU_05-Long.pdf)

過去のページを参照したいとき
- [WayBackMachine](https://archive.org/)(Internet Archiveより)
