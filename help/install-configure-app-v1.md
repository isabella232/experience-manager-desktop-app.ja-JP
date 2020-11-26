---
title: Install and configure [!DNL Experience Manager] desktop app version 1.x
description: サーバーをインストールして [!DNL Experience Manager] desktop app version 1.x to work with [!DNL Assets] 設定し、アセットをデスクトップ上のドライブとしてマウントするようにマップします。
uuid: 79bc9de9-5708-41f9-ac43-68c1fd2a2129
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.5/ASSETS, SG_EXPERIENCEMANAGER/6.4/ASSETS,SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f6365302-1690-4719-9b8c-035719422740
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2893fc1f8aad02e1436a1a281a320e6837487220
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 68%

---


# Install and configure [!DNL Experience Manager] desktop app v1.x {#install-and-configure-aem-desktop-app}

Using the [!DNL Experience Manager] desktop app, the assets within [!DNL Experience Manager] are easily accessible on your local desktop and can be used in any desktop applications. Assets can be easily revealed in Mac Finder or Windows Explorer, opened in desktop applications, and changed locally – the changes are saved back to [!DNL Experience Manager] when you upload and a new version is created in the repository.

このような統合により、組織内の様々な役割のユーザーが Assets でアセットを一元管理し、Creative Cloud やその他のアプリケーションからアセットにアクセスできるようになります。さらに、ブランディングなど様々な基準に準拠することが容易になります。

To use [!DNL Experience Manager] desktop app,

