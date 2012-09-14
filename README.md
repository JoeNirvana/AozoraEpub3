AozoraEpub3
============

説明
------------
青空文庫テキスト→ePub3変換  
青空文庫の注記入りテキストファイルをePub3ファイル(zip圧縮)に変換するツールです  


利用上の注意
------------
利用は自己責任でお願いします。  
現状、いくつか対応していない注記があります。  
青空文庫の注記仕様外の注記等で変換したxhtmlエラーで章ごと表示されない場合があります。  
4バイト文字を出力すると対応していない端末では外字以降表示されない場合があります。  
（変換しないオプション選択時は注記を小書きで表示）  
バグや変換できない注記があった配布サイトで報告お願いします。  


変換時の注意
------------
コメントの異常、対応していない注記、変換できなかった外字はログに表示されるので適宜元テキスト修正してください。  
- 仕様外や一部の揺らぎのある注記は対応しません。  
- 外字注記内で外字注記が使われている場合はエラーになります（対応予定無し）  
  →※［＃「姉」の正字、「女＋※［＃第3水準1-85-57］のつくり」 とログに出たら  
    該当部分の元テキストを ※［＃「姉」の正字、U+59CA］に修正  
- 注記内に注記がある底本コメント注記は削除してください  


動作環境
------------
Java 6 / Java 7 の動作環境 ( http://www.java.com/ja/ )


使い方
------------
#### インストール
　AozoraEpub3-1.0.*.zip を任意のフォルダに解凍します。  

#### 起動
　AozoraEpub3.jar をダブルクリックして実行します。  
　またはコンソールから "java -jar AozoraEpub3.jar" でも実行可。  
　※javaが見えなければフルパスで指定  
　　例: "C:\Program Files\Java\jre\bin\java.exe" -jar AozoraEpub3.jar  

#### 変換
　表示されたアプレットに、変換したい青空文庫テキストファイル（拡張子txtまたはzip)  
　（複数可）をドラッグ＆ドロップします。(「ファイル選択」から開くでも同じ)  
　テキストファイルと同じ場所に「元ファイル名.epub」または「[著作者名] 表題.epub」のファイルが生成されます。  
　※テキストのない画像のみのzipを変換した場合は、画像のみのePubファイルを生成します。  


使い方 CUI
------------
####コマンドラインからの実行 (仮)
　Usage: java -cp AozoraEpub3.jar AozoraEpub3 "青空文庫テキスト1.txt" "青空文庫テキスト2.zip"  
　※現状オプション指定は未対応 (すべてアップレットのデフォルト状態)  


画面設定
------------
#### 表題
* 本文内  
  本文内のタイトルと著者名の有無を設定します。  
  3行連続の場合はタイトルの次は副題してタイトルと連結します。  
  本文中のタイトルは大きい文字で、著者名地付きに設定されます。  
  画像や空行は無視されます。  
* ファイル名優先  
  "[著作者名] 表題.epub" のファイル名からタイトルと著者名を取得します。  
  本文中のタイトル行と著者名の行のスタイル設定は本文内の選択に従います。  

#### 表紙
* 表紙  
  表紙の画像を先頭の画像、ファイル選択、URLで指定します。  
  入力ファイル名と同じ画像(jpg,png)の場合は、入力ファイル(txr,zip)の拡張子以外が同じ名称の画像を表紙に利用します。  
  (拡張子は以下の順でチェックpng,jpg,jpeg,gif)  

#### ページ出力
* 表紙  
  ePubの先頭に表紙ページ（画像は幅100％）を追加します。  
  Reader等で表紙を出したい場合に指定してください。  
  （先頭の画像を表紙に指定している場合は先頭に移動されませす）  
* 表題左右中央  
  表題、著者等のページを左右中央の単一ページで出力します。  
* 目次  
  目次ページを出力する場合に選択します。  
  縦書きと横書きが選べます  
* 出力ファイル名に表題利用  
  "[著作者名] 表題.epub" のファイル名で出力します。  
  どちらも設定されていない場合は「元ファイル名.epub」で出力します。  
* 拡張子
  出力ファイルの拡張子を指定します。  
  (Koboでの利用はkepub.epubを選択推奨)  

#### 出力先
* 出力先  
  出力先を指定する場合にフルパスを設定します。  

#### 画像縮小
* 画像サイズ
  大きすぎる画像がある場合は指定ピクセルのサイズ以下になるように縮小します。  

#### 変換設定
* 栞用ID出力  
  Koboのkepubでの栞用のidを行のpタグに設定します。  
  Koboのkepub以外の環境では不要です。  
* 自動縦中横  
  半角の2文字の数字、英字、!?を並べて縦書きにします。  
