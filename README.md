GPXeditは新しいバージョンをGPXedit2として https://github.com/guchi999/GPXedit2 に上げていますので、そちらをお使いください。

このバージョンのプログラムは現在のところ参考として保存しており、いずれ消去する予定です。
 
 
 ブラウザ上で動く、GPXファイルを編集するツールです。
　ルートの新規作成、分割、部分除去、結合、時間変更、名前変更、逆ルート変換、トラックポイントの移動/消去、間引き、削除、追加など、GPXファイルの編集に必要な事はほぼ全てできます。
　ヤマケイオンラインのログファイルやGoogle Mapの経路を変換したGPXファイルのような、時間と標高データの無いファイルにも対応しています。元の GPXファイルは読み取るだけで何の変更もしません。

　特別なソフトをインストールする必要はなく、通常使っているブラウザで動きます。ホームページと同様にブックマークして呼び出す事もできます。

　Chrome、Firefox、Edgeで動作を確認しています。IEでは動きません。
　Safariでは時間入力の互換性の問題が多少あるようですが、Chrome や Firefox を使っているなら MACでも動くと思われます。

　地図表示にLeafletのライブラリと地理院の地図データにアクセスしますので、ネットに繋がっていないと動きません。



１．使い方

　GPXファイルの読み込みは、ファイルを画面上にドラッグ&ドロップするかファイル選択ボタンで行います。
　ファイルを読み込むと地図がルートの周辺に変わり、ルートが赤線で示されます。ルートの終端にあるマゼンタのドットは開始点、シアンのドットが終了点を示します。
　ルートが幾つかのトラックで構成されているときは、開始点/終了点のマーカーも各トラックに表示されますが、開始点と終了点が重なってどちらかが見えない事もあります。

　読み込むルートの数に制約はありません。[読み込みルート]の下に読み込んだルートのリストが表示されます。

　既に同じ名前のルートが読み込まれている場合、ルートが違っても名前が同じファイルは読み込めません。どちらかのルートの名前を変更してください。（入力ファイル名を変更する、もしくは読み込んでいるルートの名前を「名前変更」で変更）
　名前が異なり同じ軌跡を持つルートの場合は、読み込みはできますが軌跡が重なるため後から読み込んだルートしか選択できません。トラック編集で軌跡を一部変更して軌跡の異なる部分を作れば選択できます。

　ルートの編集は目的の作業を選んでから、地図上の目的のルートをクリックして選択し、必要な作業/設定を行なった後に確定するという流れになります。
　編集は読み込んだデータで行われ、元のGPXファイルには何もしません。

＊各変更を確定する前に「作業選択」を変更するとリセットされて、それまでの作業が消えますのでご注意ください。

　なお、GPXファイルに含まれるウェイポイント（＜wpt＞要素）やその他の情報（＜extensions＞要素等）は最初のトラック（＜trk＞要素）の前まではヘッダーとして保持され、トラックやトラックポイント（＜trkpt＞要素）に速度やその他の情報があっても省かれます。
（編集後は基本的に必要な緯度、経度、標高、時間のデータだけになります。）

　時間と標高データの無いファイルにも対応していますが、ほとんどの編集作業は時間データを基準にしているため、時間データが無い場合は逆ルート変換とルート/トラックの名前変更しかできません。
「時間変更」で時間を設定すれば通常のルートとして編集できます。

　標高データが無い場合は国土地理院のサーバーからデータをダウンロードして設定しますが、ポイント数の多いルートでは標高データ取得に時間がかかるため、通信環境等によっては上手く設定されない事があります。
　その場合には、読み込んだルートを削除して再度読み込むと、途中までの標高データは保持されていますので次は短い時間で設定されます。



２．各作業の説明


（1）ルート作成

　マウスをクリックしたポイントにマーカが表示され、所要ルートに沿って順次クリックして行くと、マーカーが仮のルートを示す青いラインで繋がって行きます。
（クリックポイントの標高データを地理院のサーバーからダウンロードしているため、反応が0.1秒程度遅れる事があります。）

　各マーカーはドラッグして移動でき、不要なマーカは再度クリックすれば消去できます。
マーカーとマーカーの間のライン上に新たにマーカーを追加することはできませんが、トラック編集では追加できますので、最初は粗くルートを作成してトラック編集で詳細を決めるという使い方もできます。

