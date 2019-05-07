NEC MultiWriter 5750c ドライバー
============

インストール手順
---

まず pacman でいろいろいれる
```
sudo pacman -S cups ghostscript gsfonts lib32-libcups a2ps
```

cups サービス有効化＆起動

```
sudo systemctl enable --now org.cups.cupsd.service
```

http://localhost:631 にアクセス
rootユーザでログイン

管理->プリンターの追加->インターネット印刷プロトコル(http)->
http://192.168.0.253:631/ipp/
を指定

プリンタ名などの任意の名前(と説明と場所)を設定
PPDファイルを参照ボタンから設定後、プリンターの追加ボタン押下
※/usr/share/ppd/NECにある

管理->プリンターの管理->キュー名をクリック
メンテナンス選択状態で許可するユーザーの設定
root, 自分のユーザ名
に対してこれらのユーザを許可に設定しておく
```
