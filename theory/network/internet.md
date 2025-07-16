# ネットワークとインターネット

- [ネットワークとインターネット](#ネットワークとインターネット)
  - [ネットワークの分類](#ネットワークの分類)
    - [LAN](#lan)
      - [イーサネット（Ethernet）](#イーサネットethernet)
      - [無線LAN](#無線lan)
    - [WAN](#wan)
    - [インターネット](#インターネット)
    - [ネットワーク機器](#ネットワーク機器)
  - [プロトコル](#プロトコル)
    - [OSI参照モデルとTCP/IPモデル](#osi参照モデルとtcpipモデル)
    - [IPアドレス](#ipアドレス)
      - [IPv4](#ipv4)
      - [IPv6](#ipv6)
      - [ドメイン名とDNS](#ドメイン名とdns)
      - [ポート番号](#ポート番号)
      - [DHCP](#dhcp)
    - [TCPとUDP](#tcpとudp)
  - [インターネットアプリケーション](#インターネットアプリケーション)
    - [電子メール](#電子メール)
    - [ストリーミング](#ストリーミング)
    - [ファイル転送プロトコル](#ファイル転送プロトコル)
    - [TELNETとセキュアシェル](#telnetとセキュアシェル)
    - [ウェブ](#ウェブ)
      - [HTML](#html)
      - [XML](#xml)



## ネットワークの分類

- LAN（Local Area Network）
- MAN（Metropolitan Area Network）
- WAN（Wide Area Network）
- インターネット

### LAN

LAN（Local Area Network）

狭い範囲にあるコンピュータやネットワーク機器を接続するネットワーク
- 学校、工場、オフィス、家庭など

LANのトポロジー：バス型、スター型、リング型

スター型：ハブ

#### イーサネット（Ethernet）

トポロジー：バス型とスター型

OSI参照モデル：物理層、データリンク層

アクセス制御方式（access control method）：CSMA/CD（Carrier Sense Multiple Access with Collision Detection）

MAC（Media Access Control）アドレス：48ビットの識別番号

転送速度は当初10Mbpsだったが、100Mbps、1Gbps、10Gbpsと進化

#### 無線LAN 

IEEE 802.11は広く普及している無線LAN関連規格の一つである

Wi-Fiは無線LANの登録商標

アクセスポイント（access point）

Wi-Fiルータ

### WAN

WAN（Wide Area Network）

### インターネット

インターネット接続事業者（Internet Service Provider、ISP）

代表的なISP
- au one net
- J:COM
- OCN

インターネット（the Internet）

intra（内部） + net（ネットワーク）: 異なるネットワークを相互に接続するネットワーク

組織のネットワークやISPなどが相互に接続したネットワーク

アドレスの割付機関：ICANN（Internet Corporation for Assigned Names and Numbers）

プロトコルの制定機関：IETF（Internet Engineering Task Force）

### ネットワーク機器

- ハブ
- リピータ
- ブリッジ
- スイッチ
- ルータ
- ゲートウェイ

## プロトコル

### OSI参照モデルとTCP/IPモデル

OSI参照モデル
1. 物理層
2. データリンク層
3. ネットワーク層
4. トランスポート層
5. セッション層
6. プレゼンテーション層
7. アプリケーション層

インターネット・プロトコル・スイート（TCP/IPモデル）
1. リンク層
2. インターネット層
3. トランスポート層
4. アプリケーション層

TCP/IP
| 層                 | プロトコル                              |
| :----------------- | :-------------------------------------- |
| アプリケーション層 | HTTP, SMTP, POP3, FTP, Telnet, SSH, DNS |
| トランスポート層   | TCP, UDP                                |
| インターネット層   | IP, ICMP, ARP, RARP                     |
| リンク層           | Ethernet, Wi-Fi                         |

### IPアドレス

IP（Internet Protocol）

IPv4：32ビットのアドレス
IPv6：128ビットのアドレス

JPNIC（Japan Network Information Center）：日本国内のIPv4アドレス、IPv6アドレス、AS番号の登録管理業務

#### IPv4
ドット付き十進表記（dotted decimal notation）

アドレスクラス：A, B, C, D, E


#### IPv6
コロン付き16進記法（colon hexadecimal notation）

#### ドメイン名とDNS

ドメイン名（domain name）

DNS（Domain Name System）

URL（Uniform Resource Locator）

#### ポート番号

| ポート番号 | 用途          |
| :--------- | :------------ |
| 20         | FTPデータ転送 |
| 21         | FTP制御       |
| 22         | SSH           |
| 23         | Telnet        |
| 25         | SMTP          |
| 53         | DNS           |
| 67         | DHCP          |
| 80         | HTTP          |
| 110        | POP3          |
| 143        | IMAP          |
| 443        | HTTPS         |

#### DHCP

DHCP（Dynamic Host Configuration Protocol）：自動でIPアドレスを割り当てる

### TCPとUDP

TCP（Transmission Control Protocol）

UDP（User Datagram Protocol）

## インターネットアプリケーション

### 電子メール

SMTP（Simple Mail Transfer Protocol）

IMAP（Internet Message Access Protocol）

POP3（Post Office Protocol version 3）

### ストリーミング

ストリーミング（streaming）

### ファイル転送プロトコル

FTP（File Transfer Protocol）

### TELNETとセキュアシェル

TELNETはあまり利用されなくなっている

セキュアシェル（Secure Shell、SSH）

### ウェブ

HTTP（HyperText Transfer Protocol）

HTTPS（HTTP Secure）

#### HTML

HTML（HyperText Markup Language）

#### XML

XML（eXtensible Markup Language）

