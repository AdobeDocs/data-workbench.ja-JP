---
description: イベントデータを出力するための命令は、エクスポーターから与えられます。
solution: Analytics
title: エクスポーターの定義
topic: Data workbench
uuid: 565d4482-6c25-407c-bda7-0d116180902a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# エクスポーターの定義{#defining-exporters}

イベントデータを出力するための命令は、エクスポーターから与えられます。

Transformation functionality provides three types of exporters for exporting [!DNL .vsl] files, log files, XML files, and ODBC data as [!DNL .vsl] files, text files, or delimited text files that can be used by DataWarehouse loading routines, auditing agencies, or other targets.

>[!NOTE]
>
>エクスポーターが正しく動作するためには、ログソースが、ログ処理設定ファイルの [Log Sources](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea) （ログソース）セクションで説明されている適切な [要件を満たしている必要があります](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)。

**エクスポーターを定義するには**

1. Open [!DNL Transform.cfg] in data workbench. See [To edit the Insight Transform.cfg file](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13).
1. 右クリックし、 **[!UICONTROL Exporters]**&#x200B;をクリックしま **[!UICONTROL Add New]**&#x200B;す。
1. 次のいずれかのオプションを選択します。

   * **[!UICONTROL ExportTextFile]**
   * **[!UICONTROL ExportDelimitedTextFile]**
   * **[!UICONTROL ExportVSLFile]**
   >[!NOTE]
   >
   >For the [!DNL ExportVSLFile] option, all of the extended fields in the input file and all user-defined fields of the form cs(*header*) are always written to the VSL output file. 既存の拡張フィールドを上書きした場合、出力ファイルに新しい値が書き込まれます。そのフィールドがブランクであったとしても同様です。

