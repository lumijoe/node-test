# 起動
npm install
npm run dev

# node-test
公式ガイド：検索
https://www.npmjs.com/
nodemonインストールコマンドあり
```npm i nodemon```

# 種類について
標準モジュール（jsを作ってるとこの提供系）
サードパーティー（jsを作ってない部外提供系収益目的、ボランティア精神など）

# サードパーティー製
すぐimportを書いても使えるわけではなく(installが必要)


## 手順
- index.jsを作成
- ```npm i nodemon```
  - node_modulesが生成
  - package-lock.jsonが生成
  - package.jsonが生成
  - gitアイコン271の表示
  - added 30 packages in 1s の表示(node_modulesの中身が多い)

## node_modules
- git にはpushしないこと（データ量が多く、バージョン管理も必要ないため）
- この中に
- サードパーティー製のライブラリがinstallされていて
- node_modulesを同じディレクトリに持っていることで
- import分を書いて実行できるようになる
- ここで補完することでチームで使用しやすくなる

## package-lock.json
マイナーチェンジがあったとしてもpackage-lock.jsonで制御されていて
他の環境でnpminstallをしても3.2.10になることはない
- package.json → ^3.1.10（範囲を指定）
- package-lock.json → 3.1.11（実際にインストールされた正確なバージョン）
パッチはバグ修正の役割です。

  セマンティックバージョニング（例：3.1.10）では：
  - メジャー（3） → 破壊的変更
  - マイナー（1） → 新機能追加（後方互換性あり）
  - パッチ（10） → バグ修正

  パッチ更新の例：
  - セキュリティの脆弱性を修正
  - クラッシュやエラーを修正
  - 誤字脱字の修正
  - パフォーマンスの小さな改善

  重要：パッチは既存の機能を壊さない安全な更新です。

  仕組み：
  1. npm installを実行
  2. ^3.1.10の範囲内で最新版（例：3.1.11）をインストール(^キャレット)
  3. package-lock.jsonに3.1.11を固定して記録

  利点：
  - チーム全員が同じバージョンを使える
  - npm ciでpackage-lock.json通りの正確なバージョンをインストール
  - 「自分の環境では動くけど他の環境では動かない」を防げる

## package.json
- ```
    {
    "dependencies": {
        "nodemon": "^3.1.10"
    }
    }
  ```
- dependenciesがサードパーティのライブラリ
- 数字はそのversion
- 依存関係を管理する表がある（表：{}の中身）
- 表を持つという事がjavascriptのデフォルト

## ライブラリやversionによって走る走らないがある
- node_modulesで管理することがjsの基本

# npm init
- ```npm init```
- ターミナル表示
```It only covers the most common items, and tries to guess sensible defaults.

See `npm help init` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.


package name: (test) 
version: (1.0.0) 
description: 
entry point: (index.js) 
test command: 
git repository: https://github.com/lumijoe/node-test
keywords: 
author: lumijoe
license: (ISC) 
```
デフォルトのpackage name はtestですよという意味

- 最後に確認 Is this OK? (yes) 

  - package.jsonもっと中身が追記される

## nodemon server
ホットリロードが可能になる（保存する度に自動で内容を変更確認できる）
ターミナルで起動が確認できる

# npm i lodash
```npm i lodash```
- lodash のインストールができる
- package.jsonでdependenciesをチェック
  - loadashとバージョンが確認できてインストールされているのがわかる
- node_modulesでlodashがインストールされているのを確認できる

# .gitignore
- 依存関係
  node_modules/

- 環境変数
  .env
  .env.local
  .env.*.local

- ログ
  *.log
  npm-debug.log*

- OS生成ファイル
  .DS_Store
  Thumbs.db

- エディタ設定
  .vscode/
  .idea/
  *.swp
  *.swo

- ビルド成果物
  dist/
  build/
  *.tsbuildinfo

- テンポラリファイル
  *.tmp
  *.temp
  .cache/
