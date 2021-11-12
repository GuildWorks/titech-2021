---
marp: true
theme: gaia
size: 16:9
header: '　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　Copyright Naotake KYOGOKU'

page_number: true
paginate: true
---

**Programming Boot Camp**

# Bubble の基本

**東京工業大学 2021/11/13**
　
　
　
　
　
　　　　　　　　　　　　　　　　　　　**Naotake KYOGOKU**

---

## 目次
  - Bubble とは
  - Bubble に登録しよう
  - Bubble でのアプリ開発の概要説明
  - まずはペット登録から一覧表示まで作ってみよう
  - ペット詳細画面を作ってみよう
  - ペットの体重を管理しよう
  - まとめ

---

## Bubble とは
- [Bubble](https://bubble.io/) はビジュアルプログラミングツールと呼ばれ、ノーコードツールではありますが、プログラミング的な発想が必要なツールとなります。
- 用意されているパーツから使用したいものを選び、それを画面にドラッグ＆ドロップしていくなどの操作は Adalo と同じです。
- ただ、配置したパーツに対して動きをつけていく部分については、プログラミング的な発想が必要となります。
- また、Adalo と違い、Web アプリケーション前提での開発を行い、それをスマホ表示に対応させていく形となります。

---

#### Adaloで作られたアプリの例
- LIBRIS（リブリス）: https://libris.ne.jp/
  - 2021年3月リリース
  - 行きたい本屋が見つかる検索サイト
  - 個人経営のお店やブックカフェやライブラリなど、全国の本屋を検索できる
  - 開発者は、本好きの非エンジニアの方だそうです

- その他
  - https://nocode-freaks.com/?p=200
  - ゲームもありました（笑）

---

## Bubble に登録しよう
- Bubble の TOP 画面からメールアドレスを入力してアカウント登録
  - https://bubble.io/
  - Get started クリック

![w:900px](images/2021-11-11-22-50-00.png)

---
- アカウントは無料で登録できます
- ご自身のメールアドレスとパスワードを入力して "Get started" クリック

![bg right h:600px](images/2021-11-11-22-52-48.png)

---

- 利用規約への同意して "I agree..." クリック

![](images/2021-11-11-22-55-02.png)

---

- 利用に向けていくつかアンケートに回答
- 最後に "Sbumit(thanks!)" クリック

![bg right h:500px](images/2021-11-11-22-56-16.png)

---

- するとエディタ画面が表示され、チュートリアルが始まりますが、これは後からでも実施できるので閉じます
- 画面右上のアイコンをクリックし "My applications" 選択

![w:900px](images/2021-11-11-22-57-49.png)

---

- Welcome ページが表示されるので、画面下までスクロールして "Create a new app" クリック

![w:900px](images/2021-11-11-22-58-52.png)

---

- このような画面が表示されたら OK です
- これは Bubble が自動生成したテンプレートが初期状態として表示されています
- 左パネルの New Application Assistant が表示された方は、下の "Close the assistant" を選択
![w:900px](images/2021-10-31-20-42-10.png)

---

### まずは Bubble のテンプレートを動かしてみよう

- 画面右上の Preview ボタンをクリックしてください

![](images/2021-10-31-20-50-28.png)

---

- プレビュー画面が起動します

![w:850px](images/2021-10-31-20-52-42.png)

---

### Sign up してみよう

- 画面右上の "SIGN UP OR LOGIN" をクリック
- モーダルが表示されるので Email / Password / Confirm password を入力して "SIGN UP" クリック
  - 入力した Email と Password はメモしておいてください(後で使います)
![bg right h:600px](images/2021-10-31-20-54-19.png)

---

- すると画面右上のボタンが "LOG OUT" になったと思います
- つまりアカウント登録が行われ、ログイン状態になったということです
![bg right h:500px](images/2021-10-31-20-56-39.png)

---

### Login してみよう

- 画面右上の "LOG OUT" をクリックして一度ログアウトします
- 再度右上の "SIGN UP OR LOGIN" をクリック
- モーダルの下にある "OR LOGIN" をクリック

![bg right h:500px](images/2021-10-31-20-59-38.png)

---

- ログイン用のモーダルが表示されるので、そこで先程入力したメールアドレスとパスワードを入力
- 最後に "LOG IN" をクリック
- 成功すると画面右上のボタンが "LOG OUT" になったと思います
- これでサインアップとサインインが動いていることが確認できます
![bg right h:500px](images/2021-10-31-20-59-38.png)

---

#### スマホ対応について

- 冒頭でお伝えした通り、Bubble のアプリは Web アプリケーションの前提となっています
- Bubble のアプリをスマホ対応させる場合、 **レスポンシブデザイン** という考え方を取り入れます

--- 

- まずは動きを見てみましょう
- ブラウザの横幅を縮めてみてください

![bg right h:500px](images/2021-10-31-21-06-15.png)

---

- レイアウトが崩れることはなく、自動的に要素の配置が変わり、スマホサイズに適した配置になったと思います
- これがレスポンシブデザインというものです
- Google ではこのように説明されています

```
ユーザーのデバイスの種類（パソコン、タブレット、モバイル、非視覚的ブラウザ）に関係なく、
同じ URL で同じ HTML コードを配信しつつ、画面サイズに応じてレンダリング方法を変更します。
```

---

- ポイントとしては下記の点ですね
1. 表示しているページの URL は同じ
2. 画面サイズに応じてレンダリング方法を自動的に変える

---

- もう少し噛み砕いて言うと、画面サイズに応じて、要素が伸びる／縮む、折り返す／折り返さない、表示する／表示しないを制御する
- これを各項目レベルで設定してあげることで、自動でレスポンシブデザインに対応させることができます
  - 実際の開発時には、設定してプレビューして動作確認していくと良いと思います

- 後ほど画面操作の中でレスポンシブを実際に設定していきます（まずは概要まで）

---

## Bubble でのアプリ開発の概要説明

次に、Bubble でのアプリ開発の概要を説明していきます

---

### 3 つのメイン操作

- Bubble では主に 3 つの操作を使い分けていきます
  1. Design
  2. Workflow
  3. Data
- 左パネルからそれぞれを行き来することができます

![bg right h:400px](images/2021-10-31-21-28-32.png)

--- 

#### Design

- ユーザーインターフェースを作るために画面上にコンポーネントを配置するモード
- 左パネルに UI のコンポーネント類、右パネルに実際の画面編集領域

---

![w:1150px](images/2021-10-31-21-34-08.png)

---

#### Workflow

- 画面に動きをつけるためのモード
  - 例）ボタンが押された時に、画面遷移する
- ここが、少しプログラミングの考え方を必要とする部分となります

![w:1150](images/2021-10-31-21-38-05.png)

---

#### Data

- データを定義したり操作したりするモード

![w:1100px](images/2021-10-31-21-40-26.png)

---

- "App data" タブを選び、右側から "All Users" のリンクをクリック
- すると、右パネルに登録済みのユーザ一覧のデータが表示され、そこに先程 "Sign up" したユーザが存在するはずです
- これで画面とデータベースが連携していることを確認できましたね

![w:900px](images/2021-11-11-23-19-02.png)

---

#### その他の操作について

- Styles
  - スタイルに名前をつけてあげることで、汎用的に使える
  - 部品ごとに個別に指定することもできる
  - 今回は基本的にありもののスタイルを使っていきますので、今回の講義では扱いません

![w:1000px](images/2021-11-11-23-22-42.png)

---

- Plugins
  - Adalo で折れ線グラフのコンポーネントを追加したように、Bubble にもアプリケーションを拡張するための様々なコンポーネントが公開されています
  - Bubble ではこれをプラグインと呼びます
  - Bubble のプラグインには無料 / 有料のものがあるので、お使いになる際には確認しましょう

---

- Settings
  - Bubble のプランの変更やアカウントに関する操作
  - Bubble が提供しているメッセージを一元管理できます
    - アプリケーションを使うメインユーザ向けにロケール（言語設定）を変更可能
    - このメッセージを変更することで、システム全体でメッセージ管理を統一できます
    - アプリ全体で共通に使えるメッセージ類を変えられるし、デフォルトのメッセージを変えることも可能
    - アプリ固有のメッセージを追加することも可能
  - 今回の講義では扱いません

---

- Logs
  - アプリケーションを動かしたときのログを見ることができます
  - ただ、アプリケーションをプレビュー表示しながらログを見ることもできるので、今回の講義では扱いません

---

#### これから作っていく画面の全体像

![w:850px](images/2021-11-12-10-21-56.png)

---

## まずはペット登録から一覧表示まで作ってみよう

- Adalo での会で作成した画面要素やデータ構造と同じものを作っていきます
- そのため、Bubble の会では画面とデータベース操作を一緒に作っていきます
- また、認証に関する部分は Bubble で用意されたデフォルトのものを流用します
- まずはペットの登録画面を作成し、そのペットを一覧に表示するところまで作ってみましょう！

---

#### ペットの一覧画面の枠だけ用意する

- まず最初に動作確認に使ったページをペットの一覧ページとして使い回します
- そのため、Bubble が自動生成したパーツを一度すべて削除します
- index ページの何か一つの要素を選択したら "Ctrl + A" で全要素を選択します
- そして Delete ボタンをクリックすると画面がまっさらになると思います

---

##### 要素削除前

![w:700px](images/2021-11-07-10-34-57.png)

---

##### 要素削除後

![w:700px](images/2021-11-07-10-35-53.png)

---

- Bubble のテンプレートに用意されていたヘッダーを使い回します
- Design タブを選択し、"UI Builder" の部分を下にスクロールすると `Reusable elements` という項目の中に Header というのがあると思いますので、そちらをクリックします

![bg right h:600px](images/2021-11-11-23-32-01.png)

---

- そして、右側の描画エリアの上の方で範囲選択（ドラッグ）すると、その部分に共通の Header 要素が追加されます

![w:1100px](images/2021-11-11-23-35-16.png)

---

- 場所がちょうど一番上に配置できない場合は Header 選択しドラッグで画面中央上部に配置します
  - 要素を選んで右クリックし `Center horizontally` を選択すると、要素の横位置を中央に移動します
  - `Center vertically` を選択すると、要素の縦位置を中央に移動します
  - 今後要素を中央に寄せたい時などはお使いください
- ヘッダーの中身は後で変更していきます

---

#### ペット登録画面を作成していきます

- 画面右上の `Search a page or ~` 部分をクリックするとポップアップが表示されます
- ポップアップの中から `Add a new page...` をクリック

![w:900px](images/2021-11-07-10-53-14.png)

---

##### ちなみに...

- ここには現在作成中のアプリケーションの中にある「ページ」や「共通コンポーネント」の一覧が表示されています
- Adalo では 1 つのキャンバスにすべての画面が表示されていましたが、Bubble では 1 つのキャンバスで 1 つの画面を操作していく操作になります
- そのため、画面間の移動はここから変更する必要があるので覚えておきましょう :raising_hand:

---

- `Add a new page...` をクリックすると新しい画面のポップアップが表示されます
- `Page name` は画面の名前となるので、空白などを含めずに英数字だけで入力します
  - 今回は `pet_register` としましょう

![bg right h:350px](images/2021-11-07-10-57-54.png)

---

- `Clone from` は似たような画面を作りたい時に、コピー元となる画面を選択してその画面のコピーを作ることができます

![bg right h:350px](images/2021-11-07-10-57-54.png)

---

- 例えば登録画面と編集画面などは画面要素がほとんど同じになるので、登録画面を作った後に編集画面を作る時に "Clone from" に登録画面を選択すると、開発工数の削減につながります

![bg right h:350px](images/2021-11-07-10-57-54.png)

---

- 今回は折角なので先ほどヘッダーだけを用意した index を選択してコピーしましょう
- 必要な情報を入力したら "CREATE" ボタンをクリック

![bg right h:350px](images/2021-11-07-10-57-54.png)

---

#### ペット登録画面を組み立てる

- Adalo で作成したペット登録画面のイメージを参考に画面を作ってみましょう
![bg right h:700px](images/2021-11-07-11-02-10.png)

---

#### ペットの名前

- まずはペットの名前を入力するテキストボックスを配置します
- 左パネルの "UI Builder" から `Input forms` の中にある `Input` を選択
- そして右パネル上で配置したい場所でドラッグをすると入力欄を表示されます

![bg right h:600px](images/2021-11-11-23-41-41.png)

---

- 要素をダブルクリックすると要素の様々な情報を設定できるダイアログが表示されますので、必要な項目を設定していきます
- `Placeholder` はテキストボックスが未入力状態の時に表示される補助文言です
  - 今回は「pet name」とします

![bg right h:550px](images/2021-11-07-11-13-05.png)

---

- `Content format` はテキストボックスに入力できる値の形式を指定できます
  - 今回は文字列の入力となるので "Text" のままとします

![bg right h:550px](images/2021-11-07-11-13-05.png)

---

- `This input should not be empty` は入力必須にするかどうかを指定できます
  - 今回は必須としたいのでチェックをつけます

![bg right h:550px](images/2021-11-07-11-13-05.png)

---

- まずはここまで設定したら OK です
  - ほかにも細かく指定ができますが、ここでは説明を省略します
  - 気になる方は見てみてください :mag:

---

- もう一つだけ設定する項目があります
- ダイアログ先頭の部分をクリックすると、このテキストボックスの要素に対して名前を付けることができます
- これは後々ワークフローを定義するときに便利になるのでここでは `Input pet name` と指定しましょう

![bg right h:350px](images/2021-11-08-22-36-23.png)

---

#### ペットの画像

- 次にペットの画像をアップロードする要素を配置します
- 左パネルから `Picture Uploader` を選択し、右パネル上でドラッグして要素を配置します

![bg right h:700px](images/2021-11-11-23-46-49.png)

---

- この要素も同じくダブルクリックから要素の情報を設定します
  - 今回は `Placeholder` に「Click to upload pet image」と入力します
  - 要素の名前として `Input pet image` を指定します

![w:800px](images/2021-11-11-23-48-59.png)

---

#### ペットの誕生日

- 次にペットの誕生日を入力するための要素を配置します
- 左パネルから `Date/Time Picker` を選択し、右パネル上でドラッグして要素を配置します

![bg right h:700px](images/2021-11-11-23-50-06.png)

---

- こちらも要素をダブルクリックして要素の詳細を設定します
  - `Input type` に Date を選択することで日付入力のみとなります
    - ここで Date & Time を選択することで日付と時刻の入力が可能です
    - 今回は Date とします

![bg right h:700px](images/2021-11-11-23-51-15.png)

---

- `This input should not be empty` はチェックをつけて必須にします
- 要素の名前として `Input pet birthday` を指定します

![bg right h:700px](images/2021-11-11-23-51-15.png)

---

#### ペットの性別

- 最後にペットの性別を選択するための要素を配置します
- 左パネルから `Dropdown` を選択し、右パネル上でドラッグして要素を配置します

![bg right h:700px](images/2021-11-11-23-52-41.png)

---

- こちらも要素をダブルクリックして要素の詳細を設定します
  - `Placeholder` に「pet gender」と入力します
  - `Choices` に "Male" と入力したら Enter キーで改行し、次の行に "Female" と入力します

![bg right h:700px](images/2021-11-11-23-55-03.png)

---

- `This input should not be empty` はチェックをつけて必須にします
- 要素の名前として `Input pet gender` を指定します

![bg right h:700px](images/2021-11-11-23-55-03.png)

---

#### 登録ボタン

- ここまでペット情報の入力ができたら登録ボタンを配置します
- 左パネルの `Visual elements` の中にある `Button` を選択し、右パネルでドラッグして要素を配置します

![bg right h:600px](images/2021-11-11-23-56-17.png)

---

- こちらも要素をダブルクリックして要素の詳細を設定します
  - Appearance タブの上部にある「...edit me...」と入力されている部分を編集して「REGISTER」と入力します

![w:1000px](images/2021-11-07-11-32-37.png)

---

#### 各入力要素にラベルをつけましょう

- Adalo の時の画面のように、各要素の左上にラベルを用意しましょう
- 左パネルの `Visual elements` の中にある `Text` を選択し、右パネルでドラッグして要素を配置します

![bg right h:600px](images/2021-11-11-23-57-15.png)

---

- 配置する際、高さは 30px 以上になるように配置してください
- そうしないと、要素の中身が正しく表示されないためです！
- こちらも要素をダブルクリックして要素の詳細を設定します
  - Appearance タブの上部にある「...edit me...」と入力されている部分を編集して「Name」と入力します
  - ダイアログ中断にある `Style` に `H3 Sub Heading - Dark` を選択します

![w:600px](images/2021-11-07-11-39-17.png)

---

- 同じ要領でその他のラベルもつけてみましょう
- 同じ手順でもよいですが、先ほど作った Name のラベルをコピーして使い回すことで手間を省けます
  - コピー（Ctrl + C）してペースト（Ctrl + P）し、ラベルの内容だけ書き換える
- 最後にすべての要素の幅を 220px に統一してください
  - 各要素をダブルクリックしたときのダイアログから `W` (Width) の値を 220 に統一します
  - これは画面表示したときの見栄えを整えるためです

![w:500px](images/2021-11-07-11-45-50.png)

---

#### 最後に要素を整理してプレビュー

- 右パネルに配置した（Header を除く）すべての要素をドラッグで選択し右クリックから `Center horizontally` を選択し、入力フォームの横位置を中央に統一します

![bg right h:700px](images/2021-11-12-00-00-35.png)

---

- ここまで出来たら画面右上にある `Preview` をクリックしてプレビューを表示して動きを見てみましょう！
- この時、ログイン中の状態であることを確認してください！
  - これは、この後の一覧表示と連携するときに必要な情報となるためです

![](images/2021-11-12-09-22-41.png)

---

  - ヘッダーの右上のボタンが 
  - すべての要素が表示されていますか？
  - すべての入力フォームに値を入力できますか？
  - 画像を指定すると表示されますか？

![bg right h:500px](images/2021-11-12-00-05-36.png)

---

### データベースとつなげてみよう

- ここまでで画面レイアウトが整ったので、いよいよデータベースとつなげてみましょう

---

#### まずはペットの情報を保存するための箱を用意します

- 左パネルのタブから Data を選択
- すると Data types タブが有効になっていると思うのでその下にある Custom data types の中から `New type` と書かれたテキストボックスに「Pets」と入力してください

![bg right h:500px](images/2021-11-07-12-07-08.png)

---

- そして `Make this data type private by default` のチェックをつけて `Create` ボタンをクリックします

![bg right h:500px](images/2021-11-07-12-07-08.png)

---

##### ちなみに...

- Adalo と Bubble ではデータベースに関する各要素の呼び方が一部異なります

- Type: データの型（箱）を定義したもの
  - Adalo でいうところの Collection
- Field: データの型を表現するための要素
  - Adalo でいうところの Property

---

- 作成した Pets の type に対して要素（field）を追加していきます
- `Custome data types` から `Pets` を選択
- 右側の `Fields for type pets` の下にある `Create a new field` をクリック

![w:880px](images/2021-11-12-00-14-09.png)

- するとポップアップが表示されるので必要な情報を入力します

---

- `Field name` には要素の名前を入力します

![bg right h:450px](images/2021-11-07-12-17-50.png)

---

- `Field type` には要素の種類（テキスト、数字、日付など）を選択します

![bg right h:450px](images/2021-11-07-12-17-50.png)

---

- Adalo では Relationship から type 同士の関連を指定できました
- Bubble では `Field type` の選択肢の中に、登録されている type も表示されているので、そこで関連付けたい type を選択することで Adalo と同様のことが実現できます

![bg right h:450px](images/2021-11-07-12-17-50.png)

---

##### それでは Pets type に必要な field を追加していきましょう

- Name: text
- Image: image
- Birthday: date
- Gender: text

![bg right h:500px](images/2021-11-07-12-21-23.png)

---

### 登録ボタンをクリックしたらペットを登録できるようにする

- ペットの情報を格納するための箱が準備できたので、いよいよ登録ボタンに押したときにデータベースに保存する動きをつけていきます
- Bubble では動きを設定するのはすべて Workflow タブで操作をしていきます
- いきなり Workflow タブから設定も出来ますが、今回は動きをつける元となるボタンからワークフローの設定をしていきます

---

- 左パネルから Design タブを選択
- 右パネルからペット登録画面の "REGISTER" のボタンをダブルクリックします
- "Appearance" タブにある `Start/Edit workflow` をクリックします

![bg right h:400px](images/2021-11-07-12-26-27.png)

---

- すると Workflow タブに切り替わり、When の部分に `Button REGISTER is clicked` と表示されていると思います
  - これは文字通り "REGISTER" ボタンを押したときのワークフロー定義になります

![w:800px](images/2021-11-07-12-29-27.png)

---

- なので、その下にある `Click here to add an action...` を選択して、ボタン押下時の振る舞いを設定していきます

![w:800px](images/2021-11-07-12-29-27.png)

---

- `Click here to add an action...` を選択すると、様々なアクションを指定できるポップアップが表示されます
- 今回のようにデータベースに関する操作（アクション）の場合 `Data(Things)` を選びます

![bg right h:630px](images/2021-11-08-22-23-30.png)

---

- すると下位要素がさらに表示されると思いますので、その中から `Create a new thing...` を選択します

![bg right h:630px](images/2021-11-08-22-23-30.png)

---

- `Create a new Pets...` のダイアログが表示されるので、今回登録するタイプを指定します
  - 今回は Pets ですね
- すると `Set another field` というボタンが表示されるので、タイトルの通り画面で入力された項目を Pets の "field" にセットしていきます

![bg right h:400px](images/2021-11-12-00-22-31.png)

---

- ここでは Pets に保存したい項目の "field" 名を左辺に指定し、右辺に実際にその "field" に保存する値を指定します
  - まず、左辺に `Name` を選択します

![bg right h:400px](images/2021-11-12-00-25-50.png)

---

- 左辺を指定すると `=` に挟まれて今度は右辺に `Click` というのが表示されると思います

![bg right h:400px](images/2021-11-12-00-27-03.png)

---

- ここをクリックすると何やらいろいろな選択肢が出てきます
- 詳細はここでは割愛しますが、左辺に選択されたフィールドに対して設定する対象を指定します

![bg right h:600px](images/2021-11-12-00-27-53.png)

---

- 今回は画面で入力されたペットの名前になるので `Input pet name` という項目を選択します

![bg right h:600px](images/2021-11-12-00-30-52.png)

---

- この `Input pet name` というのは画面を作るときに入力要素に対して名前を付けたものがここに表示されています
- こうすることで、例えば 1 つの画面に複数の入力要素が存在したときにも、それらを一意に識別しやすくなります

![bg right h:600px](images/2021-11-12-00-30-52.png)

---

- `Input pet name` を選択するとさらに選択肢が表示されます
- ここでは画面で入力されたペットの名前の「値そのもの」を使いたいので `'s value` を選択します
  - その他の選択肢である `is valid` と `isn't valid` は入力された値が正しいかどうかの判定結果を使いたい時に利用します

![bg right h:500px](images/2021-11-08-22-33-45.png)

---

- すべて指定するとこんな感じ

![bg right h:700px](images/2021-11-08-22-40-07.png)

---

### 動かしてみよう！

- ここまで設定したら実際にプレビューでペットが登録されるかどうかを確認してみましょう
  - ちなみに "Ctrl + P" をクリックするとプレビュー表示ができます（ショートカットキー）
- 入力要素をすべて埋めて "REGISTER" ボタンをクリックしてみましょう
- 画面としては特に何も起こらないですが、実際にデータが登録されたかどうか見てみましょう

---

- プレビューを閉じ Data タブを開いて App data を選択、そして左パネル `All Pets` を選択したときに、先ほど画面から入力された情報が保存されていることを確認してください

![w:850px](images/2021-11-08-22-45-05.png)

---

- これで画面で入力した内容をデータベースに保存するところまで出来ました！ :tada:

- 続いて、画面遷移を作り込んでみます

---

#### 画面遷移してみよう

- 左パネルから Workflow タブをクリック
- 先ほど設定した "REGISTER" ボタンをクリックした時の振る舞いが表示されていると思います

![](images/2021-11-08-22-57-42.png)

---

- ここで "Create a new Pets..." の右にある `Click here to add an action...` をクリック

![](images/2021-11-08-22-57-42.png)

---

- 今度は `Navigation` を選択し、下位要素として `Go to page...` をクリック

![](images/2021-11-08-22-57-42.png)

---

- するとダイアログが表示されるので "Destination" に遷移したい画面を選択します
- 今回はペット一覧画面へ遷移したいので `index` を選択します

![bg right h:500px](images/2021-11-08-22-59-29.png)

---

- それではプレビューしてみましょう
- ペット登録画面が表示されたと思うので、先ほどと同じようにペット情報を入力し "REGISTER" ボタンをクリックします
- すると、まっさらなページに遷移したと思います
  - まだペット一覧画面を作っていないので今は問題ありません

- これで画面遷移もマスターしました！ :tada::tada:

---

### ペットの一覧表示

- 次にペットの一覧表示を作ってみましょう

![w:1000px](images/2021-11-12-01-20-27.png)

---

- 左上のページ一覧から `index` を選択
- 同じ要素を繰り返し表示する場合、 `Containers` の中から `Repeating Group` を選択
- 右パネルのキャンバスにドラッグします

![bg right h:500px](images/2021-11-09-20-00-45.png)

---

- 要素の詳細設定ポップアップが表示されるので設定していきます
- 一番上の要素名に `pet list` を入力
- `Type of content` には、繰り返し表示するデータのタイプを指定します
  - 今回は `Pets` ですね

![bg right h:500px](images/2021-11-12-00-54-44.png)

---

- `Rows` はデフォルトで表示する際の行数
  - データが複数あれば自動的に複数行になるためここでは `1` とします
- `Columns` は 1 行あたりの列数
  - 今回は `3` とします

![bg right h:500px](images/2021-11-12-00-54-44.png)

---

- もし 4 件以上のペットデータがあったときに、一覧を自動的に広げるために "Layout style" に `Full list` を選択しておきます
- また、それぞれのセルの中で画像の横幅をいっぱいに表示したいので Cell min width に括弧書きで記載されている current width と同じ値を設定しておきます（画像の例だと 193）

![bg right h:700px](images/2021-11-12-09-32-31.png)

---

- そして `Data source` の Click から `Do a search for` をクリック
  - これは一覧表示対象のデータ元を指定するためのものです
- 別のポップアップが表示されますので Type に `Pets` を指定します

![bg right h:500px](images/2021-11-12-00-57-12.png)

---

- これだけだと、未ログイン状態でもペットの一覧が表示できてしまうため、ログインユーザが登録したペットだけを表示するように条件を追加していきます
- "Add a new constraint" をクリックし、さらに条件を追加します
  - どんな設定内容になりますか？

![bg right h:500px](images/2021-11-12-01-58-11.png)

---

- 設定する条件としては「ペットの作成者（Created By）が "Current User" と同一であること」

![bg right h:500px](images/2021-11-12-02-00-38.png)

---

- 次に繰り返し表示する内容を設定していきます
- Adalo の時のように、画像と名前を表示してみましょう

![bg right h:500px](images/2021-11-09-20-09-03.png)

---

- まず `Visual elements` から `Image` を選択し、右パネルにドラッグ
  - このとき先ほど配置した "Repeating Group" の中に含める形でドラッグすると、後で移動する手間が無くなります
  - 後から Repeating Group に含めることも可能
  - 配置した後に Repeating Group の中いっぱいにドラッグして広げます
- 要素名に `pet list image` と名付けましょう

![w:600px](images/2021-11-12-01-03-31.png)

---

- 要素を配置したら、表示される詳細設定のポップアップから "Dynamic image" を選択
- すると `Insert dynamic data` というボタン（のようなもの）が表示されるのでクリック
  - これは固定の値や画像を表示するのではなく、文字通り動的に値や画像を出したい時に利用する機能となります

![w:600px](images/2021-11-12-01-04-41.png)

---

- クリックすると、プルダウンが表示されますので、そこから `Current cell's Pets` をクリック
  - これは文字通り現在のセルのペットのデータを使いたい場合に利用できます

![bg right h:600px](images/2021-11-12-01-08-38.png)

---

- `Current cell's Pets` を選ぶとさらにプルダウンが表示され、Pets タイプが持っている field が表示されますので `'s Image` をクリック
  - これで、現在のセルのペットの画像が表示する、という命令になるため、ペットデータが複数存在する場合に、それぞれのセルにペットの画像が並ぶようになります

![bg right h:600px](images/2021-11-12-01-09-35.png)

---

- 先ほどセルの横幅いっぱいに画像を表示する設定にしたのですが、画像要素の "Run-mode rendering" の値を `Streth` から `Zoom` に変えておきましょう
  - こうしないと、セルの中で画像の縦横比率を自動で変えられてしまうため、拡大表示に変更します

![bg right h:540px](images/2021-11-12-09-35-52.png)

---

- 続いて画像下に表示する名前の背景を設定しましょう
- `Visual elements` から `Shape` を選択し、右パネルにドラッグ
  - こちらも "Repeating Group" の中に含める形でドラッグ
  - 配置した後に Repeating Group の下部に移動して横幅いっぱいにドラッグして広げます
- 配置した Shape の Color の横の数値を `30` にします
  - これは画像の透過率となり 100 が非透明、0 が透明となります

![w:800px](images/2021-11-09-20-16-58.png)

---

- 最後にペットの名前を表示します
- `Visual elements` から `Text` を選択し、先ほど配置した Shape の上にドラッグ
  - こちらも Repeating Group の中に含める形でドラッグ
  - 配置した後に Shape と同じサイズにドラッグして広げます
- 要素名に `pet list name` と名付けましょう

![w:800px](images/2021-11-12-01-13-10.png)

---

- ペットの画像と同様、ペットの名前も Dynamic data を使います
- `...edit me...` となっている部分をクリックすると、画像の時と同様 `Insert dynamic data` が表示されるので
  そこから `Current cell's Pets` --> `'s Name` を選択

![w:800px](images/2021-11-09-20-29-45.png)

---

#### ここまで出来たらプレビューしてみましょう

- ペットの一覧として、ペットの画像とペットの名前が表示されていますか？

![w:1000px](images/2021-11-12-01-20-27.png)

---

- ちなみに Repeating Group はレスポンシブに対応しているため、画面の横幅を変えると自動的に画像のサイズが変わると思います！

![bg right h:600px](images/2021-11-12-09-40-57.png)

---

#### ペット一覧から登録画面の導線を用意しましょう

- ペットの一覧画面が出来たので、一覧画面から登録画面への導線を用意しましょう
- この導線は Header からいつでも遷移出来るように導線を用意してみましょう

![w:900px](images/2021-11-12-01-55-32.png)

---

- 左上のメニューをクリックし、その中から Header を選択します

![w:900px](images/2021-11-12-01-25-24.png)

---

- するとヘッダー部分の要素が右パネルに表示されるので、ここを編集していきます

![w:1100px](images/2021-11-12-01-26-29.png)

---

- まず元々ある `Bubble Forum` と `FAQs` のリンクは不要なので削除します
- そして `Visual elements` の中から `Link` を選択してヘッダー領域にドラッグします

![w:1000px](images/2021-11-12-01-30-55.png)

---

- リンクの名前は "PET REGISTER" としましょう
- "Destination page" として遷移先は `pet_register` を選択
- "This element is visible on page load" のチェックを外します
  - このチェックを外す、要素は常に非表示となります
  - この理由はこのあと説明しますね

![bg right w:420px](images/2021-11-12-01-38-44.png)

---

- このペット登録のリンクは、ユーザがログインしているときだけ表示させたいので、その制御を設定していきます
- 同じダイアログから `Conditional` タブを選択し `Define another condition` をクリック

![bg right h:400px](images/2021-11-12-01-41-08.png)

---

- ここでは、このリンク自体に対して簡単な振る舞いを定義することができます
- 今回の場合、ユーザがログインしているときだけ表示させたいので、まず When のところで、表示させたいときの条件を設定します

![bg right h:600px](images/2021-11-12-01-43-35.png)

---

- Click から `Current User` を選択し、次に `is logged in` を選択することで、「現在のユーザがログインしている場合」という条件を指定できます

![bg right h:500px](images/2021-11-12-01-46-14.png)

---

- 続いて、When を満たしたときの振る舞いを設定します
- `Select a property to change when true` のプルダウンの中から `This element is visible` を選択します
  - これは文字通り、この要素を表示する、という振る舞いになります
- 選択したら、その振る舞いにチェックを付けます

![bg right h:500px](images/2021-11-12-01-48-31.png)

---

#### ではプレビューしてみましょう！

- 一度 index へ戻り、プレビューを実行
- 現在はログイン済みの状態のはずなので、"PET REGISTER" のリンクが表示されていると思います
- そこから右上の LOG OUT をクリックすると、"PET REGISTER" のリンクが非表示になりましたか？

---

## ペット詳細画面を作ってみよう

- 次にペット詳細画面を作っていきます
- ここでのポイントは、一覧画面で選択されたペットの情報の受け渡し部分ですね

![bg right h:700px](images/2021-11-12-02-07-02.png)

---

### まずは詳細画面を新たに用意

- 左上から "Add a new page..." を選択
- "Page name" は `pet_detail`
- "Clone from" は画面構成が似ているので `pet_register` を選びましょう

---

- クローン（コピー）してきたままだと、登録画面と同じになってしまうので見直していきます

![bg right h:700px](images/2021-11-10-21-22-02.png)

---

- まずは入力項目として用意した入力要素をすべて削除します
![bg right h:700px](images/2021-11-10-21-23-28.png)

---

- 続いて表示用の要素を配置していきます
- "Visual elements" からそれぞれの要素ドラッグしてみましょう
  - Name: Text
  - Image: Image
  - Birthday: Text
  - Gender: Text
- 要素の幅（w）はすべて 220px としてください

![bg right h:700px](images/2021-11-10-21-55-27.png)

---

- 要素の準備が出来たら実際にデータベースから参照する値を定義していきます
- まず最初にこの画面自体の詳細設定用ダイアログを表示します

---

- 右パネルの左上の部分から `pet_detail` を選択すると、ダイアログが表示されます
  - 要素がいくつも重なっているときなどはここから要素を選ぶことも出来て便利です！

![](images/2021-11-10-21-59-18.png)

---

- その中から `Type of content` という項目があるので、そこで `Pets` を指定します
- こうすることで、この画面を表示する元となるデータベースのタイプが何なのかを指定でき、各項目にはそのタイプのどのフィールドを使うのかを指定するだけで済みます

![bg right h:600px](images/2021-11-10-22-01-45.png)

---

- ちなみに、タイプは指定できましたが、具体的にどのペットの情報なのか（ポチなのかタマなのか）は一覧画面から遷移するときに指定しますが、これは後ほど設定しましょう

---

- それでは表示用の要素と Pets タイプのフィールドを紐付けていきます
- まずは Name からやってみましょう
- 今回のように、データベースから取得した値を動的に表示したい場合、どうやるか覚えていますか？

:ghost::jack_o_lantern::ghost::jack_o_lantern:

---

- そうです！ "Dynamic data" を使います！
- Name の要素をダブルクリックし `...edit me...` と書かれた部分をクリックすると `Insert dynamic data` というボタンが表示されるのでクリック

![w:700px](images/2021-11-10-22-06-51.png)

---

- すると、プルダウンが表示され、その中から `Current Page Pets's` をクリック
  - これは文字通り現在のページに割り当てられたペットの情報を指しています
- すると Pets タイプが持っているフィールドが表示されるので `'s Name` を選択

![bg right h:260px](images/2021-11-10-22-11-03.png)

---

- 同じ要領で Image / Birthday / Gender の Dynamic data を設定してみましょう
- 設定が済んだらペット詳細に関するすべての要素を選択して中央寄せにしましょう
  - 要素を選択した状態から右クリック --> `Center horizontally`

![bg right h:700px](images/2021-11-10-22-14-56.png)

---

- 設定が済んだらプレビューしてみましょう
- 正しく値が表示されませんよね？
- これはまだ一覧画面からどのペットの情報なのか？を指定していないからです
  - `Lorem ipsum` と出ているのはよくあるダミーコンテンツのイディオムを Bubble が自動的に出しています

![bg right h:700px](images/2021-11-10-22-17-32.png)

---

### それでは一覧画面と詳細画面をつなげてみましょう

- 左上のメニューから index ページに切り替えます
- 画面操作のイメージとしては、ペット一覧画面で表示されているペットの画像をクリックしたら、そのペットの詳細画面へ遷移させたいですね
- なので、一覧画面のペット画像に対してワークフローを設定していきます

---

- ペット画像をダブルクリックし `Start/Edit workflow` をクリックします
- すると "When pet list image is clicked" の箱に対して振る舞いを設定する前の状態になっているかと思います

![bg right h:400px](images/2021-11-10-22-22-27.png)

---

- なので "Click here to add an action" から Navigation -> Go to page を選択
- ダイアログが表示されるので `Destination` (遷移先) には `pet_detail` を指定

![bg right h:500px](images/2021-11-10-22-32-42.png)

---

- そして `Data to send` に `Current cell's Pets` を指定
  - これでペット詳細画面へ遷移するときに、現在のセルのペット情報を遷移先へ送る、という指定ができました

![bg right h:500px](images/2021-11-10-22-32-42.png)

---

- それではプレビューしてみましょう
- 一覧画面でペットの画像を選択すると、そのペットの詳細画面が表示されることを確認できましたか？

---

### Appendix

- ここで表示のアドバイス
- Birthday と Gender の表示が少し味気ないので、表示の書式を変えてみましょう

![bg right h:700px](images/2021-11-10-22-36-08.png)

---

### Appendix1: 誕生日の書式を日本風に変えてみます

- pet_detail 画面を Design タブで開きます
- そして Birthday の表示要素をダブルクリックし、詳細設定用ダイアログを表示します

---

- そして `Current Page Pets's Birthday` の Birthday の部分をクリックすると、後ろに `More` という項目が表示されると思いますので、それをクリックします

![bg right h:400px](images/2021-11-10-22-40-25.png)

---

- すると Birthday の値の表示フォーマットをさらに指定できるようになります
- 今回は一番上の `:formatted as DD/MM/YY` をクリックします
  - DD/MM/YY には本日日付が入っていると思います

![bg right h:700px](images/2021-11-10-22-42-24.png)

---

- すると、さらに隣に `Date Formatting` のダイアログが表示されると思います
- ここでフォーマットの細かな指定が可能です
- 今回は `Format type` に `Custom` を選択し、 `Custom format` に `yyyy年m月d日` を指定します

![bg right h:400px](images/2021-11-10-22-46-11.png)

---

- それではプレビューしてみましょう
  - 一度 index ページを開いた上で、プレビュー実行
- ペット一覧からペット詳細を開いてみると Birthday の日付が指定した書式になっていると思います

![bg right h:700px](images/2021-11-10-22-45-42.png)

---

### Appendix2: 性別のラベルを変えてみよう

- pet_detail 画面を Design タブで開きます
- そして Gender の表示要素をダブルクリックし、詳細設定用ダイアログを表示します
- 先ほどと同じ要領で `Current Page Pets's Gender` の Gender の部分をクリックし `More` をクリックし、続けて下記のように入力します

---

- `is` を選択、 `Male` と手入力してエンターキークリック、 `:formatted as text` を選択
- すると `Boolean Formatting` というダイアログが表示されるので下記の通り入力します
  - Formatting for yes: 男の子
  - Formatting for no: 女の子

![bg right h:300px](images/2021-11-10-22-55-11.png)

---

- これは下記の処理を書いていることになります

```
現在のペットの Gender（性別）が Male だった場合には「男の子」、そうでない場合は「女の子」を表示する
```

ここで少しプログラミング的な要素が出てきましたね！

---

- それでは index ページからプレビュー実行してみましょう
- ペット一覧からペット詳細を開いてみると Gender の値が「男の子」「女の子」になっていると思います

![bg right h:700px](images/2021-11-10-22-57-59.png)

---

### Appendix3: 詳細画面から一覧画面への導線を設けてみよう

- 詳細画面から一覧へ戻るための導線を用意してみましょう
- これまでの講義を踏まえるときっとイメージは沸いていると思うので、完成イメージとヒントだけ記載しておきます

---

#### ヒント

- 使用する要素は `Visual elements` の `Link`
- Link 要素の場合、画面遷移は Workflow ではなく、要素自身に "Destination page" を設定できます
- 完成イメージ

![bg right h:700px](images/2021-11-10-23-12-19.png)

---

## ペットの体重を管理しよう

- 続いてペットの体重管理を見ていきましょう

![bg right h:700px](images/2021-11-12-02-17-49.png)

---

- まずは Type を用意していきます
- Data タブから New type として `PetWeightLogs` を入力して Create します
- 続いて field を設定していきます

---

- 画面から入力されたペットの体重
  - WeightKg: number
- どのペットの体重かを紐付ける
  - pet: Pets

![](images/2021-11-10-23-37-27.png)

---

- データベースの準備が出来たので画面を設定していきましょう
- まずはペットの体重管理画面を新たに用意します
- Add a new page からページ名 `pet_weight_register` でコピー元は `pet_register` を選択して CREATE

![bg right h:380px](images/2021-11-10-23-23-54.png)


---

- この画面も、ペット詳細から遷移する前提であるため `pet_weight_register` 画面に対する詳細設定ダイアログから、 `Type of content` に Pets を指定します

![bg right h:550px](images/2021-11-11-08-21-17.png)

---

- コピー元のペット登録画面の要素が残っているので、不要なものは削除しつつ参考画像のような要素を配置します
- ただし、グラフ描画エリアは現時点では配置しません

![bg right h:550px](images/2021-11-10-23-28-08.png)


---

- このとき、体重の入力要素について、今回は小数点付き数字だけの入力を許容したいので、その設定だけ行います
- ペットの体重入力要素をダブルクリックし `Content format` に `Decimal` を選択します
  - ちなみに `Integer` は小数点なしの整数入力の場合に選択します

![bg right h:700px](images/2021-11-10-23-30-42.png)

---

- 次に、体重保存のボタンクリックに対してワークフローを設定していきます
- ADD ボタンをダブルクリックし、詳細設定ダイアログから Start/Edit workflow を選択

![w:800px](images/2021-11-11-08-23-59.png)

---

- すると `When Button ADD is clicked` に対して、すでに振る舞いがいくつか設定されています
- これはページ作成時に `pet_register` をコピーして作ったため、そのときのワークフロー設定が引き継がれています
- 今回は新たに振る舞いを定義していくので、既存のワークフローは削除します
- Step1 / Step2 の振る舞いを選択すると、右下に `delete` と表示されているので、そこから振る舞いを削除します

![w:400px](images/2021-11-11-08-26-36.png)

---

- それではワークフローを設定していきましょう
- まずやりたいのは、「画面で入力された体重の値を、先ほど用意した PetWeightLogs に保存する」ですね
- 今までの講義内容を踏まえて設定してみてください！

- 次のページに解説を載せているので、まずはやってみましょう！

---

# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass:
# :hourglass:

---

- まず設定するアクションとしては `Data(Thing)` --> `Create a new thing...` ですね

![w:600px](images/2021-11-11-08-43-18.png)

---

- そして、登録するタイプとフィールドを指定します
- 今回登録するのはペットの体重なので Type は `PetWeightLogs`

![bg right h:600px](images/2021-11-11-08-46-21.png)

---

- 設定するフィールドは `WeightKg` と `pet` ですね
- `pet` フィールドを設定しないと、どのペットの体重なのかを判断できないので指定します
- その際に指定するのが `Current Page Pets` 、今表示している画面の Pets となります

![bg right h:600px](images/2021-11-11-08-46-21.png)

---

- 登録ができたら画面を再描画して、この後表示するグラフを最新化したいので、登録後に画面を再描画する振る舞いを定義しましょう
- 画面操作に関するアクションは `Navigation` でしたね
- その中のサブメニューを見てみると `Refresh this page` というピッタリのアクションがあるのでこれを選択しましょう

![w:500px](images/2021-11-11-09-16-15.png)

---

- これでペットの体重登録が出来たので、詳細画面からの導線を用意しましょう
- 詳細画面を開き、Image と Birthday の間にリンクを用意しましょう
- リンクは `Visual elements` の `Link` を使いましょう

---

- ポイントとしては 2 つ

1. 遷移先を `Destination page` に設定する
2. リンク先に対して現在ページのペット情報を渡してあげる

- 次のページに設定イメージを書いていますのでまずはご自身で設定してみましょう

---

- こんな感じ！

![w:1000px](images/2021-11-11-08-56-41.png)

---

- 詳細画面から体重管理への導線が出来たら、逆の導線も用意しておきましょう
- 考え方は詳細画面に設置したリンクと同じで大丈夫です

---

- 設定できたら一覧画面に戻ってプレビューを実行してみましょう
- 一覧、詳細、体重管理へ遷移した後、Weight に値を入力して ADD を押すと画面が再描画されましたかね？

![bg right h:700px](images/2021-11-11-09-18-33.png)

---

- 念のため、データベースにデータが登録されていることを確認してみましょう
- Data の App data タブから `All PetWeightLogs` を選択すると左側にデータが登録されていますよね？

![w:1200px](images/2021-11-11-09-20-13.png)

---

## ペットの体重をグラフィカルに表示してみよう

- 登録したペットの体重を Adalo の時と同様グラフを使って表示してみましょう

![bg right h:700px](images/2021-11-12-02-25-30.png)

---

### まずはプラグインを導入します

- Bubble でもグラフ表示の機能は標準では搭載していないため、プラグインという形で機能を追加します
- Adalo の時は Component という形でしたが、Bubble では Plugins から導入します

---

- 左メニューから Plugins を選択し、プラグイン画面を表示します
- そして、右上の `+ Add plugins` を押して追加するプラグインを検索します

![w:1100px](images/2021-11-11-20-21-36.png)

---

- `Install New Plugins` というポップアップが表示されますので、左パネルの検索窓に `chart` と入力します
- すると、右パネルに検索結果が表示されますので、その中から（おそらく一番上にある） `Chart Element` の `Install` ボタンをクリックします

![w:1100px](images/2021-11-11-20-26-37.png)

---

- インストールが完了したら DONE をクリックしてポップアップを閉じます
- Installed Plugins に Chart Element が入っていれば OK デス

![bg right h:700px](images/2021-11-11-20-40-34.png)

---

- Bubble のプラグインには無料のものと有料のものが存在します
- プラグイン一覧の画面で `Free` と書かれているもの、もしくは `By Bubble` と書かれているものは無料です
  - とくに `By Bubble` と書かれているものは文字通り Bubble の公式が提供しているプラグインのため、何かと信頼できます
- 逆に金額が記載されているプラグインは文字通り有料です
- 様々なプラグインがあるので、導入する際には Free のもので事足りるプラグインがないかをまずは探し、有料のプラグインしかどうしても存在しない場合には有料のプラグインインストールを検討してみても良いでしょう

---

![w:1200px](images/2021-11-11-20-31-40.png)

---

### それでは実際にグラフ描画を行っていきましょう

- `pet_weight_register` ページの Design を開きます
- すると `Visual elements` の中に `Line/Bar Chart` という要素が新たに追加されていると思いますので、この要素を選択して早速体重入力の上部にドラッグします

![bg right h:700px](images/2021-11-11-20-43-44.png)

---

- 描画するとこれまでと同じく詳細設定用のダイアログが表示されますので、各項目を設定していきましょう
- `Chart type` はグラフの種類を指定します
  - 今回は折れ線グラフなので `Line` とします

![bg right h:600px](images/2021-11-11-20-48-33.png)

---

- `Type of data` はグラフ描画するデータのタイプを指定します
  - 今回はペットの体重表示となるので `PetWeightLogs` とします

![bg right h:600px](images/2021-11-11-20-48-33.png)

---

- 続けて `Data source` に対象データの条件を指定します
  - 一覧画面での条件指定と同じように、まずは `Do a search for` を選択

![bg right h:600px](images/2021-11-11-20-48-33.png)

---

- Do a search for のダイアログがさらに表示されますので
  - `Type` には対象データの型を指定しますので `PetWeightLogs` を指定

![bg right h:500px](images/2021-11-11-20-53-49.png)

---

- これだけだとすべてのペットのすべての体重データが表示されてしまうので絞り込みの条件を指定します
  - `Add a new constraint` をクリックして条件を指定します

![bg right h:500px](images/2021-11-11-20-53-49.png)

---

- まずは Click をクリックすると Type に指定した `PetWeightLogs` が持っているフィールドが表示されます
- 今回は `PetWeightLogs` に関連する `Pet` の情報が、現在表示しているペットと同じデータを対象とします

![bg right h:550px](images/2021-11-11-20-55-37.png)

---

- これを条件として表現するとこのようになりますので、それを設定してみましょう
  ```
  pet = Current Page Pets
  ```

![bg right h:550px](images/2021-11-11-20-55-37.png)

---

- 最後にデータの並び順を指定します
  - グラフの見せ方として、登録した体重を新しいもの順にしたいと思います

![bg right h:700px](images/2021-11-12-02-33-14.png)

---

- `Sort by` に `Created Date` を指定します
  - これで並び順のキーを指定しました
- `Descending` に `"yes"` を指定します
  - これでキーの新しいもの順（降順）と指定しました

![bg right h:700px](images/2021-11-11-21-00-40.png)

---

- 仮に登録日の古いもの順としたい場合、 `Descending` に `"no"` を指定すれば古いもの順（昇順）となります
- 設定完了したら `Close` をクリックしてこのサブダイアログを閉じておきます

---

- 最後にグラフに描画する X 軸と Y 軸を指定します
- 今回の場合、X 軸は登録日時、Y 軸は体重となります

![bg right h:700px](images/2021-11-12-02-33-14.png)

---

- X 軸の設定は `Label expression`
  - 今回は `Current point's Creation Date` とします
- Y 軸の設定は `Value expression`
  - 今回は `Current point's WeightKg` とします

![bg right h:600px](images/2021-11-11-21-07-32.png)

---

- `Current point` は対象データのタイプで指定した `PetWeightLogs` の各データをプロットした 1 件 1 件のデータを指します

---

- それでは一覧画面に戻ってプレビューしてみましょう！
- 一覧で選択したペットに対して登録された体重がグラフとして表示されましたか？
- 同じ画面で Weight をどんどん追加するとグラフの内容が変化しますか？

![bg right h:700px](images/2021-11-11-21-09-48.png)

---

### Appendix4: グラフの X 軸のラベルを変えてみよう

- 現時点の X 軸のラベルは長ったらしい日時の書式になっているので、皆さんでお好きなフォーマットに変えてみてください
- 例えばこんな感じ

![bg right h:600px](images/2021-11-11-21-13-22.png)

---

### Appendix5: 体重データが 1 件もない場合にメッセージを出してみよう

- 現在の開発内容だと、ペットの体重が 1 件も登録されていない場合、グラフ描画エリアが空白になってしまい、ページとしての見栄えが悪いですね

![bg right h:680px](images/2021-11-11-21-55-31.png)

---

- そこで、ペットの体重が 1 件も登録されていない場合に専用のメッセージを表示して、ユーザビリティを向上させてみましょう

![bg right h:680px](images/2021-11-11-22-27-19.png)

---

- 対応イメージとしては、グラフ要素と同じ幅と高さの Shape を同じ位置に用意
  - その上に表示したいメッセージを Text として配置し、Shape と Text をグルーピング
  - グルーピングすることで 1 つの要素として扱うことができます
- その Shape に対して下記を設定します
  - 要素自身は常に非表示とする
  - Conditional で PetWeightLogs の件数が 0 件だった場合に、要素を表示する
- こうすることで、体重が 1 件も登録されていない場合は Shape を表示し、そうでない場合はグラフを表示することができます

---

- 設定イメージはこんな感じです

![w:1000px](images/2021-11-11-22-41-24.png)

---

### Appendix6: ペット一覧にメッセージを出し分けてみよう

- ペット一覧はログインしていないと表示されません
- さらに、ログインしていてもペットが 1 件も登録されていないと何も表示されません
- しかし、ユーザからすると、なぜペット一覧が表示されていないのかが判断つきません

---

- そこで、それぞれの状態に応じてメッセージを出し分けて見ましょう

![w:900px](images/2021-11-12-18-12-17.png)
![w:900px](images/2021-11-12-18-13-40.png)

---

- 設定の考え方は先ほどのペットの体重が 0 件の時の出し分けと同じです
- それぞれのメッセージを用意しつつ、デフォルトでは非表示設定にしておきます
- その上で、それぞれの条件に合致する場合に、メッセージを表示させます
  - 現在のユーザがログイン済みかどうか？
  - 現在のユーザがログイン済みで、かつそのユーザが登録したペットが 1 件以上存在するか？
- 次のページに答え（設定内容）を書いています！

---

- 現在のユーザがログイン済みかどうか？

![w:600px](images/2021-11-12-18-16-33.png)

---

- 現在のユーザがログイン済みで、かつそのユーザが登録したペットが 1 件以上存在するか？

![w:550px](images/2021-11-12-18-17-30.png)

---

#### Appendix7: 詳細画面から更新画面への導線を設け、更新機能を作ってみよう

- ポイントとしては次のシートの通りです！ぜひ実践してみてください！

![bg right h:700px](images/2021-11-12-09-56-23.png)

---

- 更新画面は登録画面とほぼ同じ画面要素を持つので `pet_register` を Clone して `pet_update` を作ってみましょう
- 登録画面では、各入力要素（名前や誕生日など）の中身は空っぽでしたが、更新画面では既に登録済みのデータの値を画面表示時点でセットしてあげる必要があります
- 各入力要素のダイアログからそれっぽい項目がありますので、そこに初期値となる値を指定します
  - Hint:bulb: Insert dynamic data
  - Hint:bulb: Initial content

---

- 更新ボタンを押したときの振る舞いについては、新規登録時には `Data(Thing)` の `Create a new thing...` でしたが、今回は更新ですよね
  - 更新といえば change... お、それっぽいアクションがありそうですね :yum:
- 最後に詳細画面から更新画面へ遷移するとき、詳細画面で表示しているペットの情報を渡してあげる必要がありますね。これは今日の講義で学んだ部分です！
  - Hint:bulb: Data to send

---

# まとめ

- 今回のレクチャーでは Bubble の使い方から始まり、実際に画面をデザインするところから、データベースとの連携まで行いました
- 基本的な流れは Adalo と似ている部分もありつつ、ワークフロー周りの考え方はビジュアルプログラミングツールと呼ばれる所以をを少しは感じていただけたかなと思います
- 次回は Bubble のより深いところをレクチャーしていければと思いますので乞うご期待！

---

# 以上です！
# お疲れさまでした！