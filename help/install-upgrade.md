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
source-git-commit: 49532b1c5eec497df5b29084675c08f25a15819a

---


# Adobe Experience Manager デスクトップアプリケーションのインストール {#install-app-v2}

Adobe Experience Managerデスクトップアプリケーションを使用すると、Experience Manager内のアセットをローカルデスクトップで簡単に使用でき、任意のネイティブデスクトップアプリケーションで使用できます。 アセットのプレビュー、ネイティブデスクトップアプリケーションでの開き、他のドキュメントでの配置用にMac FinderまたはWindowsエクスプローラーでの表示、ローカルでの変更が可能です。アップロード時に変更がExperience Managerに保存され、リポジトリに新しいバージョンが作成されます。

このような統合により、組織内の様々な役割が

* Experience Manager Assetsでアセットを一元管理します。
* サードパーティ製アプリケーションやAdobe Creative Cloudなど、任意のネイティブデスクトップアプリケーションのアセットにアクセスします。 これを行うと、ブランディングを含む様々な標準に簡単に準拠できます。

Adobe Experience Manager デスクトップアプリケーションを使用するには、次の手順に従います。

* Experience ManagerのバージョンがExperience Managerデスクトップアプリケーションでサポートされていることを確認します。 以下の必要システ [ム構成を参照](release-notes.md#system-requirements-and-prerequisites-v2) 。
* アプリケーションをダウンロードしてインストールします。下記のデスクト [ップアプリケーションのインストール](#install-v2) （英語）を参照してください。
* いくつかのアセットを使用して接続をテストします。アセッ [トの参照方法と検索方法を参照します](using.md#browse-search-preview-assets)。

## 必要システム構成、前提条件およびダウンロードリンク {#tech-specs-v2}

詳しくは、[Adobe Experience Manager デスクトップアプリケーションリリースノート](release-notes.md)を参照してください。

## デスクトップアプリケーション v1.x から v2 へのアップグレード {#upgrade-from-previous-version}

デスクトップアプリケーションの既存ユーザーの場合は、デスクトップアプリケーションの以前のバージョンと最新バージョンの相違点と類似点を理解します。また、v1.xから最新トランジションに移行するには、次のガイドラインに従ってください。

>[!NOTE]
>
>デスクトップアプリケーション v1.x と v2 は 1 台のマシン上に共存できません。あるバージョンをインストールするには、その前に他のバージョンをアンインストールします。

デスクトップアプリケーションの v1.x から最新バージョンにアップグレードするには、次の手順に従います。

1. アップグレードする前に、すべてのアセットを同期します。デスクトップアプリケーション v1.x を使用して、すべての変更内容をアップロードします。これは、デスクトップアプリケーション v1.x のアンインストール時に変更内容が失われるのを避けるためです。
1. デスクトップアプリケーション v1.x をアンインストールします。v1.x のアンインストール時に、キャッシュをクリアします。
1. コンピューターを再起動します。
1. 最新のデスクトップアプリケーションをダウンロードしてインストールします。以下の手順に従ってください。

## インストール {#install-v2}

デスクトップアプリケーションをインストールするには、次の手順に従います。最新のデスクトップアプリケーションをインストールする前に、既存の Adobe Experience Manager デスクトップアプリケーション v1.x をアンインストールします。詳しくは、上記を参照してください。

1. Experience ManagerデプロイメントのURLと資格情報を手元に置いておきます。
1. Experience Managerをクラウドサービス、Experience Manager 6.4.4以降、Experience Manager 6.5.0以降として使用している場合は、この手順をスキップします。 Ensure that your Experience Manager setup meets the compatibility requirements mentioned in the [release notes](release-notes.md). If necessary, download the applicable [compatibility package](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) and install it using the Experience Manager Package Manager as an Experience Manager administrator. パッケージのインストールについては、[パッケージの作業方法](https://helpx.adobe.com/jp/experience-manager/6-5/sites/administering/using/package-manager.html)を参照してください。
1. インストーラーのバイナリを実行し、画面の指示に従ってインストールします。
1. Windows では、`Visual Studio C++ Redistributable 2015` をインストールするように求められる場合があります。その場合は、画面の指示に従ってインストールします。インストールに失敗した場合は、手動でインストールします。インストーラーを[ここ](https://www.microsoft.com/ja-jp/download/details.aspx?id=52685)からダウンロードし、`vc_redist.x64.exe` ファイルと `vc_redist.x86.exe` ファイルを両方ともインストールします。AEM デスクトップアプリケーションインストーラーを再実行します。
1. 指示に従ってコンピューターを再起動します。デスクトップアプリを起動し、設定します。
1. デスクトップアプリケーションを AEM リポジトリに接続するには、トレイのデスクトップアプリケーションアイコンをクリックしてデスクトップアプリケーションを起動します。AEM インスタンスのアドレスを指定します。「**[!UICONTROL Connect]**」をクリックし、認証情報を入力します。

   ![サーバーアドレスを入力するためのデスクトップアプリケーションの接続画面](assets/connect_da2.png "サーバーアドレスを入力するための接続画面")

   >[!C注意]
   >
   >AEM サーバーのアドレスの前後にスペースがないことを確認します。スペースがあると、デスクトップアプリケーションが AEM サーバーに接続できません。

1. 接続に成功すると、AEM DAM のルートフォルダーにあるフォルダーやアセットのリストが表示されます。デスクトップアプリケーション内からフォルダーを参照できます。

   ![ログイン時にデスクトップアプリケーションに表示される DAM コンテンツ](assets/firstview_da2.png "ログイン時にデスクトップアプリケーションに表示される DAM コンテンツ")

1. （Experience Manager 6.5.1以降）Experience Manager 6.5.1以降でデスクトップアプリを使用している場合は、S3またはAzureコネクタをバージョン1.10.4以降にアップグレードします。 詳しくは、[Azure コネクタ](https://helpx.adobe.com/jp/experience-manager/6-5/sites/deploying/using/data-store-config.html#AzureDataStore)または [S3 コネクタ](https://helpx.adobe.com/jp/experience-manager/6-5/sites/deploying/using/data-store-config.html#AmazonS3DataStore)を参照してください。

   Adobe Managed Services（AMS）を使用している場合は、アドビカスタマーケアにお問い合わせください。

## 環境設定の指定 {#set-preferences}

環境設定を変更するには、![その他のオプション](assets/do-not-localize/more_options_da2.png) アイコンと **[!UICONTROL Preference]** ![環境設定](assets/do-not-localize/preferences_icon_da2.png) アイコンを順にクリックします。**[!UICONTROL Preferences]** ウィンドウで、以下の値を調整します。

* [!UICONTROL Launch application on login].
* [!UICONTROL Show window when application starts].
* **[!UICONTROL Cache Directory]**：デスクトップアプリケーションのローカルキャッシュの場所（ローカルにダウンロードされたアセットが格納されます）
* **[!UICONTROL Network Drive Letter]**：AEM DAM へのマッピングに使用されるドライブ文字。確信がない限り、この値を変更しないでください。デスクトップアプリケーションでは、Windows の任意のドライブ文字にマッピングできます。2 人のユーザーが異なるドライブ文字のアセットを配置した場合、互いに相手が配置したアセットは表示されません。アセットのパスが変更されます。アセットは、バイナリファイル（INDD など）に配置されたままで、削除されません。使用可能なすべてのドライブ文字がデスクトップアプリケーションに一覧表示され、最後に使用可能な文字（通常は `Z`）がデフォルトで使用されます。
* **[!UICONTROL Maximum Cache Size]**：ローカルにダウンロードしたアセットの保存に使用できる、ハードディスク上のキャッシュのサイズ（GB 単位）
* **[!UICONTROL Current cache size]**：ローカルにダウンロードしたアセットのストレージサイズ。この情報は、デスクトップアプリケーションを使用してアセットをダウンロードした後にのみ表示されます。
* **[!UICONTROL Automatically download linked assets]**：サポート対象のネイティブ Creative Cloud アプリケーションに配置されたアセットは、元のファイルをダウンロードすると自動的に取得されます。
* **[!UICONTROL Maximum number of downloads]**：（「Reveal」、「Open」、「Edit」、「Download」などのオプションを使用して）初めてアセットをダウンロードする場合は、バッチに含まれているアセットがこの数より少ない場合にのみ、アセットがダウンロードされます。デフォルト値は 50 です。不明な場合は、値を変更しないでください。値を増やすと、待ち時間が長くなり、値を減らすと、必要なアセットやフォルダーを 1 回でダウンロードできなくなる場合があります。
* **[!UICONTROL Upload Acceleration]**:アセットをアップロードする場合、アプリケーションは同時アップロードを使用して、アップロード速度を向上できます。 スライダを右に動かすことで、アップロードの同時実行性を高めることができます。 最も左側のスライダは、同時実行（シングルスレッドアップロード）を行わないことを意味し、中央の位置は10個の同時スレッドに対応し、右端の最大制限は20個の同時スレッドに対応します。 同時性の上限を高くすると、ローカルマシンのプロセッサのリソース消費量が増えます。

使用できない環境設定を更新するには、AEM サーバーからログアウトします。環境設定を更新した後、![環境設定の保存](assets/do-not-localize/save_preferences_da2.png) アイコンをクリックして、変更内容を保存します。

![AEM デスクトップアプリケーションの環境設定](assets/preferences_da2.png "デスクトップアプリケーションの環境設定")

## デスクトップアプリケーションのアンインストール {#uninstall-the-app}

Windows でデスクトップアプリケーションをアンインストールするには、次の手順に従います。

1. AEM に変更内容をすべてアップロードして、編集内容が失われないようにします。詳しくは、[アセットの編集と AEM への更新済みアセットのアップロード](using.md#edit-assets-upload-updated-assets)を参照してください。ログオフし、デスクトップアプリケーションの「[!UICONTROL Exit]」を実行します。
1. 他の OS アプリケーションを削除する場合と同様に、デスクトップアプリケーションを削除します。Windows のプログラムの追加と削除からアンインストールします。
1. キャッシュとログを削除するには、必要なチェックボックスをオンにします。
   ![ログとキャッシュを削除するためのアンインストールダイアログ](assets/uninstall_da2.png "ログとキャッシュを削除するためのアンインストールダイアログ")
1. 画面に表示される指示に従います。完了したら、コンピューターを再起動します。

Mac でデスクトップアプリケーションをアンインストールするには、次の手順に従います。

1. AEM に変更内容をすべてアップロードして、編集内容が失われないようにします。詳しくは、[アセットの編集と AEM への更新済みアセットのアップロード](using.md#edit-assets-upload-updated-assets)を参照してください。ログオフし、デスクトップアプリケーションの「[!UICONTROL Exit]」を実行します。
1. `/Applications` から `Adobe Experience Manager Desktop.app` を削除します。

あるいは、Mac 上の内部アプリケーションキャッシュを消去し、デスクトップアプリケーションをアンインストールするには、ターミナルで `/Applications/Adobe Experience Manager Desktop/Contents/Resources/uninstall-osx/uninstall.sh` というコマンドを実行します。
