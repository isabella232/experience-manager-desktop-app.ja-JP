---
title: ' [!DNL Adobe Experience Manager] デスクトップアプリのインストールと設定'
description: ' [!DNL Adobe Experience Manager] desktop app to work with [!DNL Adobe Experience Manager Assets] サーバーをインストールして設定し、ローカルファイルシステムにアセットをダウンロードします。'
translation-type: tm+mt
source-git-commit: a25c1fa13895ae9eb7268e3e01c83a5f0b9d7d1d
workflow-type: tm+mt
source-wordcount: '1162'
ht-degree: 84%

---


# [!DNL Adobe Experience Manager]デスクトップアプリ{#install-app-v2}をインストール

[!DNL Adobe Experience Manager]デスクトップアプリを使用すると、[!DNL Experience Manager]内のアセットはローカルデスクトップで簡単に入手でき、任意のネイティブデスクトップアプリケーションで使用できます。 アセットのプレビュー、ネイティブデスクトップアプリケーションでの開き方、Mac FinderまたはWindowsエクスプローラでの配置用に表示、ローカルでの変更が可能です。アップロード時に変更内容が[!DNL Experience Manager]に保存され、リポジトリに新しいバージョンが作成されます。

このような統合により、組織内の様々な役割のユーザーが以下をおこなえます。

* [!DNL Experience Manager Assets]でアセットを一元的に管理します。

* サードパーティアプリケーションや Adobe Creative Cloud アプリケーションなど、任意のネイティブデスクトップアプリケーションでアセットにアクセスする。その間、ユーザーはブランディングなどの様々な標準に容易に準拠できます。

[!DNL Experience Manager] デスクトップアプリケーションを使用するには、次の手順に従います。

