# Expressインストール

## Vagrantfile
VirtualBox + Vagrantで環境構築  
OS: Ubuntu22.04

Node.jsのインストール参考サイト  
https://github.com/nodesource/distributions

```ruby
 -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-22.04"
  config.vm.network "private_network", ip: "192.168.33.15"
  config.vm.synced_folder ".", "/vagrant/"

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update

    # install Node 20x
    sudo apt-get install -y ca-certificates curl gnupg
    sudo mkdir -p /etc/apt/keyrings
    curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg
    NODE_MAJOR=20
    echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_$NODE_MAJOR.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list
    sudo apt-get update
    sudo apt-get install nodejs -y
  SHELL
end
```

## vagrant立ち上げ&ssh接続

```sh
vagrant up
vagrant ssh
```

## .gitignore修正
GitHub用に追記

```
.vagrant
```

## Node.jsとnpmのバージョン確認

```sh
node --version
npm --version
```

## Express.jsインストール
https://expressjs.com/ja/starter/installing.html

```sh
mkdir myapp
cd myapp
npm init
npm install express
```

## Hello World!
下記のapp.jsを作成

```js
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})
```

実行コマンド

```
node app.js
```

http://192.168.33.15:3000/
