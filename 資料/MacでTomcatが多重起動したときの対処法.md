### MacでTomcatが多重起動したときの対処法

Mac上のEclipseでTomcatが多重起動してしまうと、以下のウィンドウが表示されWebページが表示されなくなります。そうなった場合の対処法です。  
![Error](https://i.gyazo.com/acafaaf78ff9774f9852c302e84b6961.png)


#### ターミナルを開きます。
ターミナルは、Launchpadの「その他」の中にあります。   
※ Launchpadはトラックパッドで指4本を縮こめると出てきます。   
![Launchpad](https://i.gyazo.com/d31d65e37594f076612144c87bc220cc.png)

#### Tomcatのpidを調べます。
ターミナルで以下のコマンドを実行します。   
```
lsof -i:8080
```
以下の画像の赤枠がpidです。（状況によって異なります。）   
![pid](https://i.gyazo.com/fddd1c1b313aa92a10138251b463195e.png)

#### Tomcatをタスクキルします。
ターミナルで以下のコマンドを実行します。   
```
kill -9 <pid>
```

調べたpidを使ってタスクキルします。   
pidが`1234`だった場合は、`kill -9 1234`となります。
