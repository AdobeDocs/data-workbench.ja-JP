---
description: Data Workbench では、現在、国際的な言語の補助的なテキスト入力プロセスとして Input Method Editor（IME）をサポートしています。
title: Input Method Editor のインストール
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
exl-id: 3fcc58f5-29a9-427e-831a-44d527614b56,0bdc7d95-b49a-4ca5-9fde-9c1ce2cd14ec,e4e1c016-0544-434a-b82e-fdd2a4af316c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 91%

---

# Input Method Editor のインストール{#installing-the-input-method-editor}

data workbench は、多言語による入力をサポートするため、Input Method Editor（IME）を利用可能です。

IME を使用すると、地域の言語に適した様々な方法を用いて国際文字を入力できます。Data Workbench に用意されている入力ダイアログボックスを開くと、テキストフィールドで目的の IME を使用できます。

>[!NOTE]
>
>Data Workbench 6.1リリースでは、簡体字中国語の仮想キーボードのみがサポートされます。 この IME で他の言語を入力すると、予期せぬ動作が生じる可能性があります。

## IME の使用 {#section-5f008d75a7b24119ab6aebc55454f927}

フローティング IME テキスト入力機能を使用するには：

1. 任意のテキスト入力領域で&#x200B;**[!UICONTROL Alt + Space]**&#x200B;をクリックします。
1. システムの IME を使用して値を入力します。
1. **[!UICONTROL Enter]** キーを押すか、「**[!UICONTROL OK]**」ボタンをクリックして、入力ダイアログを閉じます。

   ダイアログが消え、選択したフィールドに文字が表示されます。

**Insight.cfg ファイルの更新**

IME を利用するには、[!DNL Insight.cfg] ファイルを次の設定で更新する必要があります。

```
Localized IME = bool: true
```

設定ファイル内にこの設定が存在しない場合は、**[!UICONTROL Alt + Space]** キーを押しても IME 機能が起動しません。

**別の言語で Insight を起動する：**&#x200B;スプラッシュスクリーンのようにローカライズされたアセットをサポートしたり、将来的に複数の言語をサポートしたりするには、Data Workbench では、ロードする言語を指定するコマンドライン引数が必要です。デフォルトの言語は英語です。

Data Workbench を中国語で起動するには、「-zh-cn」引数を指定して [!DNL Insight.exe] を起動する必要があります。

```
Insight.exe -zh-cn
```

（これらのコマンドライン引数は大文字と小文字を区別しません。）