* [!DNL Experience Manager]バージョンが[!DNL Experience Manager]デスクトップアプリでサポートされていることを確認してください。 以下の[必要システム構成](release-notes.md#system-requirements-and-prerequisites-v2)を参照してください。

* アプリケーションをダウンロードしてインストールします。下記の[デスクトップアプリケーションのインストール方法](#install-v2)を参照してください。

* いくつかのアセットを使用して接続をテストします。[アセットの参照方法と検索方法](using.md#browse-search-preview-assets)を参照してください。

## 必要システム構成、前提条件およびダウンロードリンク {#tech-specs-v2}

詳しくは、[[!DNL Experience Manager] Adobe デスクトップアプリケーションリリースノート](release-notes.md)を参照してください。

## 以前のバージョンからのアップグレード {#upgrade-from-previous-version}

デスクトップアプリケーション v1.x のユーザーの場合は、デスクトップアプリケーションの以前のバージョンと最新バージョンの相違点と類似点について理解してください。[デスクトップアプリの新機能](introduction.md#whats-new-v2)と、[アプリの仕組み](release-notes.md#how-app-works)を参照してください。

>[!NOTE]
>
>2 つのバージョンのデスクトップアプリケーションを 1 台のコンピューターに共存させることはできません。あるバージョンをインストールするには、その前に他のバージョンをアンインストールします。

以前のバージョンのアプリケーションからアップグレードするには、次の手順に従います。

1. アップグレードする前に、すべてのアセットを同期し、変更を[!DNL Experience Manager]にアップロードします。 これは、アプリケーションをアンインストールする際に編集内容が失われないようにするためです。

1. 以前のバージョンのアプリケーションをアンインストールします。アンインストール時に、キャッシュをクリアするオプションを選択します。

1. コンピューターを再起動します。

1. 最新のデスクトップアプリケーションを[ダウンロード](release-notes.md)して[インストール](#install-v2)します。以下の手順に従ってください。

## インストール {#install-v2}

デスクトップアプリケーションをインストールするには、次の手順に従います。最新のAdobeをインストールする前に、既存の[!DNL Experience Manager]デスクトップアプリケーションv1.xをアンインストールしてください。 詳しくは、上記を参照してください。

1. 最新のインストーラーを[リリースノート](release-notes.md)ページからダウンロードします。

1. [!DNL Experience Manager]デプロイメントのURLと資格情報を手元に置いておきます。

1. 別のバージョンのアプリケーションからアップグレードする場合は、[デスクトップアプリケーションのアップグレード](#upgrade-from-previous-version)を参照してください。

1. [!DNL Experience Manager]を[!DNL Cloud Service]、[!DNL Experience Manager] 6.4.4以降、または[!DNL Experience Manager] 6.5.0以降として使用する場合は、この手順をスキップします。 [!DNL Experience Manager]の設定が、[リリースノート](release-notes.md)に記載されている互換性要件を満たしていることを確認してください。 必要に応じて、該当する[互換性パッケージ](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)をダウンロードし、Adobe 管理者として Adobe パッケージマネージャーを使用してインストールします。[!DNL Experience Manager][!DNL Experience Manager]パッケージのインストールについては、[パッケージの作業方法](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html?lang=ja)を参照してください。

1. インストーラーのバイナリを実行し、画面の指示に従ってインストールします。

1. Windows では、`Visual Studio C++ Redistributable 2015` をインストールするように求められる場合があります。その場合は、画面の指示に従ってインストールします。インストールに失敗した場合は、手動でインストールします。インストーラーを[ここ](https://www.microsoft.com/ja-jp/download/details.aspx?id=52685)からダウンロードし、`vc_redist.x64.exe` ファイルと `vc_redist.x86.exe` ファイルを両方ともインストールします。[!DNL Experience Manager] デスクトップアプリケーションインストーラーを再実行します。

1. 指示に従ってコンピューターを再起動します。デスクトップアプリケーションを起動し設定します。

1. アプリケーションを [!DNL Experience Manager] リポジトリーに接続するには、トレイのアプリケーションアイコンをクリックしてアプリケーションを起動します。[!DNL Experience Manager] サーバーのアドレスを `https://[aem_server]:[port]/` の形式で指定します。

   「**[!UICONTROL Connect]**」をクリックし、認証情報を入力します。

   ![入力サーバーアドレスへのデスクトップアプリの接続画面](assets/connect_da2.png)

   *図：入力サーバーアドレスへの接続画面。*

   >[!CAUTION]
   >
   >[!DNL Experience Manager] サーバーのアドレスの前後にスペースがないことを確認します。スペースがあると、デスクトップアプリケーションが [!DNL Experience Manager] サーバーに接続できません。

1. 接続に成功すると、[!DNL Experience Manager] DAM のルートフォルダーにあるフォルダーやアセットのリストが表示されます。デスクトップアプリケーション内からフォルダーを参照できます。

   ![ログイン時に、アプリケーションに DAM コンテンツが表示されます](assets/firstview_da2.png)

   *図：ログイン後に DAM コンテンツが表示される*

1. （[!DNL Experience Manager] 6.5.1以降）[!DNL Experience Manager] 6.5.1以降のデスクトップアプリを使用している場合は、S3またはAzureコネクタをバージョン1.10.4以降にアップグレードします。 詳しくは、[Azure コネクタ](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/data-store-config.html?lang=ja#azure-data-store)または [S3 コネクタ](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/data-store-config.html?lang=ja#amazon-s-data-store)を参照してください。

   Adobe Managed Services（AMS）を使用している場合は、アドビカスタマーケアにお問い合わせください。

## 環境設定の指定 {#set-preferences}

環境設定を変更するには、![その他のオプションアイコン](assets/do-not-localize/more_options_da2.png)と&#x200B;**[!UICONTROL Preference]**![&#x200B;環境設定アイコン](assets/do-not-localize/preferences_icon_da2.png)を順にクリックします。**[!UICONTROL Preferences]** ウィンドウで、以下の値を調整します。

* [!UICONTROL Launch application on login]

* [!UICONTROL Show window when application starts].

* **[!UICONTROL Cache Directory]**：デスクトップアプリケーションのローカルキャッシュの場所（ローカルにダウンロードされたアセットが格納されます）

* **[!UICONTROL Network Drive Letter]**：[!DNL Experience Manager] DAM へのマッピングに使用されるドライブ文字。確信がない限り、この値を変更しないでください。デスクトップアプリケーションでは、Windows の任意のドライブ文字にマッピングできます。2 人のユーザーが異なるドライブ文字のアセットを配置した場合、互いに相手が配置したアセットは表示されません。アセットのパスが変更されます。アセットは、バイナリファイル（INDD など）に配置されたままで、削除されません。使用可能なすべてのドライブ文字がデスクトップアプリケーションに一覧表示され、最後に使用可能な文字（通常は `Z`）がデフォルトで使用されます。

* **[!UICONTROL Maximum Cache Size]**：ローカルにダウンロードしたアセットの保存に使用できる、ハードディスク上のキャッシュのサイズ（GB 単位）

* **[!UICONTROL Current cache size]**：ローカルにダウンロードしたアセットのストレージサイズ。この情報は、デスクトップアプリケーションを使用してアセットをダウンロードした後にのみ表示されます。

* **[!UICONTROL Automatically download linked assets]**：サポート対象のネイティブ Creative Cloud アプリケーションに配置されたアセットは、元のファイルをダウンロードすると自動的に取得されます。

* **[!UICONTROL Maximum number of downloads]**：（「Reveal」、「Open」、「Edit」、「Download」などのオプションを使用して）初めてアセットをダウンロードする場合は、バッチに含まれているアセットがこの数より少ない場合にのみ、アセットがダウンロードされます。デフォルト値は 50 です。不明な場合は、値を変更しないでください。値を増やすと、待ち時間が長くなり、値を減らすと、必要なアセットやフォルダーを 1 回でダウンロードできなくなる場合があります。

* **[!UICONTROL Upload Acceleration]**：アプリケーションでアセットをアップロードする際に同時アップロードを使用して、アップロード速度を向上させることができます。スライダーを右に動かして、アップロードの同時実行性を高めることができます。スライダーが最も左側にある場合は、同時実行をおこなわないこと（シングルスレッドアップロード）を意味し、中央にある場合は 10 個の同時スレッドに相当し、右端の上限にある場合は 20 個の同時スレッドに相当します。同時実行性の上限を高くすると、ローカルマシンのプロセッサのリソース消費量が増えます。

使用できない環境設定を更新するには、[!DNL Experience Manager] サーバーからログアウトします。環境設定を更新した後、![環境設定の保存](assets/do-not-localize/save_preferences_da2.png)アイコンをクリックして、変更内容を保存します。

![デスクトップアプリケーションの環境設定](assets/preferences_da2.png)

*図：デスクトップアプリケーションの環境設定*

## デスクトップアプリケーションのアンインストール {#uninstall-the-app}

Windows でデスクトップアプリケーションをアンインストールするには、次の手順に従います。

1. [!DNL Experience Manager] に変更内容をすべてアップロードして、編集内容が失われないようにします。詳しくは、「[アセットの編集と  [!DNL Experience Manager]](using.md#edit-assets-upload-updated-assets) への更新済みアセットのアップロード」を参照してください。ログオフし、デスクトップアプリケーションの「[!UICONTROL Exit]」を実行します。

1. 他の OS アプリケーションを削除する場合と同様に、デスクトップアプリケーションを削除します。Windows のプログラムの追加と削除からアンインストールします。

1. キャッシュとログを削除するには、必要なチェックボックスをオンにします。

   ![ログとキャッシュを削除するアンインストールダイアログ](assets/uninstall_da2.png)

1. 画面に表示される指示に従います。完了したら、コンピューターを再起動します。

Mac でデスクトップアプリケーションをアンインストールするには、次の手順に従います。

1. [!DNL Experience Manager] に変更内容をすべてアップロードして、編集内容が失われないようにします。詳しくは、「[アセットの編集と  [!DNL Experience Manager]](using.md#edit-assets-upload-updated-assets) への更新済みアセットのアップロード」を参照してください。ログオフし、デスクトップアプリケーションの「[!UICONTROL Exit]」を実行します。

1. `/Applications` から `Adobe Experience Manager Desktop.app` を削除します。

あるいは、Mac 上の内部アプリケーションキャッシュを消去し、デスクトップアプリケーションをアンインストールするには、ターミナルで次のコマンドを実行します。

```shell
/Applications/Adobe Experience Manager Desktop/Contents/Resources/uninstall-osx/uninstall.sh
```
