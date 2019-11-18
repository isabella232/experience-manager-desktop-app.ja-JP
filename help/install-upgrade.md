---
title: AEMデスクトップアプリケーションのインストールと設定
description: AEM Assetsサーバーで動作するようにAEMデスクトップアプリケーションをインストールして設定し、ローカルファイルシステムにアセットをダウンロードします。
uuid: 79bc9de9-5708-41f9-ac43-68c1fd2a2129
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f6365302-1690-4719-9b8c-035719422740
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 850d2c21a796599ed40164e7d6f892967563c16b

---


# AEMデスクトップアプリケーションのインストール {#install-app-v2}

## システム要件 {#tech-specs-v2}

For detailed information, see the [AEM desktop app release notes](release-notes.md).

## アプリケーションv1.xからアプリケーションv2へのアップグレード {#upgrade-from-previous-version}

既存のアプリのユーザーの場合は、以前のバージョンと最新バージョンのアプリの相違点と類似点を把握します。 また、v1.xから最新バージョンに移行するには、次のガイドラインに従います。

>[!NOTE]
>
>デスクトップアプリケーションv1.xとv2は、1台のマシン上に共存できません。 バージョンをインストールする前に、他のバージョンをアンインストールします。

v1.xから最新バージョンのアプリケーションにアップグレードするには、次の手順に従います。

1. アップグレードする前に、すべてのアセットを同期します。 アプリケーションv1.xを使用して、すべての変更をアップロードします。これにより、アプリケーションv1.xのアンインストール時に変更内容が失われるのを防ぐことができます。
1. アプリケーションv1.xをアンインストールします。v1.xをアンインストールする場合は、キャッシュをクリアします。
1. マシンを再起動します。
1. 最新のアプリケーションをダウンロードしてインストールします。 次の手順に従ってください。

##  のインストール{#install-v2}

デスクトップアプリケーションをインストールするには、次の手順に従います。 最新のアプリケーションをインストールする前に、既存のAdobe Experience Managerデスクトップアプリケーションv1.xをアンインストールします。 詳しくは、上記を参照してください。

