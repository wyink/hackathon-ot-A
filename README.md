# Pokemon Quiz

株式会社ラクス様のインターン（11/5-11/26）で作成したリアルタイムクイズアプリ</br>
- 興味のある機能を順次追加予定

## 概要
ログインしているユーザー間でポケモンに関するクイズを答え、その解答数を競うことができるアプリケーションです。
もちろん一人でもプレイすることができます。</br>

## アプリの起動

1. 次のコマンドを実行します

    ```bash
    # アプリのディレクトリに移動
    cd ~/chatapp
    # アプリの開発で使用するライブラリをインストール（初回のみ）
    npm install
    # 起動コマンドを実行
    npm start
    ```

2. `http://サーバのIPアドレス:ポート番号/` にブラウザでアクセスします

    例：`http://127.0.0.1:3000/`

## 機能

#### ログイン画面

- ログイン画面からユーザ名を入力して「入室する」ボタンでクイズ画面に遷移します
    - ユーザ名は重複して登録できません（すでに使用済みの場合は警告）
    - 空白はユーザー名として使用できません

#### クイズ画面
- 入室したタイミングで問題が出題されます
  - すでにほかのユーザーが入室していた場合は同じ問題が出題されます（ただし、ポケモンの画像のみ）
  - すでにログインしているユーザーはそのログインをメッセージで知ることができます
- ログインユーザーは解答フォームにポケモン名を入力します。
 - ヒントのボタンは2つあり、それぞれ何タイプのポケモンであるかという情報と頭文字を知ることができます
 - ただし、他のログインユーザーとの競争なので他のユーザーの解答の方が早かった場合は次の問題に移ります
 - 解答はひらがな、カタカナの両方を許容し、また、改行や末尾の空白は省いて解答の判定が行われます
- 自身が解答できた場合、もしくは他のユーザーが回答した場合は次の問題に自動で移ります
- 自身の解答数およびヒントの使用回数はテーブルに表示されます

- ユーザの入退室時に自分を除いた他のクライアントに入退室のメッセージが表示されます
    - このとき、右上に表示されるテーブルから退出したユーザーのIDとそれに紐づくデータが他のユーザーのページから消えます
    - 退出後は最初のログインページに戻ります