　ルートが出来たら、ルートとトラックの名前、スタートとゴールの時間を設定してルートを「確定」ボタンを押すとルートが赤線になります。
　デフォルトで表示されている名前は適宜変更してください。（以下、他の作業でも同じ）トラック名はブランクにしても大丈夫ですがルート名は必須です。[読み込みルート] のリストに無い名前にしてください。

＊「確定」を押す前に作業選択を変更すると、それまでの作業は全て消えますのでご注意ください。

　時間設定は日付を跨いで設定できませんので、数日に渡るルートを作成する時は日付毎にルートを作成して後でルートを結合してください。
　逆に全行程のルートを作成して時間は適当に設定しておき、後でそのルートを分割してそれぞれの日時を変えるという方法もあります。


（2）トラック編集

　目的のルート/トラックをクリックすると、各トラックポイントにマーカが置かれ仮のルート(青ライン)が表示されます。そのマーカーの移動、削除、追加でトラックを編集します。
　編集する範囲は、ルートが1つのトラックだけのときはルート全体、複数のトラックで構成されているときはクリックしたトラックのみになります。

　編集する範囲のトラックポイントが多いと動作が著しく遅くなりますので、トラックポイントの多いルートは最大で1000ポイントくらいを目安に分割し、編集後に結合してください。
　ポイント数はトラック編集でラインをクリックすると表示されますが、ポイントが多いと表示されるまでに時間がかかります。
　作業選択の「ポイント間引き」でもポイント数は表示されますので、作業を始める前にそちらで確認しておくと良いです。

　マーカーを移動や削除すると、それをつなぐ仮のルートも変わります。元ルートの赤いラインは、「確定」ボタンを押すまでそのまま残っています。
　始点と終点も削除できますが、そのポイントの時間データが失われますので、それを考慮する必要があります。

　マーカの追加は青ラインをクリックすると、その場所に追加されます。ライン以外の場所にマーカは追加できませんので、ライン上に追加して移動してください。
　追加したマーカーの標高データは地理院のサーバーからダウンロードされ、時間データは前後のマーカー間の時間が標高差と距離に応じて配分された値になります。


（3）ルート分割

　ルート上の分割したい地点をクリックすると、その点の一番近いトラックポイントに分割ポイントのマーカーが付きます。マーカーのキャンセルは再度そのマーカーをクリックします。
　分割は開始点から分割ポイントの前までと、分割ポイントを含んで終了点までに分けられます。前半と後半のルート名を決めて確定してください。


（4）ルート部分削除

　マーカーを2つ設定して削除する部分を選び、削除する部分を決めて「確定」すればその部分が削除されます。始点からマーカーまで、マーカーから終点までを削除する場合は、マーカーは1つでも構いません。
　マーカーの設置に順序はなく、キャンセルはそのマーカーをクリックします。


（5）ルート結合

　ルートを2つ選択し、時系列に結合します。選択したトラックを再度クリックすれば、選択をキャンセルできます。
　ルートに複数のトラックが含まれている場合、全てのトラックを統合してトラックを一つに結合するモードと、トラックを残して結合するモードがあります。
　結合後は、結合前のルートは削除されます。


＊　結合後のルート名に、結合前と同じ名前を使うと正常に動作しなくなりますのでご注意ください。
　同じ名前にしたいときは、1文字でも変えた名前で結合し、そのあとで名前を変更してください。

　ルートの複数トラックを統合する事だけもできます。1つだけルートを選択し「トラックを統合して結合」で結合してください。この場合、結合後のルート名は設定する必要はなく、設定してもルート名は変わりません。


（6）ポイント間引き

　選択したルートのトラックポイントを指定した間隔(m)で間引きます。
　間引く間隔はトラックポイント間の距離を積算して判断しているため正確ではなく、多少の誤差を含みます。

（7）時間変更