1. AEMデプロイメントのURLと秘密鍵証明書を手元に置いておきます。
1. AEM 6.4.4以降またはAEM 6.5.0以降を使用している場合は、この手順をスキップします。 AEMの設定が、リリースノートに記載されている互換性要件を満たしていることを確認します。 必要に応じて、該当する互換性パッケ [ージをダウンロードし](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) 、AEM管理者としてAEM Package Managerを使用してインストールします。 To install a package, see [How to work with Packages](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html).
1. インストーラーのバイナリを実行し、画面の指示に従ってインストールします。
1. Windowsでは、インストーラーがインストールを求めるプロンプトが表示される場合があり `Visual Studio C++ Redistributable 2015`ます。 画面の指示に従ってインストールします。 インストールに失敗した場合は、手動でインストールします。 インストーラーをここからダウンロ [ードし](https://www.microsoft.com/en-us/download/details.aspx?id=52685) 、との両方のファイルをイ `vc_redist.x64.exe` ンストー `vc_redist.x86.exe` ルします。 AEMデスクトップアプリケーションのインストーラーを再実行します。
1. 指示に従ってマシンを再起動します。 デスクトップアプリを起動して設定します。
1. アプリケーションをAEMリポジトリと接続するには、トレイのアプリケーションアイコンをクリックしてアプリケーションを起動します。 AEMインスタンスのアドレスを指定します。 をクリック **[!UICONTROL Connect]** し、資格情報を入力します。

   ![デスクトップアプリケーションの入力サーバーアドレスへの接](assets/connect_da2.png "続画面入力サーバーアドレスへの接続画面")

   >[!C自動]
   >
   >AEMサーバーのアドレスの前後に、先頭または末尾に空白がないことを確認します。 そうしないと、アプリはAEMサーバーに接続できません。

1. 接続が成功すると、AEM DAMのルートフォルダーで使用可能なフォルダーとアセットのリストを表示できます。 アプリ内からフォルダーを参照できます。

   ![ログイン時にアプリはDAMのコンテンツを表示し](assets/firstview_da2.png "ます。ログイン時にアプリはDAMのコンテンツを表示します")

1. （AEM 6.5.1以降）AEM 6.5.1以降でデスクトップアプリケーションを使用している場合は、S3またはAzureコネクタをバージョン1.10.4以降にアップグレードします。 「 [Azure Connector](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html#AzureDataStore) 」または「 [S3 Connector](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html#AmazonS3DataStore)」を参照してください。

   アドビ管理サービス(AMS)のお客様は、アドビカスタマーケアにお問い合わせください。

## 環境設定の指定 {#set-preferences}

環境設定を変更するには、「その他のオプション」アイコ ![ンと「環境設定](assets/do-not-localize/more_options_da2.png) 」アイコ **[!UICONTROL Preference]** ンをク ![リックしま](assets/do-not-localize/preferences_icon_da2.png)す。 ウィンドウ **[!UICONTROL Preferences]** で、次の値を調整します。

* [!UICONTROL Launch application on login].
* [!UICONTROL Show window when application starts].
* **[!UICONTROL Cache Directory]**:アプリのローカルキャッシュの場所（ローカルにダウンロードされたアセットが含まれます）。
* **[!UICONTROL Network Drive Letter]**:AEM DAMへのマッピングに使用するドライブ文字。 不明な場合は、この設定を変更しないでください。 アプリはWindowsの任意のドライブ文字にマップできます。 2人のユーザーが異なるドライブ文字のアセットを配置した場合、相互に配置されたアセットは表示されません。 アセットのパスが変更されます。 アセットはバイナリファイル（INDDなど）に残り、削除されません。 アプリには、使用可能なすべてのドライブ文字が一覧表示され、デフォルトでは、通常は最後に使用可能な文字が使用されま `Z`す。
* **[!UICONTROL Maximum Cache Size]**:ローカルにダウンロードしたアセットの保存に使用する、ハードディスク上の許可されたキャッシュ(GB)。
* **[!UICONTROL Current cache size]**:ローカルにダウンロードしたアセットのストレージサイズ。 情報は、アプリを使用してアセットをダウンロードした後にのみ表示されます。
* **[!UICONTROL Automatically download linked assets]**:サポート対象のネイティブCreative cloudアプリケーションに配置されたアセットは、元のファイルをダウンロードすると自動的に取得されます。
* **[!UICONTROL Maximum number of downloads]**:初めて（「表示」、「開く」、「編集」、「ダウンロード」などのオプションを使用して）アセットをダウンロードする場合、バッチに含まれる数がこの数より少ない場合にのみ、アセットがダウンロードされます。 デフォルト値は 50 です。不明な場合は変更しないでください。 値を増やすと、待ち時間が長くなり、値を減らすと、必要なアセットやフォルダーを1回でダウンロードできなくなる場合があります。

使用できない環境設定を更新するには、AEMサーバーからログアウトします。 環境設定を更新した後、「環境設定を保存 ![」をクリックし](assets/do-not-localize/save_preferences_da2.png) 、変更を保存します。

![AEMデスクトップアプリの環境設定デスクト](assets/preferences_da2.png "ップアプリの環境設定")

## アプリのアンインストール {#uninstall-the-app}

Windowsでアプリケーションをアンインストールするには、次の手順に従います。

1. AEMにすべての変更をアップロードして、編集内容が失われないようにします。 詳しくは、ア [セットの編集と更新済みアセットのAEMへのアップロードを参照してください](using.md#edit-assets-upload-updated-assets)。 ログオフしてアプリ [!UICONTROL Exit] を作成します。
1. 他のOSアプリケーションを削除する際に、アプリケーションを削除します。 Windowsの[プログラムの追加と削除]からアンインストールします。
1. キャッシュとログを削除するには、必要なチェックボックスをオンにします。
   ![ログを削除するためのアンインストールダイアログとキャッシュログを削](assets/uninstall_da2.png "除するためのアンインストールダイアログログとキャッシュを削除する")
1. 画面の指示に従います。 完了したら、コンピューターを再起動します。

Macでアプリケーションをアンインストールするには、次の手順に従います。

1. AEMにすべての変更をアップロードして、編集内容が失われないようにします。 詳しくは、ア [セットの編集と更新済みアセットのAEMへのアップロードを参照してください](using.md#edit-assets-upload-updated-assets)。 ログオフしてアプリ [!UICONTROL Exit] を作成します。
1. からを削 `Adobe Experience Manager Desktop.app` 除します `/Applications`。

また、Mac上の内部アプリケーションキャッシュを消去し、アプリケーションをアンインストールするには、ターミナルで次のコマンドを実行します。
`/Applications/Adobe Experience Manager Desktop/Contents/Resources/uninstall-osx/uninstall.sh`
