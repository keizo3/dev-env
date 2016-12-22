# baserCMS + vagrant

## 下記URLを参考にする
[http://basercms.net/develop/archives/81](http://basercms.net/develop/archives/81)

## インストール

```
# ディレクトリ作成
mkdir baserCMS
cd baserCMS

# boxファイル取得
vagrant box add baserbox http://basercms.s3-website-ap-northeast-1.amazonaws.com/vagrant_boxes/CentOS-6.4-x86_64-basercms3-beta-v20131011.box

# vagrant初期化
vagrant init baserbox

# vagrant起動
vagrant up
```

## 動作確認

* front  
[http://192.168.33.10/basercms3/](http://192.168.33.10/basercms3/)

* admin  
[http://192.168.33.10/basercms3/index.php/admin](http://192.168.33.8/basercms3/index.php/admin)  
USER: root  
PASS: vagrant  

baserCMSは、/var/www/html/basercms3/ に設置しており、SSHでフォルダに入って、git pull すると最新の開発版が落とせます。
```
git pull origin dev-3
```