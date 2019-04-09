# todo-list-app
lesson of laravel<br>
https://docs.google.com/spreadsheets/d/1QV0mZnql-pB9Usi4vSCgj8gWWDxSMhmRaV2r995Gg0Y/edit?usp=sharing

## Laravel開発環境のインストール
### VagrantとVirtualBoxをインストール
以下URLよりVagrantとVirtualBoxをインストールしておきます。
すでに、インストールしているのであればバージョンだけ注意してください。

[Vagrant](https://www.vagrantup.com/)
[VirtualBox](https://www.virtualbox.org/wiki/Downloads/)

### Composerをインストール
インストールがまだの場合、下記の通りインストール

```
curl -sS https://getcomposer.org/installer | php
// /usr/local/bin/composerに移動させる
mv composer.phar /usr/local/bin/composer
// バージョン確認
composer --version
```

### HomeSteadのVagrant BoxをVagrantのリストに追加
HomeSteadのBoxを追加します。

```
vagrant box add laravel/homestead
```

以下コマンドで追加されているか確認します。

```
vagrant box list
```

### インストール
プロジェクト用のディレクトリを作って、composer でインストールします。

```
mkdir /Users/username/.../project
cd project
composer require laravel/homestead --dev
```

vagrant fileとHomestead.yamlを生成します。

```
php vendor/bin/homestead make
```

プロジェクト用ディレクトリにVagrantをインストールします。

```
vagrant up
```

### Vagrantにsshで入ってLaravelをインストール
```
vagrant ssh
cd /home/vagrant/code
laravel new
```
### hostファイルの編集
ホストファイルにHomestead.yamlのsites:のtoに書いてあるドメインを同じファイルに記されているipを当てます。
※ipやドメインはこのファイルから変更可能です。
Macのアプリ、hostsで編集するとお手軽です。
[[Mac]GUIでhosts編集できる「Hosts」が簡単操作で便利！ブログサーバー移転時の動作確認に使える！](https://delightmode.com/mac-hosts-prefpane/)
