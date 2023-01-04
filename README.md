このバージョンはα版であり、まだデバッグ中です。
現在のバージョンを https://github.com/guchi999/GPXedit2 に上げていますので、そちらをお使いください。
 
 ----------------------------------------------------------------

GPXファイルを編集するツールです。 ブラウザ上で動き、特別なプログラムをインストールする必要はありません。

乱れた GPS ログの修正、GPS 機器へ入力する計画ルートの作成に使えます。 Google Map でエクスポートした KML ファイルも読込めます。

出来ることは下記の通りです。

　・ルート(トラック)の新規作成

　・ルートの編集（トラックポイントの移動/削除/追加によって経路を変更）

　・分割

　・部分削除

　・結合（２つのルートを結合、複数のトラックに分かれているルートを１つのトラックにする）

　・ルート（ログ）の時間変更

　・ルートやトラックの名前変更

　・逆ルート変換

　・標高値を地理院地図の標高、あるいは任意の値に置き換える

　・トラックポイント間引き

　・ウェイポイントの編集

ダウンロードした zip ファイルを展開し、全てのファイルを同じフォルダに置いて GpxEdit2.htm をブラウザで立ち上げてください。 ホームページと同様にブックマークもできます。

編集作業の説明は GpxEdit2.htm の編集画面にある「使い方」で開くウインドウ(usage.htm)を参照してください。

 ----------------------------------------------------------------

改版履歴

V2.2

・ルートの色を編集ルートは赤か黄色（結合モード）、複数の読込みルートがある場合は編集ルート以外は紫に変更
（V2.1までは読込みルートの色は全て赤、編集ルートとして選択すると緑か黄色）

・作業モードを変更しても編集ルートをリセットしないように変更
（V2.1までは読込みルートが１本でも選択する必要があり、作業モードを変更するたびにルートを選択する必要があった)

・ポイント情報のルート情報表示に合計距離と累積標高差を追加、緯度経度表示を地理院地図やGoogleMap等に直接コピペして検索できるように変更

・指定トラックのみの時間変更を削除

・名前変更でトラック名とNumberをブランクに出来ないバグを修正

・標高データ無いルートで部分修正が出来ないバグを修正



V2.1　2022/11/03

・ポイント情報のルート情報表示の時間と標高は入力欄の表示のみとし、標高も入力できるように変更

・標高置換で地理院地図のデータがない場所は代替値が使え、代替値を使わない場合はブランクとなるように変更

・標高値のあるkmlファイルの読込みで、標高が緯度と同じ値になるバグを修正



V2.0　2022/05/27

