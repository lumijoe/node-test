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