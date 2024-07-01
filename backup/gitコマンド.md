```git
現在のフォルダをGitリポジトリとして初期化します。  
　　`git init`

リモートGitリポジトリをローカルにクローンします。  
　　`git clone <URL>`

ファイルをステージングエリアに追加します。  
　　`git add <file>`

すべてのファイルをステージングエリアに追加します。  
　　`git add .`

ステージングエリアの変更をローカルリポジトリにコミットし、メッセージを追加します。  
　　`git commit -m "<message>"`

ステージングエリアをスキップし、追跡されているすべてのファイルの変更を直接ローカルリポジトリにコミットし、メッセージを追加します。  
　　`git commit -a -m "<message>"`

ローカルブランチを一覧表示します。  
　　`git branch`

新しいブランチを作成します。  
　　`git branch <name>`

指定されたブランチに切り替えます。  
　　`git checkout <name>`

指定されたブランチを現在のブランチにマージします。  
　　`git merge <name>`

マージ操作を中止します。  
　　`git merge --abort`

リモートリポジトリを追加します。  
　　`git remote add <name> <URL>`

リモートリポジトリを一覧表示します。  
　　`git remote -v`

ローカルブランチをリモートリポジトリにプッシュします。  
　　`git push <remote> <branch>`

リモートブランチをローカルリポジトリにプルします。  
　　`git pull <remote> <branch>`

リモートリポジトリから最新のコミットを取得しますが、現在のブランチにマージしません。  
　　`git fetch <remote>`

リモートリポジトリのmainブランチを取得し、ローカルに新しいブランチを作成します。  
　　`git fetch origin main:main-local`

現在のリポジトリの状態を確認します。  
　　`git status`

コミット履歴を確認します。  
　　`git log`

簡略化されたコミット履歴を確認します。  
　　`git log --oneline`

コミット履歴をグラフィカルに表示します。  
　　`git log --graph`

ファイルの変更を確認します。  
　　`git diff <file>`

Reflogを確認します。  
　　`git reflog`

ファイルの変更を取り消します。  
　　`git checkout -- <file>`

すべてのファイルの変更を取り消します。  
　　`git checkout -- .`

ステージングエリアの変更を取り消し、ワークツリーに戻します。  
　　`git reset HEAD <file>`

ステージングエリアのすべての変更を取り消します。  
　　`git reset HEAD .`

指定されたコミットまでの変更を取り消します。  
　　`git reset --hard <commit>`

強制的にリモートブランチにプッシュします。  
　　`git push -f origin <branch>`

ファイルをステージングエリアに追加します。  
　　`git add <file>`

最新のコミットを修正します。  
　　`git commit --amend`
```