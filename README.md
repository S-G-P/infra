# infra 

RailsアプリケーションをEC2インスタンス上にデプロイするための

Vagrantfile, AnsibleのPlaybookなどを管理するためのリポジトリです。

# 構成
以下の環境をワンコマンドで構築できるレベルを目指して作成する。

- host
  - ansible (nginxの設定ファイル, mysqlの設定ファイル, etc...)
    
- web 
  - nginx
  - ruby
  - git 
  - rails, unicorn  (unicorn は gem に書くのでアプリケーションサイドで管理する。（ansibleには書かない）)

- db
  - mysql

# 参考
[Ansible入門 ① vagrantでhost, web, dbの環境を作ってsshで接続するまで](http://qiita.com/G-awa/items/93689f1814a192b5077e)

[Ansible入門 ② webとdbの環境に対して、Ansibleコマンドを実行してみる](http://qiita.com/G-awa/items/84c50bf29bb2a358b02c)

[Ansible入門 ③ Ansibleのplaybookを書いてwebサーバにnginxを入れるところまで](http://qiita.com/G-awa/items/2cea5db8b4309f94cff4)


