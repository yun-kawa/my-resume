# マージコンフリクトを回避する

_マージコンフリクトを回避する方法を*VSCode*を用いて学びます。_

## 概要

マージコンフリクトは起こり得るものですが、工夫することで避けることが可能です。
このコースではマージコンフリクトを回避する一連の流れをGitHubとVSCodeを用いて学びます。

- 学習内容：VSCodeを利用したマージコンフリクトの回避方法について。
- 作成するもの: マークダウンで書かれた要約ファイル`resume.md`を使用します。
- 前提条件：[resolve-merge-conflict-with-vscode](https://github.com/kuboctopus/resolve-merge-conflict-with-vscode)の内容を理解していることをお勧めします
- 所用時間: このコースの所要時間は 30 分未満です。

このコースではVSCodeを利用して以下を学びます:

1. リモートリポジトリのコードをローカル端末に複製、コンフリクトが発生しないように内容を修正し、プッシュする。
1. Pull requestを作成する。
1. Pull requestをMergeする

> [!NOTE]
> Git、GitHub初学者は[こちら](https://github.com/kuboctopus/dodge-merge-conflict/blob/main/for_newbie.md)へ


## このコースの始め方

<!-- For start course, run in JavaScript:
'https://github.com/new?' + new URLSearchParams({
  template_owner: 'kuboctopus',
  template_name: 'dodge-merge-conflict',
  owner: '@me',
  name: 'my-resume',
  description: 'My clone repository',
  visibility: 'public',
}).toString()
-->

[![start-course](https://user-images.githubusercontent.com/1221423/235727646-4a590299-ffe5-480d-8cd5-8194ea184546.svg)](https://github.com/new?template_owner=kuboctopus&template_name=dodge-merge-conflict&owner=%40me&name=my-resume&description=My+clone+repository&visibility=public)

1. **Start cource**を**右クリック**し、新しいタブでリンクを開きます。
2. 新しいタブでリポジトリを作成します。
   - 個人下にリポジトリを作成してください(組織下に作成すると課金される可能性があるため)
   - リポジトリの公開設定はパブリックにしてください(プライベートだとGitHub Actionsで課金されます)
3. 新しいリポジトリが作成されて20秒後にページを更新してください。ステップごとの説明がREADMEに表示されます。