1. 次の表を参考にして、設定ファイルの Exporters パラメーターを編集します。

   <table id="table_35C380DB6E4F42448C149D5EC185213C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> パラメーター </th> 
      <th colname="col2" class="entry"> 説明 </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> Data Format </td> 
      <td colname="col2"> <p><span class="wintitle">ExportTextFile</span> の場合のみ。各出力行の形式。エスケープされたフィールド名（%<i>fieldname</i>% 形式）とその他必要な定型テキストから成ります。この形式には、行区切り記号を含める必要があります（通常、[CR] [LF]）。 </p> <p> 書式設定文字列にリテラルのパーセント記号（%）を含めるには、「%%」のようにエスケープする必要があります。 </p> <p> 例えば、「<span class="filepath">%x-timestring% %x-trackingid%[CR][LF]</span>」のように Data Format パラメーターを入力します。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> フィールド </td> 
      <td colname="col2"><span class="wintitle">ExportDelimitedTextFile</span> の場合のみ。出力するフィールドの名前。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Delimiter </td> 
      <td colname="col2"> <p>(オプション)<span class="wintitle">ExportDelimitedTextFile</span> の場合のみ。出力ファイル内のフィールドの区切りに使用する文字。 </p> <p> データの値に含まれている区切り文字はエスケープできません。そのため、コンマを区切り文字として使用することは、できるだけ避けてください。 </p> <p> Delimiter パラメーター内で Ctrl キーを押しながら右クリックすると、<span class="wintitle">挿入</span>メニューが表示されます。このメニューには、区切り文字としてよく使用される特殊文字が一覧表示されます。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Line Separator </td> 
      <td colname="col2">(オプション)<span class="wintitle">ExportDelimitedTextFile</span> の場合のみ。出力ファイル内の行の区切りに使用する文字。デフォルト値は [CR] [LF] です。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 名前 </td> 
      <td colname="col2"> <p>(オプション)エクスポーターの識別子。「<span class="wintitle">詳細なステータス</span>」インターフェイスにはこの名前が表示されます。 </p> <p> 「<span class="wintitle">詳細なステータス</span>」インターフェイスについて詳しくは、『<i>Data Workbench ユーザーガイド</i>』を参照してください。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Comments </td> 
      <td colname="col2"> (オプション)エクスポーターについてのメモ。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Output Path </td> 
      <td colname="col2"> <p>出力ファイルの保存先となるパス。Data Workbench サーバーのインストールフォルダーを基準とする相対パスで指定します。 </p> <p> <p>注意：出力データを格納する Data Workbench サーバーは、<span class="filepath">profile.cfg</span> ファイルにおける処理サーバー #0 です。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> File Rotation Period </td> 
      <td colname="col2"> <p>(オプション)出力ファイルにデータをエクスポートする頻度。それぞれの出力ファイルには、特定の期間（ローテーション期間）に関連したデータが含まれます。すべての時刻計算は GMT で行われます。つまり、1 日は午前 0 時 GMT に始まり、翌日の午前 0 時 GMT に終わります。ファイルに書き込まれたデータが、現地時刻に変換済みのフィールドを含んでいたとしても同様です。 </p> <p> 選択できる値は次のとおりです。 </p> 
      <ul id="ul_64F56D093E2E4D07ACB7D7921F4E6FA1"> 
       <li id="li_E4985C7F56E443049AFF57B0270032D6"> YEAR：1 年分のデータが各ファイルに保存されます。 </li> 
       <li id="li_42E59BB7A5704C85A6079ED9715C44BC"> MONTH：1 か月分のデータが各ファイルに保存されます。それぞれの月には、1（1 月）～ 12（12 月）の番号が付けられています。 </li> 
       <li id="li_91831283616C48DA8C8086776D181751"> WEEK：1 週間分のデータが各ファイルに保存されます。週の始まりは月曜日です。1 年の最初の 7 日間のうちいずれかの日を始まりとする週を第 1 週とし、その前の（不完全な）週がもしあれば第 0 週となります。 </li> 
       <li id="li_BDB7B4D779434B98935261B8B5C0AABB"> DAY：1 日分のデータが各ファイルに保存されます。 </li> 
       <li id="li_018F4133E03C42F29073FED1DB082ED5"> HOUR：1 時間分のデータが各ファイルに保存されます。 </li> 
       <li id="li_EE8CF71BA12149F49D4B7F7108262CD0"> NONE：ファイルの回転は実施されません。すべてのデータが同じファイル（または他のパラメーターの設定で指定された一連のファイル）に書き込まれます。詳しくは、この表の「<span class="wintitle">File Name Format</span>」パラメーターを参照してください。 </li> 
      </ul> <p>ファイルのローテーション期間のデフォルトは DAY です。 </p> 
      <ul id="ul_0F3BC98275634F759E5022FF2C19715E"> 
       <li id="li_24DC4D144DA94ED0B7B50E8BB39DB8E3"> ファイルの回転を NONE に設定するのは、<span class="wintitle">オフラインモード</span>で作業するときだけにしてください。Offline Modeパラメータ <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13"> ーの説明を参照</a> してください。 </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> File Name Format </td> 
      <td colname="col2"> <p>(オプション)出力ファイル名の形式。 </p> <p> 各ログエントリの保存先となるファイルには、ローテーション期間の開始時刻に由来した名前を付けることができます。さらに、ログエントリに含まれている行のフィールド値をファイル名の中で使用することもできます。フィールド名は、エスケープして（%<i>fieldname</i>% 形式で）ファイル名に埋め込みます。 </p> <p>ローテーション期間に関連した構成要素は、次のエスケープシーケンスを使用した書式設定文字列でファイル名に埋め込みます。 
      <ul id="ul_3C5C8C5DC9104070ABCFDD85F49BE596"> 
       <li id="li_B100AE13FEA84AB6A1138CF58440E29E"> %yyyy%（4 桁の年） </li> 
       <li id="li_0583970798494A1795B03866DC717FB9"> %yy%（2 桁の年） </li> 
       <li id="li_10AA96200F294364A5CE9DC3F22C789A"> %mm%（2 桁の月、01 ～ 12） </li> 
       <li id="li_E112E367F62147C49751D6894E47607C"> %ww%（2 桁の週、01 ～ 52） </li> 
       <li id="li_C4B30E38C05942BB8CAA92F3C9B98A3C"> %dd%（2 桁の日、01 ～ 31） </li> 
       <li id="li_0318CA8C4DC441B48C16B29A615F3293"> %HH%（2 桁の時、00 ～ 23） </li> 
      </ul> </p> <p> ファイル名のデフォルトの形式は <span class="filepath">%yyyy%%mm%%dd%-%x-mask%.txt</span> です。 </p> 
      <ul id="ul_07AE3624E7D74632AD5E5F164048196F"> 
       <li id="li_BA5C2BFBA73D4AAD8D729B30FF812759"> エスケープシーケンスでは、大文字と小文字が区別されます。 </li> 
       <li id="li_32CB9C98190D4B17B4DA84732CFB9E2F"> File Rotation Period を NONE に設定した場合、エスケープシーケンス（存在する場合）は空の文字列に置き換えられます。 </li> 
       <li id="li_C64731961ED6402FB92210A42854BA72"> <span class="wintitle">File Name Format</span> で得られたファイル名がローテーション期間ごとに一意になっていない場合、エラーが発生します（この表の「File Rotation Period」パラメーターを参照）。例えば、ローテーション期間を DAY とした場合、データの喪失を防ぐために、%dd% と %mm% に加え、%yy% または %yyyy% のエスケープシーケンスをパターンに含める必要があります。 </li> 
       <li id="li_15CDA2ABE450418FA8D9C4BC581C4ADD"> フィールド名のエスケープシーケンスをパターン内で使用する場合、指定したフィールドの値が多様だと、それだけ多くの出力ファイルがローテーション期間ごとに書き込まれます。その場合、パフォーマンスが低下する可能性があるので、この機能は注意して使用してください。 </li> 
       <li id="li_D0F75E4FFAFF47C4AA8A8D14A6E1C18A"> すべての時刻計算は GMT で行われます。 </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Execute at Rollover </td> 
      <td colname="col2"> <p>(オプション)それぞれのファイルの最終処理時に外部（Windows）コマンドを実行できます。コマンドラインは、最終的なファイル名から得られます。その際、次のエスケープシーケンスがこのパラメーターに代入されます。 </p> 
      <ul id="ul_5E16832BDBEA4757A2C02DE4B019A122"> 
       <li id="li_6A74D069353E4FE781657BF492675220"> %dir%：最終的なファイル名のディレクトリ部分（末尾のバックスラッシュを含む）。 </li> 
       <li id="li_2CF7232553C348089B1395BBB0BBD6AE"> %file%：最終的なファイルの名前（ディレクトリと拡張子を除く）。 </li> 
       <li id="li_901BAB90E5EA434F9EE37A60477F4591"> %ext%：最終的なファイル名の拡張子（先頭の「.」を含む）。 </li> 
       <li id="li_AD7269A67A0041438A6951FD1898D458"> %path%：ファイルのフルパス名（%dir%%file%%ext% に相当）。 </li> 
      </ul> <p> デフォルトでは、このパラメーターは空です（コマンドは実行されません）。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Memory Limit </td> 
      <td colname="col2"> <p>(オプション)エクスポーターの出力をバッファリングする際に使用されるメモリ量（バイト）。デフォルト値は 10,000,000 バイトです。 </p> <p> <p>注意：多数の出力ファイルを同時に開く場合は、この値を増やしてください。ただし、他のシステムコンポーネントに必要な空きメモリ量が減る可能性があります。一方、この値を小さくすると、エクスポート処理のパフォーマンスは低下する可能性があります。不明な点はアドビにお問い合わせください。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Open Files Limit </td> 
      <td colname="col2"> <p>(オプション)エクスポーターからの出力時に同時に開くことができるファイルの最大数。この数を超えると、イベントログにエラーが記録され、Data Workbench サーバーの実行が停止されます。デフォルト値は 1000 です。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. [!DNL Transform.cfg] ファイルでエクスポーターを定義し、他のパラメーターに必要な変更を加えたら、そのファイルをローカルに保存してから、Data Workbench サーバーコンピューター上の適切なプロファイルに保存します。
