---
title: デスクトップアプリケーション v1.10 のインストールと設定
description: ' [!DNL Experience Manager] desktop app version 1.10 to work with [!DNL Assets]  サーバーをインストールして設定し、アセットをデスクトップ上にドライブとしてマウントするようにマッピングします。'
exl-id: 7f3bdfb1-d345-4e48-b020-6e06531f46f2
source-git-commit: 78f18e68178f711d925d7e308822c657087d009a
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 100%

---

# [!DNL Experience Manager] デスクトップアプリケーション v1.10 のインストールと設定 {#install-and-configure-aem-desktop-app}

[!DNL Experience Manager] デスクトップアプリケーションを使用すると、[!DNL Experience Manager] 内のアセットにローカルデスクトップから手軽にアクセスし、任意のデスクトップアプリケーションで利用できるようになります。アセットは Mac Finder や Windows エクスプローラーで容易に表示したり、デスクトップアプリケーションで開いたり、ローカルで変更したりできます。変更したアセットをアップロードすると、変更内容が [!DNL Experience Manager] に保存され、リポジトリー内に新しいバージョンが作成されます。

このような統合により、組織内の様々な役割のユーザーが Assets でアセットを一元管理し、Creative Cloud やその他のアプリケーションからアセットにアクセスできるようになります。さらに、ブランディングなど様々な基準に準拠することが容易になります。

[!DNL Experience Manager] デスクトップアプリケーションを使用するには、次の手順に従います。

