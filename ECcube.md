# EC-CUBE 3 + Vagrant

## 事前準備

### 必要なソフトウェアのインストール

下記リポジトリのREADME.mdを参考に必要なソフトウェアをインストールする
[EC-CUBE/eccube-vagrant](https://github.com/EC-CUBE/eccube-vagrant)

* VirtualBox  
* Vagrant  
* Git  

Vagrantインストール後、下記コマンドを実行
```
vagrant plugin install vagrant-omnibus
vagrant plugin install vagrant-cachier
```

## EC-cube3のVagrant環境構築

作業ディレクトリは各自自由に作ってください
```
# EC-cube3本体をclone
git clone https://github.com/EC-CUBE/ec-cube.git

# vagrant設定用リポジトリをサブモジュールとしてclone
cd ec-cube
git submodule add https://github.com/EC-CUBE/eccube-vagrant.git ./vagrant

# vagrant起動
cd vagrant
vagrant up

# vagrantにsshログイン
vagrant ssh

# vagrant上でec-cubeのインストールを実行
cd /ec-cube
./eccube_install.sh pgsql
```

### 設定ファイルの修正

/ec-cube/app/config/eccube/path.yml の内容を修正する

```
#下記内容を修正する
root_urlpath: /ec-cube/html

↓

root_urlpath: /
```
```
#下記内容を修正する
# urlpath
admin_urlpath: /ec-cube/html/template/admin
front_urlpath: /ec-cube/html/template/default
image_save_urlpath: /ec-cube/html/upload/save_image
image_temp_urlpath: /ec-cube/html/upload/temp_image
user_data_urlpath: /ec-cube/html/user_data
plugin_urlpath: /ec-cube/html/plugin

↓

# urlpath
admin_urlpath: /template/admin
front_urlpath: /template/default
image_save_urlpath: /upload/save_image
image_temp_urlpath: /upload/temp_image
user_data_urlpath: /user_data
plugin_urlpath: /plugin
```

## 動作確認

* Front

[http://192.168.33.10/](http://192.168.33.10/)

frontのユーザーは[新規会員登録](http://192.168.33.10/entry)から作成

* Admin

[http://192.168.33.10/admin](http://192.168.33.10/admin)

ID: admin  
パス: password  

## 補足

#### ローカルとVagrantの共有ディレクトリ
ローカルのec-cubeディレクトリがvagrant上で共有ディレクトリとなっている  

ローカル : ec-cube  
vagrant上 : /ec-cube  

ので、ローカルで変更した内容は即時vagrant上の環境にも反映される

#### EC-CUBE3本体

[EC-CUBE3本体](https://github.com/EC-CUBE/ec-cube)

#### DB情報

DB名: cube3_dev
ユーザー: cube3_dev_user
パス:  password