　選択したルートの始点から終点までの各ポイントの時間を距離と標高差に応じて配分した時間に置き換えます。
　日付を跨いだ設定はできませんので、その場合は日付毎にルートを分割し個別に設定してください。
　また、複数のトラックがあるルートで、トラック毎に時間を設定したい場合も同様に分割して行ってください。
　時間配分の比率はソースファイルの定数を変更すれば変えられます。(カスタマイズを参照してください）


（8）名前変更

　ルートとトラックの名前を変更します。
　ルートを選択すると現在のルート名とトラック名が表示されます。それを変更してください。
　トラック名は＜name＞の後に所要の名前(半角、全角いずれも可)、＜number＞の後に数字(半角)を付けます。
　トラック名、numberはブランクにできますが、その場合にも＜name＞＜number＞の形にしてください。


（9）逆ルート変換

　選択したルートの始点と終点を反転します。
　時間データが失われますので、変換後に時間変更で再設定してください。


（10）ルート削除

　選択したルートを、地図と読み込みリストからから削除します。
　確認等は無く、ルートをクリックすると即削除されますので、編集したルートを保存してない時には注意してください。
　また、ファイルを読み込んだ時にルート削除になっていると、作業選択を変える前にルートをクリックすると削除されますので、それも注意してください。


（11）ポイント情報(時間変更)

　ルートをクリックした点に一番近いトラックポイントの情報が示されます。indexはトラックでの0から始まる順序です。
　そのポイントの時間も変更できますが、前後のポイントとの時間の関係がずれるとGPXファイルを使うアプリによってはルートが乱れますので注意してください。


（12）ファイル出力

　出力するルートを選択してファイル名を決めて保存すると、ダウンロードフォルダにGPXファイルが出力されます。


（13）地図ジャンプ

　表示される山域をクリックすると地図がその山域に移動し、縮尺も変わります。
　山域はソースファイルの定数を変更することで変えられます。(カスタマイズを参照してください）


（14）リストジャンプ

　複数のルートを読み込んでいる時、[読み込みルート]に示されているルート名をダブルクリックすると、そのルート全体が表示できる縮尺で、その場所にジャンプします。
　ただし、ダブルクリックして選択できる文字列の範囲がブラウザによって異なるため、同じ文字が使われているルートがある場合、所要の場所にジャンプしない事があります。異なる文字をクリックするようにしてください。


3．カスタマイズ

　メモ帳等のテキストエディタでGpxEdit.htmを開き、ソースコードの定数を変えれば、下記の2つはカスタマイズできます。
　値を変更して保存するときは、文字コードをUTF8(BOMなし)で保存してください。

（1）時間変更の時間配分

　ソースコードの8行目からの傾斜に対する速度比、及び傾斜レンジの閾値を変えれば、ルート作成や時間変更での時間配分も変わります。
　この値を自分の速度に合わせた値にすると、欠落したGPSログを補完する時などに、より自然な時間配分にできます。


（2）地図ジャンプ

　地図ジャンプのジャンプ先は、ソースコード17行目からのjumpListの配列の値を変更して変えます。
　増やす場合ことも減らすこともできます。増やす場合は定数を追加し、減らす場合は不要な定数を削除してください。変更する際には閉じカッコとセミコロン（ ]; ）を消さないように注意してださい。
　ジャンプ先定数の記述フォーマットは、ジャンプ先名称(適当な名前を付けます)、地図縮尺値、ジャンプ先緯度経度をスラッシュ(/)で区切り、それをダブルクォーテーションで囲ってカンマで区切ったものです。(改行はしても、しなくてもOKです）

　例：
　　"奥多摩/12/35.779436/139.127785",

　縮尺値や緯度経度は国土地理院の地図( https://maps.gsi.go.jp/ )で目的の場所を表示したとき、アドレス欄に出ているurlで、#に続く3つの数値をコピーすればジャンプ先も同じ場所とスケールになります。

　国土地理院地図のurlの例：
	https://maps.gsi.go.jp/#13/35.711117/137.821426/&base=std&ls=std&disp=1&vs=c1j0h0k0l0u0t0z0r0s0m0f1



3．リセット

　入手し得えた範囲のGPSファイルで動作チェックしていますが、GPSファイルの書式によっては予期しない動作になる可能性も残っています。例えば、ルートは表示されても読み込みリストに出てこない、逆にリストにはあっても地図に表示されない、編集作業ができない等。
　そのような場合には、ブラウザでリロード(再読み込み)するか、タブを閉じて再度立ち上げてください。



4. 履歴
V1.0 2021/09/01
　初版リリース
V1.1 2021/09/11
　同一時間のトラックポイントが複数あるgpxファイルを分割すると動作異常になる問題を解消。
V1.2 2021/09/30
　同じtrkptが複数あるgpxファイルは、重複するtrkptを読み込み時にスキップするように変更。

