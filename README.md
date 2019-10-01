# GitHub Flow Sample

## About

GitHubを使い、Gitでの開発管理フローを学ぶ資料です。

基本的な流れとしては、

- (1) Issueを起こす
- (2) ブランチを切る
- (3) 実装を行う
- (4) プルリクエストを作成し、レビュー
- (5) マージ

というフローになります。

また基本運用としては`master`ブランチを主として、各拡張ごとに分かりやすい名前でブランチを切る運用とします。

## 運用フロー
### (1) Issueを起こす

まずは`Issue`を起こすことからはじめます。`Issue`とは日本語で「問題」を意味する単語であり、`Git`を使い最小の実装を進めていく際の指標となるものでもあります。  
そのため`Issue`は、「大きな範囲や抽象度の高い内容」で起こさずに「小さく具体的な内容」ごとに作成すると良いでしょう。

また、`GitHub`や`GitLab`などのホスティングサービスなどでは`Issue`を作成する際に`Markdown`を使うことができます。`Markdown`を使うことで以下のように`Issue`内に`Todoリスト`を作成することもできます。

ex:
- [ ] Aクラスの仕様書作成 
- [ ] Aクラスの実装
- [ ] Aクラスのテスト

### (2) ブランチを切る

次に、作成した`Issue`に対になるブランチを作成していきます。  
なお、`GitHub`などのホスティングサービスではWeb画面から新規でブランチを作成することもできます。

ブランチの作成時に注意が必要なのは、「ブランチ名」から対になる`Issue`が何であるか分かるようにする点です。

例えば「Aというクラスを実装する」という`Issue`があった場合、`Issue`は「Aクラスの実装」となっています。  
ですので、ブランチ名は「add_class_for_A」や「implement_class_A」のようなものにするとわかりやすいでしょう。

またブランチを切る場合は、事前に`master`ブランチなどを`pull`しておきましょう。最新の`master`ブランチのコミットを取り込んでおくことでコンフリクトなどを回避しやすくなります。

さらに、`GitHub`や`GitLab`を使用している場合は`Issue`の番号を「add_class_for_A_#1」のようにブランチ名に追加しても良いでしょう。  
`Issue`の番号を追加しておくことで、作成したブランチを`push`した段階で自動的に`Issue`と紐づけを行ってくれます。

### (3) 実装を行う

次に、`Issue`の内容を解消するコードを実装していきます。  
できるだけ小さな単位でのコミットで実装していくと実装の流れが追いやすくなります。ですのでできるだけ小さな粒度でコミットします。

また`GitHub`や`GitLab`などを使用しているケースでは、先ほどのブランチ名と同様にコミットメッセージに「add class A #1」のように`Issue`の番号を追加しておきましょう。  
すると自動的に`Issue`に紐づけられます。  
後から実装の流れを確認することが簡単になりますので、できるだけ`Issue`の番号をコミットメッセージに追加していきましょう。

### (4) ブランチをリモートリポジトリへプッシュ

`(3) 実装を行う`が完了した後は、手元のブランチをリモートリポジトリへとプッシュします。  
この時、同様の名前のブランチなどがリモートリポジトリ側に無いかチェックしておくとよいでしょう。

状況にもよりますが同じようなブランチを作成しているケースもあります。その場合、

### (4) プルリクエストを作成し、レビュー

`(3)実装を行う`での作業が完了した後は、手元のブランチをリモートリポジトリにプッシュします。

`GitHub`などのサービスを利用している場合は、`プルリクエスト`という別ブランチの内容を指定のブランチに取り込むという機能が使えます。  
`プルリクエスト`の便利なところは、マージ元とマージ先のブランチ間でのコンフリクトのチェックなどを自動的に行ってくれる点です。  
その為、マージ後にファイルがコンフリクトしているのを修正するなどの手間が省けます。

また、`GitHub`や`GitLab`では`CI(継続的インテグレーション)`を使用することができ、作成した`プルリクエスト`の内容に対して自動的にテストを行うこともできます。  
その為、ソースコード自体の品質向上も見込めます。

`プルリクエスト`作成時に、指定のユーザーに対してレビューを要求することもできます。これによりコードを実装した人以外のチェックが入り、事前にミスを見つけることができます。

### (5) マージ

`(4) プルリクエストを作成し、レビュー`が終了したあとは、`プルリクエスト`内にある`マージ`ボタンをクリックします。  
これにより自動的に`master`ブランチなどの主流ブランチに作成した機能がマージされます。






















