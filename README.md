

## Step 1: VSCodeを使ったクローンの作成

インターネット上に存在するGitHubのリポジトリデータをローカルの端末にダウンロードして修正することも可能です。
そうしておけば、新幹線や飛行機で出張している状況でもオフライン且つ高速な作業環境が実現できます。実験的な変更を加える場合やバックアップを取得したい場合にも役立ちます。

### :keyboard: VSCodeのインストールとブランチの切替

今回はVSCodeを使ってローカルにリモートリポジトリのクローンを作成するため、事前に[VSCodeをインストール](https://azure.microsoft.com/ja-jp/products/visual-studio-code)します(インストール済みの場合はスキップ)。

1. VSCodeのインストールが完了したら、[Git](https://git-scm.com/)をインストールします。VSCodeの拡張機能である[Remote Explorer](https://marketplace.visualstudio.com/items?itemName=ms-vscode.remote-explorer)、[GitHub Actions](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-github-actions)、[GitGraph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph)、[GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)もインストールします。
1. 次にGitHubの画面で`<>Code`のボタンを押下し、表示されるHTTPSのURLをコピーします(コピーアイコンを押す)。
1. VSCode画面左のアクティビティバー`「リモートエクスプローラー」`を押下し、リモートリポジトリの追加`+`を押します。
1. 上部の検索バーに`「GitHubからリポジトリを開く」`を押し、先ほどコピーしたURLを入力し実行します。VSCode上にリモートリポジトリが表示されます。
1. デフォルトで`main`ブランチが選択されています。後の手順のためにブランチの`resume.md`の内容をメモします(notepadなどでローカルにコピー)。
1. [最初の手順](https://github.com/kuboctopus/dodge-merge-conflict/blob/main/README.md)で作成した`my-resume`ブランチに切り替える必要があります。VSCodeの画面の左下に表示される`main`を押下し、`my-resume`を選択します。
1. `my-resume`ブランチの`resume.md`の内容を確認し、先の手順でメモした内容(5行目)と異なることを確認します。このまま`my-resume`ブランチを`main`ブランチへマージするとマージコンフリクトが発生します。

**_マージコンフリクトって何_?**: **マージコンフリクト** は、2つの異なるブランチで同じファイルの同じ箇所が修正されている場合に発生します。

### :keyboard: ローカル端末へのクローンの作成

作成したブランチをローカルの端末に保存します。

1. VSCodeの画面左下にある`「>< GitHub」`を押下し、`「新しいローカルクローンで作業を続ける」`を押します。
1. `「はい、作業中の変更を使って続行します」`を選択します。必要に応じてGitHubの認証を行い、ローカル端末のリポジトリの任意の保存先を選択します。
1. `「複製したリポジトリを開きますか? または現在のワークスペースに追加しますか?」`というメッセージダイアログが表示されるので、`「開く」`ボタンを押下します。
1. エクスプローラーで指定した保存先にリポジトリに含まれるフォルダとファイル群(dodge-merge-conflict 以下)が保存されていることを確認します。

以上でローカル端末へのクローン作成は完了します。

## Step 2: マージとブランチのファイルの修正

先ほどローカルに複製したリポジトリのブランチ`my-resume`に対し、リモートリポジトリの`main`ブランチをマージします。
次に`my-resume`ブランチに含まれるファイルを更新し、`main`ブランチに再度マージします。

### :keyboard: リモートブランチのマージ

`main`ブランチのデータを`my-resume`ブランチへマージします。

1. VSCode のメニューから`<ターミナル>-<新しいターミナル>`を押下し、ターミナルを開きます。
1. ターミナルの画面上で、クローンしたGitのフォルダがカレントディレクトリになっていることを確認し、`git branch`を実行すると、`my-resume`ブランチが表示されます(`my-resume`ブランチが表示されない場合は、`git switch my-resume`を実行し切り替えます)。
1. `git merge origin/main`を実行します。vim等のエディタが起動しますので、メッセージを入力し保存、マージを行います。このマージにより、`my-resume`ブランチの`resume.md`が更新され、`main`と`my-resume`ブランチの`resume.md`の記載内容が同じになりコンフリクトが回避された形になります。

### :keyboard: ブランチのファイルの修正

1. VSCodeの画面左下を確認し、選択中のブランチが`my-resume`になっていることを改めて確認します。
1. アクティビティバーのエクスプローラーを選択し、`resume.md`を押下します。ファイルの内容が表示されますので、本来の修正内容に正すために、文字列`Jobs`を`Jobs History`に変更し保存します。
1. VSCodeの画面左側のアクティビティバーの`ソース管理`を押下し、変更メッセージに任意の文字列を入力、`コミット`ボタンを押下します。
1. ステージの確認メッセージが表示された場合は、`はい`を押します。更に、ボタンのテキストが`変更の同期`に変更されたら、押下します。

### :keyboard: プルリクエスト

1. GitHubの画面を表示し、`Pull requests`のリンクを押します。
1. `New pull request`アイコンを押下します。
1. ベースブランチを`main`、ヘッドブランチを`my-resume`に設定します。
1. 画面をスクロールし、修正内容を確認、任意のコメントや説明を入力、`Create pull request`を押下します。

約20秒待ってから、このページ(あなたが指示を受けているページ)を更新してください。GitHub Actionsが自動的に次のステップに更新されます。


