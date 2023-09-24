# Express のアプリケーション生成プログラム

アプリケーション生成プログラム・ツールの express を使用すると、アプリケーション・スケルトンを素早く作成できます。
次のコマンドを使用して、express をインストールします。

```sh
sudo npm install express-generator -g
```

Express のアプリケーション生成プログラムの実行コマンド

```sh
express --view=pug myapp

    create : myapp/
    create : myapp/public/
    create : myapp/public/javascripts/
    create : myapp/public/images/
    create : myapp/public/stylesheets/
    create : myapp/public/stylesheets/style.css
    create : myapp/routes/
    create : myapp/routes/index.js
    create : myapp/routes/users.js
    create : myapp/views/
    create : myapp/views/error.pug
    create : myapp/views/index.pug
    create : myapp/views/layout.pug
    create : myapp/app.js
    create : myapp/package.json
    create : myapp/bin/
    create : myapp/bin/www

    change directory:
        $ cd myapp

    install dependencies:
        $ npm install

    run the app:
        $ DEBUG=myapp:* npm start
```
