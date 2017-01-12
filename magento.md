# magento2 + vagrant

## 下記URLを参考にする
[https://github.com/paliarush/magento2-vagrant-for-developers](https://github.com/paliarush/magento2-vagrant-for-developers)

## インストール
```
# magento+vagrantのリポジトリをclone
git clone git@github.com:paliarush/magento2-vagrant-for-developers.git vagrant-magento
```

```
 # 設定ファイル修正
cd vagrant-magento/
cp etc/config.yaml.dist etc/config.yaml
vi etc/config.yaml

ce: "git@github.com:magento/magento2.git"
# ↓　
ce: "git@github.com:magento/magento2.git::2.1"
# magentoのバージョンを指定する
```

```
# vagrant起動+magento3インストール
bash init_project.sh
```

/etc/hosts にmagentoのhost名が追記されている
```
## vagrant-hostmanager-start id: ead0a4ef-159b-427a-b2b3-421e952be8c2
192.168.10.69   magento2.vagrant69
```

## 動作確認

* front  
[http://magento2.vagrant69/](http://magento2.vagrant69/)

* admin  
[http://magento2.vagrant69/admin/](http://magento2.vagrant69/admin/)  
ID: admin  
pass: 123123q  

## サンプルデータ投入

設定ファイルを修正  
vagrant-magento/etc/config.yaml
```
install_sample_data: 0
↓
install_sample_data: 1
```

ローカルマシンにて下記コマンドを実行
```
cd vagrant-magento
bash m-switch-to-ce -f
```
または、vagrant上でmagentoディレクトリ配下で以下のコマンドを実行
```
php bin/magento sampledata:deploy
php bin/magento setup:upgrade
```
