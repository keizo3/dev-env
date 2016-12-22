# wordpress + vagrant

## 下記URLを参考にする
[http://vccw.cc/](http://vccw.cc/)

## 準備

* vagrantをインストール
* virtualboxをインストール

vagrantとvirtualboxのバージョンに注意。

必要なvagrant pluginとboxをインストールする  
```
vagrant plugin install vagrant-hostsupdater
vagrant box add vccw-team/xenial64
```

プログラムを[ダウンロード](https://github.com/vccw-team/vccw/archive/3.0.5.zip)してきて、解凍。  
```
# 解凍されたディレクトリに移動
cd vccw-3.0.5

# vagrant起動
vagrant up

# 途中パスワードを聞かれた場合はローカルマシンのパスワードを入力
```

##　動作確認

* front  
[http://vccw.dev/](http://vccw.dev/)

* admin  
[http://vccw.dev/wp-login.php](http://vccw.dev/wp-login.php)  
Username: admin  
Password: admin  


## 参考

[http://qiita.com/naru0504/items/58011181f2c271808c7f](http://qiita.com/naru0504/items/58011181f2c271808c7f)  
