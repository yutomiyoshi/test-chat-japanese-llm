### SSHでRunPodのコンテナに接続する

1. SSHキー生成をローカルPCで実行

コマンドはRunPodのConnect > Configure Public Keyからコピペ。


```
ssh-keygen -t ed****** -C "****@***.***"
```

2. ローカルPCの公開鍵をコピー

ローカルPCでディレクトリを確認

```
ls ~/.ssh
```

SSHキー生成コマンドで生成されたファイル名のうち、末尾に.pubがついているものを確認

```
cat ~/.ssh/*****.pub
```

一文で公開鍵が表現されているので全コピー（ctrl + shift + c）

```
# まるごと一行コピー
ssh-key: *****************
```

3. リモートPCに公開鍵を登録

認証キーのファイルに書き込み

```
echo "(先程コピーした一文)" >> ~/.ssh/authorized_keys
```

4. vscodeのコマンドパレットからremote-ssh: connect・・・で接続

(拡張機能REMOTE　SSHが必要)

sshコマンドでは、RunPodのConnect > Connection Options > SSH over exposed TCP: (Supports SCP & SFTP)のコマンドをコピーして貼り付け
