# fAPPassport

## 実行方法
1. ソースコードをダウンロードしてソースコードをgithubに上げる
2. serviceworker.jsの1行目のORIGIN変数のパスの「fapPasspor3」を自分のGitHubのリポジトリ名に変更する. 
3. github公開ページを使用しアプリケーションを公開し、アクセスする

公開ページの使用方法
 githubのリポジトリ→setting→GitHub Pages→Sourceをmaster/branchに変更

## グラフの計測方法
自分で計測する場合
1. アプリケーションの検診予約を複数し, 表示速度を計測する.
2. perfomance.nowメソッドを使い計測した.
3. 複数を一気に登録するには, appointment.htmlの
 
>```
<!--
    <br />
    <button class="btn btn-primary btn-lg btn-block" onclick="location.href='menu.html'">戻る</button>
    <br>
    <input type="text" class="form-control" placeholder="回数" id="count">
    <br>
    <button class="btn btn-primary btn-lg btn-block" onclick="regCount()">データ登録</button>
    <br>
-->```

のコメントアウトを外す. 1件目の登録は上記のデータ登録ボタンではなく, 登録ボタンでデータを登録してください.
また, checkAppointment.jsの17,21行目のコメントアウトを外す.

## グラフの計測
https://ecls.info.kindai.ac.jp:8443/gitbucket/1610370187/thesis

上記のURLのgpiかdatを用いる

>gnuplotを用いてグラフの作成 

>$ load "plot.gpi"

>上記のコマンドで表示できるはず

できなかった場合下記で試して

$ plot "AveSpeedMac.dat" with linespoint ps 2 title "Mac", "AveSpeedAndroid.dat" with linespoint lt 1 pt 4 ps 2 title "Android", "AveSpeediOS.dat" with linespoints lt 1 pt 6 ps 2 title "iOS"
