---
title: Adobe Experience Manager デスクトップアプリケーションのインストールと設定
description: Adobe Experience Manager デスクトップアプリケーションをインストールして、Adobe Experience Manager Assets サーバーと連携し、アセットをローカルファイルシステムにダウンロードするように設定します。
uuid: 79bc9de9-5708-41f9-ac43-68c1fd2a2129
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f6365302-1690-4719-9b8c-035719422740
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a6f33efdd5702cc2f411d0deed8f54e7335c09ed
workflow-type: tm+mt
source-wordcount: '1238'
ht-degree: 100%

---


# Adobe Experience Manager デスクトップアプリケーションのインストール {#install-app-v2}

Adobe Experience Manager デスクトップアプリケーションを使用すると、Adobe Experience Manager 内のアセットをローカルデスクトップから手軽に入手し、任意のネイティブデスクトップアプリケーションで利用できるようになります。アセットをプレビューしたり、ネイティブデスクトップアプリケーションで開いたり、Mac Finder や Windows エクスプローラーで表示して他のドキュメント内に配置したり、ローカルで変更したりできます。変更したアセットをアップロードすると、変更内容が Adobe Experience Manager に保存され、リポジトリ内に新しいバージョンが作成されます。

このような統合により、組織内の様々な役割のユーザーが以下をおこなえます。

* アセットを Adobe Experience Manager Assets で一元管理する。

* サードパーティアプリケーションや Adobe Creative Cloud アプリケーションなど、任意のネイティブデスクトップアプリケーションでアセットにアクセスする。その間、ユーザーはブランディングなどの様々な標準に容易に準拠できます。

Adobe Experience Manager デスクトップアプリケーションを使用するには、次の手順に従います。

