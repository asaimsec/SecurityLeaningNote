## 何のツール？

総当たり攻撃によるパスワードをクラッキングするプログラム

公式リポジトリによると、Hydra は次のプロトコルをサポートしており、ブルート フォース攻撃を行う能力があります: “Asterisk、AFP、Cisco AAA、Cisco auth、Cisco enable、CVS、Firebird、FTP、HTTP -FORM-GET、HTTP -FORM-POST 、 HTTP -GET、HTTP -HEAD、HTTP -POST、HTTP - PROXY、HTTPS-FORM-GET、HTTPS-FORM-POST、HTTPS-GET、HTTPS-HEAD、HTTPS-POST、HTTP - Proxy、ICQ、IMAP、IRC、LDAP、MEMCACHED、MONGODB、MS- SQL、MYSQL、NCP、NNTP、Oracle Listener、Oracle SID、Oracle、PC-Anywhere、PCNFS、POP3 、 POSTGRES、Radmin、RDP、Rexec、Rlogin、Rsh、RTSP、SAP/R3、SIP、SMTP、SMTP Enum、SNMP 「v1+v2+v3、SOCKS5、SSH（v1 および v2）、SSHKEY、Subversion、TeamSpeak（TS2）、Telnet、VMware-Auth、VNC、および XMPP。

## 用語・前提

## 構成 / 仕組み

## 使い方（基本）
攻撃対象のサービスによってオプションが異なる

FTP
`hydra -l user -P passlist.txt ftp://10.66.161.241`

SSH
`hydra -l <username> -P <full path to pass> 10.66.161.241 -t 4 ssh`

Web Form
`sudo hydra <username> <wordlist> 10.66.161.241 http-post-form "<path>:<login_credentials>:<invalid_response>"`

## メモ
ただ実際は総当たり攻撃の対策はほぼ入っていると思われる。

以下が揃って初めてブルートフォースが“成立”する
- レート制限が無い
- CAPTCHAが無い
- ロックアウトが無い
- レスポンスが成功/失敗で明確に分かれる