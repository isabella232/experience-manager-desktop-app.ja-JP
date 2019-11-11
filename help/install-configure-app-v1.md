---
title: AEMデスクトップアプリケーションバージョン1.xのインストールと設定
seo-title: AEMデスクトップアプリケーションバージョン1.xのインストールと設定
description: AEM Assetsサーバーで動作するようにAEMデスクトップアプリケーションバージョン1.xをインストールして設定し、アセットがデスクトップ上のドライブとしてマウントされるようにマップします。
seo-description: AEM Assetsサーバーで動作するようにAEMデスクトップアプリケーションバージョン1.xをインストールして設定し、アセットがデスクトップ上のドライブとしてマウントされるようにマップします。
uuid: 79bc9de9-5708-41f9-ac43-68c1fd2a2129
contentOwner: asgupta
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f6365302-1690-4719-9b8c-035719422740
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ce29042aff6d4caea0e7b8a56673d4bfed03a45

---


# AEMデスクトップアプリケーションv1.xのインストールと設定 {#install-and-configure-aem-desktop-app}

AEM Assetsサーバーで動作するようにAEMデスクトップアプリケーションをインストールして設定し、アセットをローカルファイルシステムにダウンロードします。 AEMデスクトップアプリケーションを使用するには、

* ご使用のAEMサーバーのバージョンがAEMデスクトップアプリでサポートされていることを確認します。 [互換表](release-notes-of-v1.md#compatibilitymatrix)を参照してください。
* アプリケーションをダウンロードしてインストールします。
* いくつかのアセットを使用して接続をテストします。See [Access and open assets on your desktop](use-app-v1.md#openondesktop).

## 必要システム構成、前提条件およびダウンロードリンク {#system-requirements-prerequisites-and-download-links}

For detailed information, see the [AEM desktop app release notes](release-notes-of-v1.md).

## Install and connect AEM desktop app to AEM server {#install-and-connect-aem-desktop-app-to-aem-server}

For details, see [Install and connect AEM desktop app to AEM server](use-app-v1.md#installandconnect).

>[!NOTE]
>
>AEMデスクトップアプリケーションは、一度に1つのインスタンスのみインストールしてアクティブにすることができます。

## プロキシのサポート {#proxy-support}

AEMデスクトップアプリケーションは、システムの事前定義されたプロキシを使用して、HTTPS経由でインターネットに接続します。 AEM Desktop App は、追加の認証が必要ないネットワークプロキシのみを使用して接続できます。

Windowsのプロキシサーバーの設定を設定または変更する場合（インターネットオプション/LAN設定）、AEMデスクトップアプリケーションを再起動して変更を有効にします。

プロキシで認証が必要な場合は、IT チームがプロキシサーバー設定で AEM Assets の URL をホワイトリストに登録すると、アプリケーションのトラフィックが通過できるようになります。

## ファイルの処理 {#file-handling}

デスクトップアプリケーションがマウントするネットワーク共有の場所からファイルを変更する場合、ファイルは2段階でその場所に保存されます。 第 1 段階では、ファイルがローカルに保存されます。ユーザーは、ファイルを保存し、転送が完了するのを待つことなくそのファイルに対する作業を続けることができます。

第2段階では、デスクトップアプリケーションは、事前に定義された遅延（例えば、30秒）の後で、更新されたファイルをAEMサーバーにアップロードします。 この処理はバックグラウンドで実行されます。「View Asset Status」オプションを使用して、アップロード処理のステータスを表示できます。

1. AEM Assets にアセットをアップロードします。
1. ツールバーでAEMデスクトップアプリケーションアイコンをクリックまたはタップします。
1. メニューから、「View Asset Status」オプションを選択します。
1. ダイアログで、アップロード処理のステータスを確認します。

>[!NOTE]
>
>AEMデスクトップアプリケーションは、最大40 GBのアセットを処理できます。

## Dispatcher の背後にある AEM インスタンスへの接続 {#connect-to-an-aem-instance-behind-a-dispatcher}

Assets API の Copy および Move メソッドでは、次の追加ヘッダーを AEM に引き渡す必要があります。

* X-Destination
* X-Depth
* X-Overwrite

AEM Desktop は、デフォルトポートを含む URL を使用して AEM に接続します。Therefore, the *virtualhosts* setting in the dispatcher configuration should include the default port number. For more information around virtualhosts configuration, see [Identifying Virtual Hosts](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#identifying-virtual-hosts-virtualhosts).

For additional information on configuring the dispatcher to pass through these additional headers, see [Specifying the HTTP Headers](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#specifying-the-http-headers-to-pass-through-clientheaders).

## Asset Info ダイアログのカスタマイズ {#customize-the-asset-info-dialog}

アセット情報ダイアログは、次のコンポーネントのいずれかまたは両方をオーバーレイすることでカスタマイズできます。

* The Granite user interface page at `/libs/dam/gui/content/assets/moreinfo`
* HTLコンポー `/css/javascript` ネントは、 `/libs/dam/gui/components/admin/moreinfo`

オーバーレイされるコンポーネントは、カスタマイズの性質によって変わります。Asset Info ダイアログの一部として表示されるコンポーネントを変更するには、Granite ユーザーインターフェイスページをオーバーレイします。ダイアログの HTML／CSS／JavaScript コンテンツを変更するには、HTL コンポーネントをオーバーレイします。

## キャッシュの管理 {#manage-cache}

On Windows, the cache is at `%LOCALAPPDATA%\Adobe\AssetsCompanion\Cache\`, where is an encoded version of the AEM host configured in the desktop app. 例えば、は、と表 `http://localhost:4502` 示されま `http%3A%2F%2Flocalhost%3A4502%2F`す。

On Mac OS X, a similar directory is at `~/Library/Group Containers/group.com.adobe.aem.desktop/cache`.

### キャッシュを管理するアプリケーション内のオプション {#in-app-option-to-manage-cache}

ローカルキャッシュに使用するディスク容量を管理できます。AEM Assets サーバーのアーティファクトはローカルにキャッシュされ、スムーズに利用することができます。要件に応じてデフォルト設定を変更することができます。キャッシュをクリアして、すべてのアセットを取得し直すこともできます。To set the desired options, click the application's icon and click **[!UICONTROL Advanced]** &gt; **[!UICONTROL Manage Cache]**. ****

>[!NOTE]
>
>キャッシュをクリアした場合でも、未保存の変更内容は維持されます。AEM サーバーにチェックインしていないアセットは、削除されずにそのまま保持されます。

### Windows でのキャッシュの場所の変更 {#change-location-of-cache-on-windows}

AEMデスクトップアプリケーションのキャッシュのデフォルトの場所は次のとおりです。

* Windows: `%LocalAppData%\Adobe\AssetsCompanion\Cache\EncodedAEMEndpoint`
* Mac: `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/EncodedAEMEndpoint`

`EncodedAEMEndpoint` は、AEMデスクトップアプリの設定済みAEMエンドポイントのURLです。 この値は、AEM サーバーのターゲットとなる URL のエンコードされたバージョンです。For example, if the application is targeting `http://localhost:4502`, the directory name is `http%3A%2F%2Flocalhost%3A4502`. この例のキャッシュディレクトリへのWindowsパスは、%LocalAppData%\Adobe\AssetsCompanion\Cache\http%3A%2F%2Flocalhost%3A4502です。

アプリケーションで異なるフォルダーや異なるドライブをキャッシュの場所として指定するには、アプリケーションの設定ファイルを編集します。

1. アプリケーションのインストールディレクトリに移動します。 Windowsのデフォルトの場所はです `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop`。
1. Adobe Experience Manager Desktop.exe.config ファイルをテキストエディターで編集します。

   このファイルに対する変更を保存するには、管理者権限が必要です。

1. 文字列「ProxyCacheRoot」を検索します。この値は、キャッシュの場所「%LocalAppData%\Adobe\AssetsCompanion\Cache」に設定されています。この値を任意の有効なパスに変更します。

   >[!NOTE]
   >
   >The app automatically creates an *&lt;Encoded AEM Endpoint&gt;* subdirectory; this behavior is not configurable.

## その他のリソース {#additional-resources}

* [AEMデスクトップアプリの概要](https://helpx.adobe.com/experience-manager/kt/eseminars/ccoo-aem-desktop-app.html)
* [AEMデスクトップアプリを使用する](use-app-v1.md)

* [AEMデスクトップアプリケーションでのチェックイン/チェックアウトについて理解する](https://helpx.adobe.com/experience-manager/kt/assets/using/checkin-checkout-technical-video-understand.html)
* [AEM Assetsでのデスクトップアプリの使用](https://helpx.adobe.com/experience-manager/kt/assets/using/checkin-checkout-technical-video-understand.html)
* [AEMデスクトップアプリケーションのトラブルシューティング](troubleshoot-app-v1.md)