* Adobe Experience Manager のバージョンが Adobe Experience Manager デスクトップアプリケーションでサポートされていることを確認します。以下の[必要システム構成](release-notes.md#system-requirements-and-prerequisites-v2)を参照してください。

* アプリケーションをダウンロードしてインストールします。下記の[デスクトップアプリケーションのインストール方法](#install-v2)を参照してください。

* いくつかのアセットを使用して接続をテストします。[アセットの参照方法と検索方法](using.md#browse-search-preview-assets)を参照してください。

## 必要システム構成、前提条件およびダウンロードリンク {#tech-specs-v2}

詳しくは、[Adobe Experience Manager デスクトップアプリケーションリリースノート](release-notes.md)を参照してください。

## 以前のバージョンからのアップグレード {#upgrade-from-previous-version}

デスクトップアプリケーション v1.x のユーザーの場合は、デスクトップアプリケーションの以前のバージョンと最新バージョンの相違点と類似点について理解してください。[デスクトップアプリの新機能](introduction.md#whats-new-v2)と、[アプリの仕組み](release-notes.md#how-app-works)を参照してください。

>[!NOTE]
>
>2 つのバージョンのデスクトップアプリケーションを 1 台のコンピューターに共存させることはできません。あるバージョンをインストールするには、その前に他のバージョンをアンインストールします。

以前のバージョンのアプリケーションからアップグレードするには、次の手順に従います。

1. アップグレードする前に、すべてのアセットを同期し、変更を Adobe Experience Manager にアップロードします。これは、アプリケーションをアンインストールする際に編集内容が失われないようにするためです。

1. 以前のバージョンのアプリケーションをアンインストールします。アンインストール時に、キャッシュをクリアするオプションを選択します。

1. コンピューターを再起動します。

1. [最新のデスクトップアプリケーションをダウンロードしてインストールします。](release-notes.md)[](#install-v2)以下の手順に従ってください。

## インストール {#install-v2}

デスクトップアプリケーションをインストールするには、次の手順に従います。最新のデスクトップアプリケーションをインストールする前に、既存の Adobe Experience Manager デスクトップアプリケーション v1.x をアンインストールします。詳しくは、上記を参照してください。

1. 最新のインストーラーを[リリースノート](release-notes.md)ページからダウンロードします。

1. Adobe Experience Manager デプロイメントの URL と認証情報を手元に用意します。

1. 別のバージョンのアプリケーションからアップグレードする場合は、[デスクトップアプリケーションのアップグレード](#upgrade-from-previous-version)を参照してください。

1. Adobe Experience Manager as a Cloud Service、Adobe Experience Manager 6.4.4 以降、Adobe Experience Manager 6.5.0 以降のいずれかを使用している場合は、この手順をスキップします。Adobe Experience Manager の設定が、[リリースノート](release-notes.md)に記載されている互換性要件を満たしていることを確認します。必要に応じて、該当する[互換性パッケージ](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)をダウンロードし、Adobe Experience Manager 管理者として Adobe Experience Manager パッケージマネージャーを使用してインストールします。パッケージのインストールについては、[パッケージの作業方法](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/administering/contentmanagement/package-manager.html)を参照してください。

1. インストーラーのバイナリを実行し、画面の指示に従ってインストールします。

1. Windows では、`Visual Studio C++ Redistributable 2015` をインストールするように求められる場合があります。その場合は、画面の指示に従ってインストールします。インストールに失敗した場合は、手動でインストールします。インストーラーを[ここ](https://www.microsoft.com/ja-jp/download/details.aspx?id=52685)からダウンロードし、`vc_redist.x64.exe` ファイルと `vc_redist.x86.exe` ファイルを両方ともインストールします。AEM デスクトップアプリケーションインストーラーを再実行します。

1. 指示に従ってコンピューターを再起動します。デスクトップアプリケーションを起動し設定します。

1. デスクトップアプリケーションを AEM リポジトリに接続するには、トレイのデスクトップアプリケーションアイコンをクリックしてデスクトップアプリケーションを起動します。AEM インスタンスのアドレスを指定します。「**[!UICONTROL Connect]**」をクリックし、認証情報を入力します。

   ![入力サーバーアドレスへのデスクトップアプリの接続画面](assets/connect_da2.png)

   *図：入力サーバーアドレスへの接続画面*

   >[!CAUTION]
   >
   >AEM サーバーのアドレスの前後にスペースがないことを確認します。スペースがあると、デスクトップアプリケーションが AEM サーバーに接続できません。

1. 接続に成功すると、AEM DAM のルートフォルダーにあるフォルダーやアセットのリストが表示されます。デスクトップアプリケーション内からフォルダーを参照できます。

   ![ログイン時に、アプリケーションに DAM コンテンツが表示されます](assets/firstview_da2.png)

   *図：ログイン後に DAM コンテンツが表示される*

1. （Adobe Experience Manager 6.5.1 以降）デスクトップアプリケーションを Adobe Experience Manager 6.5.1 以降で使用している場合は、S3 または Azure コネクタをバージョン 1.10.4 以降にアップグレードします。詳しくは、[Azure コネクタ](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/deploying/deploying/data-store-config.html#AzureDataStore)または [S3 コネクタ](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/deploying/deploying/data-store-config.html#AmazonS3DataStore)を参照してください。

   Adobe Managed Services（AMS）を使用している場合は、アドビカスタマーケアにお問い合わせください。

## 環境設定の指定 {#set-preferences}

環境設定を変更するには、![その他のオプション](assets/do-not-localize/more_options_da2.png)アイコンと&#x200B;**[!UICONTROL Preference]**![&#x200B;環境設定](assets/do-not-localize/preferences_icon_da2.png)アイコンを順にクリックします。**[!UICONTROL Preferences]** ウィンドウで、以下の値を調整します。

* [!UICONTROL Launch application on login].

* [!UICONTROL Show window when application starts].

* **[!UICONTROL Cache Directory]**：デスクトップアプリケーションのローカルキャッシュの場所（ローカルにダウンロードされたアセットが格納されます）

* **[!UICONTROL Network Drive Letter]**：AEM DAM へのマッピングに使用されるドライブ文字。確信がない限り、この値を変更しないでください。デスクトップアプリケーションでは、Windows の任意のドライブ文字にマッピングできます。2 人のユーザーが異なるドライブ文字のアセットを配置した場合、互いに相手が配置したアセットは表示されません。アセットのパスが変更されます。アセットは、バイナリファイル（INDD など）に配置されたままで、削除されません。使用可能なすべてのドライブ文字がデスクトップアプリケーションに一覧表示され、最後に使用可能な文字（通常は `Z`）がデフォルトで使用されます。

* **[!UICONTROL Maximum Cache Size]**：ローカルにダウンロードしたアセットの保存に使用できる、ハードディスク上のキャッシュのサイズ（GB 単位）

* **[!UICONTROL Current cache size]**：ローカルにダウンロードしたアセットのストレージサイズ。この情報は、デスクトップアプリケーションを使用してアセットをダウンロードした後にのみ表示されます。

* **[!UICONTROL Automatically download linked assets]**：サポート対象のネイティブ Creative Cloud アプリケーションに配置されたアセットは、元のファイルをダウンロードすると自動的に取得されます。

* **[!UICONTROL Maximum number of downloads]**：（「Reveal」、「Open」、「Edit」、「Download」などのオプションを使用して）初めてアセットをダウンロードする場合は、バッチに含まれているアセットがこの数より少ない場合にのみ、アセットがダウンロードされます。デフォルト値は 50 です。不明な場合は、値を変更しないでください。値を増やすと、待ち時間が長くなり、値を減らすと、必要なアセットやフォルダーを 1 回でダウンロードできなくなる場合があります。

* **[!UICONTROL Upload Acceleration]**：アプリケーションでアセットをアップロードする際に同時アップロードを使用して、アップロード速度を向上させることができます。スライダーを右に動かして、アップロードの同時実行性を高めることができます。スライダーが最も左側にある場合は、同時実行をおこなわないこと（シングルスレッドアップロード）を意味し、中央にある場合は 10 個の同時スレッドに相当し、右端の上限にある場合は 20 個の同時スレッドに相当します。同時実行性の上限を高くすると、ローカルマシンのプロセッサのリソース消費量が増えます。

使用できない環境設定を更新するには、AEM サーバーからログアウトします。環境設定を更新した後、![環境設定の保存](assets/do-not-localize/save_preferences_da2.png)アイコンをクリックして、変更内容を保存します。

![デスクトップアプリケーションの環境設定](assets/preferences_da2.png)

*図：デスクトップアプリケーションの環境設定*

## デスクトップアプリケーションのアンインストール {#uninstall-the-app}

Windows でデスクトップアプリケーションをアンインストールするには、次の手順に従います。

1. AEM に変更内容をすべてアップロードして、編集内容が失われないようにします。詳しくは、[アセットの編集と AEM への更新済みアセットのアップロード](using.md#edit-assets-upload-updated-assets)を参照してください。ログオフし、デスクトップアプリケーションの「[!UICONTROL Exit]」を実行します。

1. 他の OS アプリケーションを削除する場合と同様に、デスクトップアプリケーションを削除します。Windows のプログラムの追加と削除からアンインストールします。

1. キャッシュとログを削除するには、必要なチェックボックスをオンにします。

   ![ログとキャッシュを削除するアンインストールダイアログ](assets/uninstall_da2.png)

1. 画面に表示される指示に従います。完了したら、コンピューターを再起動します。

Mac でデスクトップアプリケーションをアンインストールするには、次の手順に従います。

1. AEM に変更内容をすべてアップロードして、編集内容が失われないようにします。詳しくは、[アセットの編集と AEM への更新済みアセットのアップロード](using.md#edit-assets-upload-updated-assets)を参照してください。ログオフし、デスクトップアプリケーションの「[!UICONTROL Exit]」を実行します。

1. `/Applications` から `Adobe Experience Manager Desktop.app` を削除します。

あるいは、Mac 上の内部アプリケーションキャッシュを消去し、デスクトップアプリケーションをアンインストールするには、ターミナルで  というコマンドを実行します。

```shell
/Applications/Adobe Experience Manager Desktop/Contents/Resources/uninstall-osx/uninstall.sh
```