* 4バイト文字変換  
  チェックを外すと4バイト文字を〓に変換し、後ろに注記を小書きで表示します。  
  （Koboでは問題のある場合）  
  Readerでは問題なく表示可能な4バイトのJIS漢字は表示されます。  
  （ただし表示できない漢字の注記が表示されない）  
* 縦書き 横書き  
  縦書きと横書きを指定します。  
  それぞれに合わせたスタイルが設定されます。  
  (基本的にビューア側で縦書き横書きの切り替えはできない？)  

#### 変換
* 入力文字コード  
  入力する青空文庫ファイルの文字コードを指定します。通常はMS932(SJIS)です。  
* ePubファイル上書き  
  同名のファイル(元ファイル名.epub)がすでにある場合でも上書きして出力します。  
* ファイル選択  
  ファイルを選択するとテキストエリアにドラッグアンドドロップするのと同様に変換されます  
* 変換前確認  
  変換前に、タイトルと著者名と表紙の確認と編集が可能なダイアログを表示します。  
  修正したタイトルと著者名でメタデータが作成されます。  
  本文側のタイトルやスタイルは変更されません。  
  表紙はトリミングした画像を出力し、元画像を残す指定も可能です。  


ファイルの説明
------------
#### プログラムファイル  
* AozoraEpub3.jar
    ePub3変換ツール  
    ダブルクリックまたは"java -jar AozoraEpub3.jar"で実行  
* AozoraEpub3.ico
    ショートカットを作ったときにこのアイコンを指定してください（jarなので設定できない）
* lib/*.jar
    利用ライブラリ (compress, Velocity) 

#### ePub3テンプレート
* template/*
    ePub3テンプレート
* template/OPS/css/*.css
    ePub3スタイル

#### 変換用設定ファイル
* chuki_tag_suf.txt
    前方参照型注記を開始終了型注記に変換
* chuki_tag.txt
    注記をePubタグに変換
* chuki_alt.txt
    外字注記を代替文字に変換
* chuki_utf.txt
    外字注記(コード無し)をUTF-8文字に変換
* chuki_latin.txt
    ラテン文字注記をUTF-8に変換
* replace.txt
    文字置換設定ファイル


対応している注記
------------
#### 基本的な注記に設定ファイルで対応
 chuki_tag.txt 参照
 
#### 例外的にプログラム処理しているもの
- ページの左右中央  
-［＃注記付き］○［＃「△」の注記付き終わり］と［＃「○」に「△」のルビ］ → ｜○《△》に変換  
- ［＃「○」に×傍点］ → 文字と同数の×ルビに変換  
- 字下げ連続時の［＃ここで字下げ終わり］の省略  
- 字下げ折り返しと字下げ字詰めは数値化してインデント計算  
  ［＃ここから○字下げ、折り返して●字下げ］［＃ここから○字下げ、●字詰め］  
- 字下げ複合はclassを合成 (罫囲み、中央揃え)  
- 画像 (キャプション、サイズ指定は未対応)  
    ［＃説明（ファイル名.拡張子）］  
    &lt;img src="ファイル名"/&gt;  
- 底本： で改ページ (直前に改ページがない場合)  


対応している外字と特殊文字
------------
* 外字注記をコード変換してUTF-8文字で出力 （UTF8コード、JISコードあり）  
 ※［＃「さんずい＋垂」、unicode6DB6］  
 ※［＃「さんずい＋垂」、U+6DB6、235-7］  
 ※［＃「さんずい＋垂」、UCS6DB6、235-7］  
 ※［＃「てへん＋劣」、第3水準1-84-77］  
* UTF-8にない外字注記は代替文字を出力 (chuk_alt.txt)  
* コード記述がない外字注記は名称からUTF-8に変換 (chuk_utf.txt)  
* 4バイト文字 0x9000以上 は変換しない設定 (ただしJIS漢字も変換されない)  

* 青空文庫特殊文字（《》［］〔〕｜＃※）  
 ※［＃始め二重山括弧、1-1-52］ →《  
 ※［＃終わり二重山括弧、1-1-53］ →》  
 ※［＃始め角括弧、1-1-46］ →［  
 ※［＃終わり角括弧、1-1-47］ →］  
 ※［＃始めきっこう（亀甲）括弧、1-1-44］ →〔  
 ※［＃終わりきっこう（亀甲）括弧、1-1-45］ →〕  
 ※［＃縦線、1-1-35］ →｜  
 ※［＃井げた、1-1-84］ →＃  
 ※［＃米印、1-2-8］ →※  
 
* くの字点「／＼」「／″＼」をUTF-8で出力  


未対応注記
------------
- 重複不可に定義された注記の間に含まれるルビ・圏点・縦横中
- ルビ指定文字内の注記(圏点・縦横中・太字等)
- ここから横組み
- 窓見出し
- 割り注
- 訂正と「ママ」
- 左ルビ
- 画像キャプション


更新予定と更新履歴
------------
README_Changes.txt 参照
