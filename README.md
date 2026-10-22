# web-knock-0

- 名前：H.Y
- グループ：A
- テーマ：0：GitとGitHubの基本・演習

## 担当課題

| 課題番号 | 課題名 | 場所 |
|:--:|:--|:--|
| 03 | ローカルリポジトリとGitHubリポジトリの連携 | [03/](03/) |
| 06 | ブランチの作成と切り替え | [06/](06/) |

---

## 課題03：ローカルリポジトリとGitHubリポジトリの連携

### やったこと

以下のコマンドを実行した．
```
git remote add origin https://github.com/Elisir0/web-knock-0.git
git remote -v
```

### 実行結果

```
origin  https://github.com/Elisir0/web-knock-0.git (fetch)
origin  https://github.com/Elisir0/web-knock-0.git (push)
```

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


```