* Ensure that your [!DNL Experience Manager] server version is supported by [!DNL Experience Manager] desktop app. [互換表](release-notes-of-v1.md#compatibilitymatrix)を参照してください。

* アプリケーションをダウンロードしてインストールします。

* いくつかのアセットを使用して接続をテストします。詳しくは、[デスクトップでのアセットへのアクセスとオープン](use-app-v1.md#openondesktop)を参照してください。

## 必要システム構成、前提条件およびダウンロードリンク {#system-requirements-prerequisites-and-download-links}

詳しくは、[[!DNL Experience Manager] Adobe デスクトップアプリケーションリリースノート](release-notes-of-v1.md)を参照してください。

## アプリケーションをインストールし、サー [!DNL Experience Manager] バーに接続します {#install-and-connect-aem-desktop-app-to-aem-server}

詳しくは、「 [インストールと [!DNL Experience Manager] desktop app to [!DNL Experience Manager] 接続サーバー](use-app-v1.md#installandconnect)」を参照してください。

>[!NOTE]
>
>Only one instance of the [!DNL Experience Manager] desktop app can be installed and be active at a time.

## ファイルの処理 {#file-handling}

デスクトップアプリケーションによってマウントされたネットワーク共有の場所からファイルを変更した場合、ファイルは 2 つの段階を経てその場所に保存されます。第 1 段階では、ファイルがローカルに保存されます。ユーザーは、ファイルを保存し、転送が完了するのを待つことなくそのファイルに対する作業を続けることができます。

In the second phase, desktop app uploads the updated file to [!DNL Experience Manager] server after a predefined delay (for example, 30s). この処理はバックグラウンドで実行されます。「View Asset Status」オプションを使用して、アップロード処理のステータスを表示できます。

1.  Assets にアセットをアップロードします。

1. Click the [!DNL Experience Manager] desktop app icon from the toolbar.

1. メニューから、「View Asset Status」オプションを選択します。

1. ダイアログで、アップロード処理のステータスを確認します。

>[!NOTE]
>
>[!DNL Experience Manager] デスクトップアプリケーションでは、最大40 GBのサイズのアセットを処理できます。

## Connect to an [!DNL Experience Manager] instance behind a dispatcher {#connect-to-an-aem-instance-behind-a-dispatcher}

The copy and move methods in the Assets API require the following additional headers to be passed to [!DNL Experience Manager]:

* X-Destination
* X-Depth
* X-Overwrite

[!DNL Experience Manager] デスクトップアプリケーションは、デフォルトポートを含む URL を使用して に接続します。[!DNL Experience Manager]したがって、Dispatcher 設定の `virtualhosts` の設定にデフォルトポート番号を含める必要があります。`virtualhosts` の設定について詳しくは、[仮想ホストの識別](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=ja#identifying-virtual-hosts-virtualhosts)を参照してください。

これらの追加ヘッダーを引き渡すように Dispatcher を設定する方法について詳しくは、[HTTP ヘッダーの指定](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=ja#specifying-the-http-headers-to-pass-through-clientheaders)を参照してください。

### プロキシのサポート {#proxy-support}

[!DNL Experience Manager] デスクトップアプリケーションは、システムで事前に定義されたプロキシ経由で、HTTPS を使用してインターネットに接続します。AEM デスクトップアプリケーションは、追加の認証が必要ないネットワークプロキシのみを使用して接続できます。

If you configure or modify proxy server settings for Windows (Internet Options > LAN Settings), restart the [!DNL Experience Manager] desktop app for the changes to take effect.

>[!NOTE]
>
>プロキシ設定は、デスクトップアプリケーションの開始時にのみ適用されます。変更内容を反映するには、アプリケーションを閉じて再起動します。

プロキシで認証が必要な場合は、IT チームがプロキシサーバー設定で Experience Manager Assets の URL を許可すれば、アプリケーションのトラフィックが通過できるようになります。

## Asset Info ダイアログのカスタマイズ {#customize-the-asset-info-dialog}

Asset Info ダイアログは、次のコンポーネントの一方または両方をオーバーレイすることでカスタマイズできます。

* Granite ユーザーインターフェイスページ（`/libs/dam/gui/content/assets/moreinfo`）。

* HTL の `/css/javascript` コンポーネント（`/libs/dam/gui/components/admin/moreinfo`）。

オーバーレイされるコンポーネントは、カスタマイズの性質によって変わります。Asset Info ダイアログの一部として表示されるコンポーネントを変更するには、Granite ユーザーインターフェイスページをオーバーレイします。ダイアログのHTML、CSSまたはJavaScriptコンテンツを変更するには、HTLコンポーネントをオーバーレイします。

## キャッシュの管理   {#manage-cache}

Windows では、キャッシュは `%LOCALAPPDATA%\Adobe\AssetsCompanion\Cache\` にあります。ここには、デスクトップアプリケーションで設定されている、エンコード済みバージョンの ホストがあります。[!DNL Experience Manager]例えば、`http://localhost:4502` は `http%3A%2F%2Flocalhost%3A4502%2F` と表示されます。

Mac OS X では、同様のディレクトリが `~/Library/Group Containers/group.com.adobe.aem.desktop/cache` にあります。

### キャッシュを管理するアプリケーション内のオプション {#in-app-option-to-manage-cache}

ローカルキャッシュに使用するディスク容量を管理できます。 Assets サーバーのアーティファクトはローカルにキャッシュされ、スムーズに利用することができます。要件に応じてデフォルト設定を変更することができます。キャッシュをクリアして、すべてのアセットを取得し直すこともできます。必要なオプションを設定するには、アプリケーションのアイコンをクリックし、**[!UICONTROL Advanced]**／**[!UICONTROL Manage Cache]** を選択します。

>[!NOTE]
>
>キャッシュをクリアした場合でも、未保存の変更内容は維持されます。Any assets not checked into [!DNL Experience Manager] server are retained and not deleted.

### Windows でのキャッシュの場所の変更 {#change-location-of-cache-on-windows}

The default location of the cache for the [!DNL Experience Manager] desktop app is as follows:

* Windows の場合、`%LocalAppData%\Adobe\AssetsCompanion\Cache\EncodedAEMEndpoint`。

* Mac の場合、`~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/EncodedAEMEndpoint`。

`EncodedAEMEndpoint` は、アプリで設定された [!DNL Experience Manager] エンドポイントのURLです。 The value is an encoded version of the targeting URL of the [!DNL Experience Manager] server. 例えば、アプリケーションのターゲットが `http://localhost:4502` の場合、ディレクトリ名は `http%3A%2F%2Flocalhost%3A4502` となります。この例では、キャッシュディレクトリへの Windows のパスは「`%LocalAppData%\Adobe\AssetsCompanion\Cache\http%3A%2F%2Flocalhost%3A4502`」です。

アプリケーションで異なるフォルダーや異なるドライブをキャッシュの場所として指定するには、アプリケーションの設定ファイルを編集します。

1. デスクトップアプリケーションのインストールディレクトリに移動します。Windows の場合、デフォルトの場所は `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop` です。

1. Adobe Experience Manager Desktop.exe.config ファイルをテキストエディターで編集します。

   このファイルに変更を保存するには、管理者権限が必要です。

1. 文字列「ProxyCacheRoot」を検索します。この値は、キャッシュの場所「`%LocalAppData%\Adobe\AssetsCompanion\Cache`」に設定されています。この値を任意の有効なパスに変更します。

   >[!NOTE]
   >
   >自動的に *&lt;エンコードされた AEM エンドポイント>* サブディレクトリが作成されます。この動作は設定で変更することはできません。

>[!MORELIKETHIS]
* [ [!DNL Experience Manager]  デスクトップアプリケーションの概要](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app.html?lang=ja)。
* [デスクトッ [!DNL Experience Manager] プアプリを使用](use-app-v1.md)。
* [デスクトップアプリの [!DNL Experience Manager] トラブルシューティング](troubleshoot-app-v1.md)。

