## Bitzeny core既知の問題の解決

#同期が始まらない
現時点での公式サイト(bitzeny.org)よりダウンロードできるBitzeny coreには、ブロックチェーンの同期が始まらない。という問題が確認されています。
この問題の解決法は以下の通りです。
コマンドの実行時にはBitzeny coreを終了しておいてください。

---
Windowsの方はWin + Rキーを押して、名前欄に以下のコマンドをコピー&ペーストしてください。
`bitsadmin.exe /TRANSFER seedget http://http://153.126.187.209/seedlist.txt C:\temp\seedlist.txt && type C:\temp\seedlist.txt >> %AppData%bitzeny\bitzeny.conf`
---
Linux,Macの方は端末で以下のコマンドを実行してください
`wget http://http://153.126.187.209/seedlist.txt && cat seedlist.txt >> $HOME/.bitzeny/bitzeny.conf && rm seedlist.txt`
---

以上のコマンドを実行したあと、Bitzeny coreを起動すると、同期が開始されます。
同期の開始、及び完了までには、CPUの性能にもよりますが、数時間から数日かかります。
できるだけPCの電源を付けっぱなしにしておくことをおすすめします。