* [!DNL Experience Manager] サーバーのバージョンが [!DNL Experience Manager] デスクトップアプリケーションでサポートされていることを確認します。[互換表](release-notes-of-v1.md#compatibilitymatrix)を参照してください。

* アプリケーションをダウンロードしてインストールします。

* いくつかのアセットを使用して接続をテストします。詳しくは、[デスクトップでのアセットへのアクセスとオープン](use-app-v1.md#openondesktop)を参照してください。

## 必要システム構成、前提条件およびダウンロードリンク {#system-requirements-prerequisites-and-download-links}

詳しくは、[[!DNL Experience Manager] Adobe デスクトップアプリケーションリリースノート](release-notes-of-v1.md)を参照してください。

## デスクトップアプリケーションのインストールと [!DNL Experience Manager] サーバーへの接続 {#install-and-connect-aem-desktop-app-to-aem-server}

詳しくは、[ [!DNL Experience Manager] desktop app to [!DNL Experience Manager] サーバーのインストールと接続](use-app-v1.md#installandconnect)を参照してください。

>[!NOTE]
>
>インストールして一度にアクティブ化できる [!DNL Experience Manager] デスクトップアプリケーションのインスタンスは 1 つだけです。

## ファイルの処理 {#file-handling}

デスクトップアプリケーションによってマウントされたネットワーク共有の場所からファイルを変更した場合、ファイルは 2 つの段階を経てその場所に保存されます。第 1 段階では、ファイルがローカルに保存されます。ユーザーは、ファイルを保存し、転送が完了するのを待つことなくそのファイルに対する作業を続けることができます。

第 2 段階では、事前定義された時間（例：30 秒）の経過後に、更新されたファイルが [!DNL Experience Manager] サーバーにアップロードされます。この処理はバックグラウンドで実行されます。「View Asset Status」オプションを使用して、アップロード処理のステータスを表示できます。

1.  Assets にアセットをアップロードします。

1. ツールバーの [!DNL Experience Manager] デスクトップアプリケーションアイコンをクリックします。

1. メニューから、「View Asset Status」オプションを選択します。

1. ダイアログで、アップロード処理のステータスを確認します。

>[!NOTE]
>
>[!DNL Experience Manager] デスクトップアプリケーションは、最大 40 GB のアセットを処理できます。

## Dispatcher の背後にある [!DNL Experience Manager] インスタンスへの接続 {#connect-to-an-aem-instance-behind-a-dispatcher}

Assets API のコピーおよび移動メソッドでは、次の追加ヘッダーを [!DNL Experience Manager] に引き渡す必要があります。

* X-Destination
* X-Depth
* X-Overwrite

[!DNL Experience Manager] デスクトップアプリケーションは、デフォルトポートを含む URL を使用して [!DNL Experience Manager] に接続します。したがって、Dispatcher 設定の `virtualhosts` の設定にデフォルトポート番号を含める必要があります。`virtualhosts` の設定について詳しくは、[仮想ホストの識別](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=ja#identifying-virtual-hosts-virtualhosts)を参照してください。

これらの追加ヘッダーを引き渡すように Dispatcher を設定する方法について詳しくは、[HTTP ヘッダーの指定](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=ja#specifying-the-http-headers-to-pass-through-clientheaders)を参照してください。

### プロキシのサポート {#proxy-support}

[!DNL Experience Manager] デスクトップアプリケーションは、システムで事前に定義されたプロキシ経由で、HTTPS を使用してインターネットに接続します。AEM デスクトップアプリケーションは、追加の認証が必要ないネットワークプロキシのみを使用して接続できます。

Windows のプロキシサーバー設定（インターネットオプション／LAN の設定）を設定または変更した場合、変更内容を反映するには、[!DNL Experience Manager] デスクトップアプリケーションを再起動します。

>[!NOTE]
>
>プロキシ設定は、デスクトップアプリケーションの開始時にのみ適用されます。変更内容を反映するには、アプリケーションを閉じて再起動します。

プロキシで認証が必要な場合は、IT チームがプロキシサーバー設定で Experience Manager Assets の URL を許可すれば、アプリケーションのトラフィックが通過できるようになります。

## Asset Info ダイアログのカスタマイズ {#customize-the-asset-info-dialog}

Asset Info ダイアログは、次のコンポーネントの一方または両方をオーバーレイすることでカスタマイズできます。

* Granite ユーザーインターフェイスページ（`/libs/dam/gui/content/assets/moreinfo`）。

* HTL の `/css/javascript` コンポーネント（`/libs/dam/gui/components/admin/moreinfo`）。

オーバーレイされるコンポーネントは、カスタマイズの性質によって変わります。Asset Info ダイアログの一部として表示されるコンポーネントを変更するには、Granite ユーザーインターフェイスページをオーバーレイします。ダイアログの HTML、CSS、JavaScript コンテンツを変更するには、HTL コンポーネントをオーバーレイします。

## キャッシュの管理     {#manage-cache}

Windows では、キャッシュは `%LOCALAPPDATA%\Adobe\AssetsCompanion\Cache\` にあります。ここには、デスクトップアプリケーションで設定されている、エンコード済みバージョンの [!DNL Experience Manager] ホストがあります。例えば、`http://localhost:4502` は `http%3A%2F%2Flocalhost%3A4502%2F` と表示されます。

Mac OS X では、同様のディレクトリが `~/Library/Group Containers/group.com.adobe.aem.desktop/cache` にあります。

### キャッシュを管理するアプリケーション内のオプション {#in-app-option-to-manage-cache}

ローカルキャッシュに使用するディスク容量を管理できます。Assets サーバーのアーティファクトはローカルにキャッシュされ、スムーズに利用することができます。要件に応じてデフォルト設定を変更することができます。キャッシュをクリアして、すべてのアセットを取得し直すこともできます。必要なオプションを設定するには、アプリケーションのアイコンをクリックし、**[!UICONTROL Advanced]**／**[!UICONTROL Manage Cache]** を選択します。

>[!NOTE]
>
>キャッシュをクリアした場合でも、未保存の変更内容は維持されます。[!DNL Experience Manager] サーバーにチェックインしていないアセットは、削除されずにそのまま保持されます。

### Windows でのキャッシュの場所の変更  {#change-location-of-cache-on-windows}

[!DNL Experience Manager] デスクトップアプリケーションのキャッシュのデフォルトの場所は次のとおりです。

* Windows の場合、`%LocalAppData%\Adobe\AssetsCompanion\Cache\EncodedAEMEndpoint`。

* Mac の場合、`~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/EncodedAEMEndpoint`。

`EncodedAEMEndpoint` は、アプリに設定された [!DNL Experience Manager] エンドポイント URL です。この値は、[!DNL Experience Manager] サーバーのターゲット URL のエンコードされたバージョンです。例えば、アプリケーションのターゲットが `http://localhost:4502` の場合、ディレクトリ名は `http%3A%2F%2Flocalhost%3A4502` となります。この例では、キャッシュディレクトリへの Windows のパスは「`%LocalAppData%\Adobe\AssetsCompanion\Cache\http%3A%2F%2Flocalhost%3A4502`」です。

アプリケーションで異なるフォルダーや異なるドライブをキャッシュの場所として指定するには、アプリケーションの設定ファイルを編集します。

1. デスクトップアプリケーションのインストールディレクトリに移動します。Windows の場合、デフォルトの場所は `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop` です。

1. Adobe Experience Manager Desktop.exe.config ファイルをテキストエディターで編集します。

   このファイルに変更を保存するには、管理者権限が必要です。

1. 文字列「ProxyCacheRoot」を検索します。この値は、キャッシュの場所「`%LocalAppData%\Adobe\AssetsCompanion\Cache`」に設定されています。この値を任意の有効なパスに変更します。

   >[!NOTE]
   >
   >自動的に *&lt;エンコードされた AEM エンドポイント>* サブディレクトリが作成されます。この動作は設定で変更することはできません。

>[!MORELIKETHIS]
* [ [!DNL Experience Manager]  デスクトップアプリケーションの概要](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app.html?lang=ja)
* [ [!DNL Experience Manager]  デスクトップアプリケーションの使用](use-app-v1.md)
* [ [!DNL Experience Manager]  デスクトップアプリケーションのトラブルシューティング](troubleshoot-app-v1.md)

