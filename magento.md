# magento3 + vagrant

## 下記URLを参考にする
[https://github.com/paliarush/magento2-vagrant-for-developers](https://github.com/paliarush/magento2-vagrant-for-developers)

## インストール
```
# magento+vagrantのリポジトリをclone
git clone git@github.com:paliarush/magento2-vagrant-for-developers.git vagrant-magento

# vagrant起動+magento3インストール
cd vagrant-magento/
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
