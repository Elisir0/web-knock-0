## 課題06：ブランチの作成と切り替え

### やったこと

- `git switch -c develop` コマンドを使用し，新しいブランチ（develop）を作成して切り替えた．
- 該当ブランチ上でファイルを修正し，コミットを行った．

### 実行結果
```
git switch -c develop
Switched to a new branch 'develop'

git add .

git commit -m "developブランチでの変更(develop)を追加"
[develop 0860324] developブランチでの変更(develop)を追加
 1 file changed, 1 insertion(+), 1 deletion(-)

git branch
* develop
  main

git switch main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

git  branch
  develop
* main
```