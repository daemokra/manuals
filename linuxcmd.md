# ユーザ作成
```
adduser <username>
```
↑ホームディレクトリも作られるし、ユーザも追加される

```
useradd <username>
```
↑こっちだとホームディレクトリが作られない

# ユーザ追加したときのhomeディレクトリの雛形
`/etc/skel`に入ってる。

```
drwxr-xr-x  2 root root 4096  3月 23 22:49 ./
drwxr-xr-x 99 root root 4096  3月 23 23:01 ../
-rw-r--r--  1 root root  220  2月 25  2020 .bash_logout
-rw-r--r--  1 root root 4022  3月 23 22:49 .bashrc
-rw-r--r--  1 root root  807  2月 25  2020 .profile
```
↑Ubuntuのデフォ

ここに入ってるのが、`useradd`したときの自動的にコピーされる。
`.ssh`フォルダとかは作っておいてもいいかも。
あとプロンプトを変えてる人は`.bashrc`を変更しておけばユーザ追加時のプロンプトを変更することができる。

# ユーザをグループに追加
```
gpasswd -a <username> <groupname>
```
| 短いオプション | 長いオプション              | 意味                                         |
|----------  |-----------------------|--------------------------------------         |
| -a ユーザー  | --add ユーザー            | ユーザーをグループに所属させる                     |
| -d ユーザー  | --delete ユーザー         | ユーザーをグループのメンバーから外す                 |
| -r         | --delete-password       | グループのパスワードを削除する                     |
| -R         | --restrict              | グループへのアクセスをメンバーのみに制限す             |
| -A ユーザー  | --administrators ユーザー | グループの管理者を設定する（ユーザーは複数指定可能）     |
| -M ユーザー  | --members ユーザー        | メンバーのリストを設定する（ユーザーは複数指定可能）    |

>【※】複数のオプションは同時に使用できません（「-A」と「-M」オプションの組み合わせのみ可能）
>【※】オプションを指定しない場合はグループのパスワード設定（［Enter］キー2回で終了）
(参考)https://www.atmarkit.co.jp/ait/articles/1612/12/news016.html


# グループ一覧を表示
```
cat /etc/group
```

結果
```
sudo:x:27:kazuki,puchiko,docker
```

グループ名:x(暗号化されたPW):グループID(GID):所属してるユーザアカウントリスト

## 削除
```
sudo gpasswd -d <username> <groupname>
```





# .bashrcについて

## 色

| 色     | カラーコード  | bashで指定する数値 |
|--------|---------|-----------------|
| black  | #000000 | 30              |
| red    | #ff0000 | 31              |
| green  | #00ff00 | 32              |
| yellow | #ffff00 | 33              |
| blue   | #0000ff | 34              |
| purple | #ff00ff | 35              |
| cyan   | #00ffff | 36              |
| white  | #ffffff | 37              |


# apt系コマンド
- インストールしてるパッケージを一覧化したい  
`sudo dpkg -l`



# service系

## リスト表示
`service --status-all`




# 設定場所系

## nftable
/etc/nftables.conf


# 音うるさい
echo "set visualbell t_vb=" >> ~/.vimrc
echo "set bell-style none" >> ~/.inputrc

## vim
:echo &filetype
今開いてるファイルがどのファイルタイプか表示する



