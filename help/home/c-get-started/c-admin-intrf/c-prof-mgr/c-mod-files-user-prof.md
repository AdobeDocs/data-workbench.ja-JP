---
description: プロファイルマネージャーを使用して、変更するファイルをダウンロードできます。
solution: Analytics
title: ユーザープロファイル内のローカルファイルの変更
topic: Data workbench
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modify local files in the user profile{#modify-local-files-in-the-user-profile}

プロファイルマネージャーを使用して、変更するファイルをダウンロードできます。

ファイルをダウンロードして既存のローカルファイルをそのファイルのオリジナルバージョンで上書きしたり、ワークスペースメニューからアクセスできないファイルを開いたり、表示したり、変更したりできます。

**ファイルをダウンロードするには**

1. In the [!DNL Profile Manager], open the necessary folders and subfolders to locate the file that you want to download.
1. Right-click the check mark next to the name of the file and click **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Configuration ( [!DNL .cfg]), dimension ( [!DNL .dim]), and metric ( [!DNL .metric]) files can be edited directly in a profile folder and saved to the server without making them local and separately saving them to the server. Simply right-click the check mark next to the name of the file and click **[!UICONTROL Open]** > **in workstation**.

After the file has been downloaded to the local computer, a check mark appears in the [!DNL User] column, which indicates that a local copy of the file resides in the User\*profile name* folder on your computer. このチェックマークは、*profile name* 列のチェックマークと同じ色であることに注意してください。これは、ローカルファイルが *profile name* フォルダー内のファイルと同じ変更日時を持つことを示します。

**ファイルを変更するには**

1. [!DNL User] 列のファイル名の横のチェックマークを右クリックします。
1. ファイルの編集方法に応じて、以下のメニューオプションのいずれかをクリックします。

   * **[!UICONTROL Open]** /をク **[!UICONTROL in workstation]** リックします。/をク [!DNL .vw] リックすると、フ [!DNL .cfg] ァイルまたはファイルが編集されます。

   * **開く** /**in vw。 エディタ**.vwファイルを編集して新しいパラメータを追加する場合。

   * **[!UICONTROL Open]** /をクリ **[!UICONTROL In Notepad]**[!DNL .cfg] ックします。

   * **[!UICONTROL Open]** >ファ **[!UICONTROL folder]** イルが存在するコンピュータ上のフォルダを開く場合

1. 必要に応じてファイルを編集し、保存します。

In the [!DNL Profile Manager], note that the check mark in the [!DNL User] column for the file you edited has changed color. これは、ローカルファイルが *profile name* フォルダー内のバージョンと異なることを示します。必要に応じて、このプロファイルを使用している他のユーザーが使用できるよう、変更したバージョンのファイルをプロファイルに公開できます。
