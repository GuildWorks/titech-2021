---
marp: true
theme: default
size: 16:9
header: ''

page_number: true
paginate: true
---

Programming Boot Camp Learning Phase #4

# Bubble Basic #2

2021/11/20

---

## 事前準備

- 本日は前回作成したアプリケーションの続きから開発していきます
- 前回作成したアプリケーションは個々にカスタマイズしている部分もあると思いますので、開始時点をそろえるため、こちら側で用意したアプリケーションを複製したものを利用してもらいます
- 複製したアプリケーションを配布しますので、`Naotake KYOGOKU` 宛てに、Bubbleのアカウントを作成したメールアドレスを伝えてください。

![w:500px](images/2021-11-17-05-35-39.png)

---

## 今日やること

  - 前回のおさらい
  - ユーザーインタフェースを作りこむ
  - ロジックを作りこむ

---

## 前回のおさらい

- [Bubble](https://bubble.io/) はビジュアルプログラミングツールとうたっており、画面からポチポチと操作して、見た目や動きをプログラミングできるツールです。
- Webアプリケーション前提であり、ディスプレイサイズにあわせた対応をいれスマホやPCに対応させます。

- 前回お休みの方はこちらの資料でキャッチアップしましょう
  - https://github.com/GuildWorks/titech-2021/tree/master/docs/Bubble1

---

## 前回のおさらい

ペット管理アプリケーションのペットの登録、一覧、詳細、体重ログの画面を
作りながら、Bubbleの基本である、Design/Workflow/Dataの使い方を学びました。

![h:383px](images/2021-11-17-05-09-19.png) ![h:383px](images/2021-11-17-05-13-24.png) ![h:383px](images/2021-11-17-05-14-49.png) ![h:383px](images/2021-11-17-05-15-59.png)

今回はここに対して、ユーザーインタフェースやロジックを作り込んでいきます

---

今日やること

TODO

---

## 様々なディスプレイサイズにあわせる

- WebアプリケーションはPCやタブレット、スマートフォンといった様々な端末で利用されます。
- 端末毎にディスプレイサイズが違うのですが、それらに対応する手法としてレスポンシブウェブデザインというデザイン手法があります
- 画面サイズに応じて、要素が伸びる／縮む、折り返す／折り返さない、表示する／表示しないといった見た目の切り替えを行うという手法になります。
- Bubbleは標準でレスポンシブウェブデザインの機能をそなえており、意識しなくても対応されていることもあります。

--- 

## レスポンシブウェブデザインの考え方

- レスポンシブウェブデザインを考えるときには、まずはPC画面を作成し、ディスプレイサイズが小さくなっていったときの表示ルールを付け足すことが多いです。
- スマートフォンでの利用場面が主となるような場合には、スマートフォンの画面を先に作成して、PC表示をあとから整えるということもあります。

さっそく体験してみましょう。

---

## 要素が伸びる/縮む

トップページをこんな感じにしてみます。
![w:800](images/2021-11-17-06-14-29.png)　![w:200](images/2021-11-17-06-15-03.png)

--- 

## まずは

ウォーミングアップがてら、ロゴを変えておきましょう。

![](images/2021-11-17-06-17-47.png)

![](images/2021-11-17-06-18-43.png)

---

## ヘッダーコンポーネントを開く

![w:900px](images/2021-11-17-06-21-12.png)

---

## PetLogのロゴに変更する

- bubbleのロゴを選択して、Deleteしましょう
- Visual elementからテキストを選択して、ロゴの位置に配置します
- 配置したら、テキストに`PetLog`と入力します。
- Styleには`H1 Heading - Dark`を指定しましょう。
- 横幅と高さは直接整えてよいですが、数値で指定することもできます

![bg right w:300px](images/2021-11-17-06-27-04.png)

---

## PetLogのロゴからトップページに戻れるようにしておく

- 追加した`PetLog`のテキストを選択して、`Start/Edit workflow`を選ぶ

![bg right w:400](images/2021-11-17-07-16-43.png)

---


## PetLogのロゴからトップページに戻れるようにしておく（つづき）

- `Click here to add an action...`を選択
- `Navigation`>`Go to page...`を選択
- Destinationに`index`を選択

![bg right w:600](images/2021-11-17-07-18-05.png)

---

## 表示を確認しましょう

- indexページに戻って
- 画面右上のPreviewボタンを押す
  - もしくは、Windowsは`ctrl + p`、Macは`cmd + p`を押す
- `PetLog`にマウスオーバーしたら、マウスポインターが矢印から指に変わっている
  - クリックしてもトップ（同じページ）になる

![w:800](images/2021-11-17-06-31-27.png)

前回やった操作方法を、思い出してきましたか？

---

## トップとリストを別画面にする
トップページを作り込みたいので、トップページとリストページを別画面にします。
bロゴの右から、`Add a new page..`を選択してください

![w:900](images/2021-11-17-06-34-58.png)

---

## リスト画面を複製する

- Page Nameに、`pet_list`といれてください
- Clone fromに、`index`を選択してください。
- indexページを元に、pet_listページが複製されます

![bg right w:500](images/2021-11-17-06-38-56.png)


---

## サインアップ、ログイン、ログアウト後の遷移先を整えます

- サインアップとログインはBubbleが最初から用意してくれているポップアップを利用しています。ポップアップ内のWorkflowに対して処理を追加します
- ログアウトはBubbleが最初から用意してくれているヘッダーコンポーネントを利用しています。コンポーネント内のWorkflowに対して処理を追加します
- ついでに、Bubbleがどのように認証機能を定義しているかも、ちらっと見ていきます。サインアップ、ログイン、ログアウトもBubbleが用意されているActionを組み合わせてできていることがわかります。

---

## サインアップ、ログイン後はリストページに遷移

- bロゴの右から、`Signup/Login Popup`を選択
- 左メニューから`WorkFlow`を選択
- `Gutton LOG IN is Clicked`を選択
- `Click here to add an action..`を選択
- `Navigation`>`Go to page...`を選択

![bg right w:600](images/2021-11-17-06-49-10.png)

---

## サインアップ、ログイン後はリストページに遷移（つづき）

- Destinationに`pet_list`を選択
- 同様にWorkFlow内の`Button SIGN UP is clicked`にも遷移先を追加

![](images/2021-11-17-06-54-26.png)

---

## ログアウト後はトップページに遷移

- bロゴの右から、`Header`を選択
- 左メニューから`WorkFlow`を選択
- `Button SIGN UP OR LOGIN is clicked and Current User is logged in`を選択
- `Click here to add an action..`を選択
- `Navigation`>`Go to page...`を選択して、indexページを指定

![bg right w:600](images/2021-11-17-07-01-40.png)

---

### サインアップ、ログアウト、ログインを試してみてください

- bロゴ右から、`index`に戻ってプレビュー
- サインアップ、ログイン後はURLがpet_listになっていたら、うまく設定できています
- ログアウト後はURLがpet_listでなかったら、うまく設定できています

![](images/2021-11-17-06-59-07.png)

---

## 要素が伸びる/縮む

では、あらためて、トップページをこんな感じにしてみます。
![w:800](images/2021-11-17-06-14-29.png)　![w:200](images/2021-11-17-06-15-03.png)

---

## トップページに画像を追加する

---

## テキストを追加する

---

## レスポンシブでの表示を調整する

---

## 折り返す／折り返さない

- pet_detailとpet_weightを統合して、PCとスマホでレイアウトや表示非表示を制御する

---

## スタイルをつける

- pet_detailで新しいスタイルを作ってラベルにあてる
- すでにあるプライマリーボタンやリンクを変える
- カラーパレットを変える

---

## インタラクションをつける

- pet_listでマウスホバーで枠線がつくとか影がつくとかやる

---

## コードを埋め込む

- Bubble Toolboxを使って、ちょっとした計算や処理（なににしようかな？）

---

## 権限制御をいれる

- ロール（Owner、Advisor、Admin）を作る
- 管理者画面を作る
- Advisor追加をつくる

---

## 演習

- Advisorのログイン、ペット一覧表示をつくる

---
