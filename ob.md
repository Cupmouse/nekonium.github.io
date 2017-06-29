# Nekonium Open Beta試掘手順書

## 参加方法

以下の要件に該当する方が参加できます。
参加者には、個別にダウンロードURLをご案内します。

* 開発関係者と面識があること。
* 自力でググるなどしてマイニングまでたどり着ける技術のあること。
* Windows64ビット版を利用できること。
* オープンベータ期間中のハッシュレート制限や、採掘停止指示に従えること。
* Ethereumウォレットを同一PCに保持していないこと（NekoniumはEthereumのフォークのため、Ethereumウォレットに何らかの影響を及ぼす可能性を否定できません。Ethereumウォレットやgethをセットアップしている場合は必ずバックアップを取ってください。）

非技術者の方は参加できませんので、一般公開までお待ちください。


## マイニング方法

go-nekoniumを入手してください。Windowsはバイナリがあります。
<s>その他のOSはソースからコンパイルしてください。</s>


1. コマンドラインからgnekoniumを起動します。
````
$gnekonium console
````
2. ネットワークに接続するまでの間しばらくおまちください。net変数で接続ピア数がわかります。
````
> net
{
  listening: true,
  peerCount: 2,
  version: "1",
  getListening: function(callback),
  getPeerCount: function(callback),
  getVersion: function(callback)
}
````

3. アカウントを作成します。アカウントを作成するためにはパスワードが必要です。
パスワードを忘れるとアカウントにアクセスできなくなります。大切に保管してください。
````
> personal.newAccount()
````

4. 作成したアカウントの一覧はaccounts変数で見ることができます。
````
> eth.accounts
````
5. miner.start関数で採掘ができます。引数はスレッド数です。
````
>miner.steart(2)
````
6. 停止はstop関数を使います。
````
>miner.stop()
````
7. 現在のバランスを見るにはgetBalance関数を使います。単位を整形するためにfromWei関数を使います。
````
> web3.fromWei(eth.getBalance(eth.accounts[5]),"nuko")
100.968372
````
その他コマンドは参考リンクを調べてください。

<b>OpenBetaが終了するまでの間、もしくは5万Blockを採掘するまでの間は、CPUマイニング以外を行わないでください。</b>

## 参考リンク

リンク先はEthereumの説明ですが、Nekoniumでも同じように操作ができます。gethをgnekoniumに読み替えてください。

* https://book.ethereum-jp.net/what_is_ethereum/
* https://book.ethereum-jp.net/first_use/mining_ether.html


# ウォレットの利用

ウォレットアプリケーションMistWalletを利用できます。Windowsはバイナリがありますが、その他のOSはソースからコンパイルしてください。コンパイル手順はEthereumのMistと同じです。
オープンベータ期間中はオートアップデートが無効です。先にgnekoniumを起動しておいてください。

https://github.com/nekonium/mist/releases


* MistWallet起動の前に、まずgnekoniumを起動しておいてください。
* Mistを起動します。Windowsの場合はスタートメニューから起動できると思います。
* Mistの送受信機能を試すことができます。使い方はEthereum版と同じです。



参考リンク
リンク先はEthereumの説明ですが、Nekoniumでも同じように操作ができます。
* http://www.intellilink.co.jp/article/column/ethereum01.html



OpenBeta終了後もブロックチェーンのデータは保持されます。　得られたNekoniumはそのまま所有していただいて構いません。


