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
- この中に
- サードパーティー製のライブラリがinstallされていて
- node_modulesを同じディレクトリに持っていることで
- import分を書いて実行できるようになる
- ここで補完することでチームで使用しやすくなる

## package-lock.json

## package.json
- ```{
  "dependencies": {
    "nodemon": "^3.1.10"
  }
}```
- dependenciesがサードパーティのライブラリ
- 数字はそのversion
- 依存関係を管理する表がある（表：{}の中身）
- 表を持つという事がjavascriptのデフォルト


# ライブラリやversionによって走る走らないがある
- node_modulesで管理することがjsの基本