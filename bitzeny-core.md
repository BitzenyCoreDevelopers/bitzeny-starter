## Bitzeny core既知の問題の解決

# 同期が始まらない&遅い
現時点での公式サイト(bitzeny.org)よりダウンロードできるBitzeny coreには、ブロックチェーンの同期が始まらない＆遅い、という問題が確認されています。
この問題の解決法は以下の通りです。
コマンドの実行時にはBitzeny coreを終了しておいてください。

----
Windowsの方はWin + Rキーを押して、名前欄に以下のコマンドをコピー&ペーストしてください。（約1.3GBのファイルをダウンロードするので、時間がかかります。）

`mkdir C:\temp & powershell -Command "Invoke-WebRequest -Uri http://153.126.187.209/seedlist.txt -OutFile C:\temp\seedlist.txt" && powershell -Command "Invoke-WebRequest -Uri http://153.126.187.209/bootstrap20171210.dat -OutFile C:\temp\bootstrap.bat" && type C:\temp\seedlist.txt >> %AppData%\bitzeny\bitzeny.conf && move C:\temp\bootstrap.dat %AppData%\bitzeny\bootstrap.dat`

----
Linux,Macの方は端末で以下のコマンドを実行してください

`wget http://153.126.187.209/seedlist.txt wget http://153.126.187.209/bootstrap20171210.dat && cat seedlist.txt >> $HOME/.bitzeny/bitzeny.conf &&mv bootstrap20171210.dat $HOME/.bitzeny/bootstrap.dat && rm seedlist.txt && bootstrap20171210.dat`

----

以上のコマンドを実行したあと、Bitzeny coreを起動すると、同期が開始されます。
同期の開始、及び完了までには、CPUの性能にもよりますが、数時間から数日かかります。
できるだけPCの電源を付けっぱなしにしておくことをおすすめします。

***ブロックチェーンの同期が完了するまではマイニングを行わないでください。***
