---
title: AEMデスクトップアプリケーションバージョン1.xを使用する
seo-title: Adobe Experience Managerデスクトップアプリケーションバージョン1.xを使用する
description: Adobe Experience Managerデスクトップアプリケーションバージョン1.xの使用方法と、デスクトップでのアセットの操作を最適化する方法について説明します。
seo-description: Adobe Experience Managerデスクトップアプリケーションバージョン1.xの使用方法と、デスクトップおよびクリエイティブワークフローでのアセットの使用を最適化する方法について説明します。
uuid: 55057617-89de-43cd-8419-1252a42ab2fb
contentOwner: asgupta
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 39d7bcad-d7b0-4978-a790-4cb68b8a7d6a
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c305f57b8ad874bcffc250689d917e31820225e4

---


# AEMデスクトップアプリケーションv1.xを使用する {#use-aem-desktop-app-v1x}

AEM Desktop App を使用すると、AEM 内のアセットにローカルデスクトップから手軽にアクセスし、任意のデスクトップアプリケーションで利用できるようになります。アセットは、Mac finderまたはWindowsエクスプローラーで簡単に表示でき、デスクトップアプリケーションで開いてローカルで変更できます。変更内容は、リポジトリで作成された新しいバージョンでAEMに保存されます。

このような統合により、組織内の様々な役職のスタッフが AEM Assets でアセットを一元管理し、Creative Cloud やその他のアプリケーションからアセットにアクセスできるようになります。さらに、ブランディングなど様々な基準に準拠することが容易になります。

AEMデスクトップアプリケーションv1を使用して行う主なタスクは次のとおりです。

* [AEM サーバーと接続する](#installandconnect)

* [アセットをデスクトップで直接開く](#openondesktop)
* [アセットをデスクトップから編集およびチェックアウトする](#workonassets)

* [アセットおよびフォルダーを一括アップロードする](#bulkupload)

様々な推奨事項や注意事項については、[AEM Desktop App を使用する際のベストプラクティス](best-practices-for-v1.md)を参照してください。AEM Desktop App を使用する際に問題が発生した場合は、[AEM Desktop App のトラブルシューティング](troubleshoot-app-v1.md)を参照してください。

>[!NOTE]
>AEMデスクトップアプリはAEM 6.1リリースで導入され、AEM Assets Companion Appと呼ばれました。

## クリエイティブワークフローでの AEM Desktop App のタッチポイント {#aem-desktop-app-touch-points-in-the-creative-workflow}

AEM Desktop App および AEM Assets はクリエイティブワークフローで統合され、以下のタッチポイントが提供されます。

![クリエイティブワークフローでの AEM Desktop App のタッチポイント](assets/aem_desktopapp_workflow.png)

クリエイティブワークフローでの AEM Desktop App のタッチポイント

## Install and connect AEM desktop app to AEM server {#installandconnect}

クリエイティブアセットの作成または編集を開始する前に、リポジトリのアセットをダウンロードおよびアップロードするために AEM Desktop App を AEM Assets サーバーに接続します。以下の作業をおこないます。

1. [アプリをインストールします](#installapp)。
1. [環境設定](#inapppref)および接続の詳細を設定します。
1. [AEM サーバーに接続](#connect)し、アセットリポジトリをローカルドライブとしてマウントします。
1. AEM サーバーで[「デスクトップアクション」を有効にします。](#desktopactions)

AEMデスクトップアプリケーションは、HTTPS接続を使用してAEMサーバーに接続し、堅牢かつ安全にアセットを転送します。

>[!NOTE]
>インストールおよび設定手順の一部または全体で、AEM 管理者またはシステム管理者のサポートが必要になることがあります。

### アプリケーションのインストール {#installapp}

AEMデスクトップアプリを使用するには、ご使用のAEMサーバーのバージョンがAEM Desktopアプリでサポートされていることを確認します。 使用するオペレーティングシステム（Mac または Windows）に適したインストールファイル（バイナリ）をダウンロードして、アプリケーションをインストールします。

詳細な設定は、ネットワークとシステムの環境設定に応じて必要になる場合があります。 詳しくは、[AEM Desktop App のインストールと設定](install-configure-app-v1.md)を参照してください。

1. Go to the [AEM Desktop app download page](https://helpx.adobe.com/experience-manager/kb/download-companion-app.html) and download the appropriate binary for your operating system.
1. ダウンロードしたインストールファイルを実行し、画面上の指示に従ってアプリケーションをインストールします。

   >[!NOTE]
   >AEMデスクトップアプリケーションは、一度に1つのインスタンスのみインストールしてアクティブにすることができます。

### アプリケーション内のオプションと環境設定について {#inapppref}

アプリケーションでは、AEM サーバーとの接続および切断、アップロードのステータスの表示、ローカルキャッシュの管理などの設定をおこなうことができます。通常は、デフォルト設定で使用することができます。必要に応じて、アプリケーションや AEM サーバーとの統合について詳細な設定をおこなうことができます。以下では、様々な設定について詳しく説明します。

**Explore Assets** AEM Assetsリポジトリがマウントされているローカルドライブを開きます。 つまり、ローカルマシンで利用できるようになったアセットを参照します。

**アセットのステータスの表示** ：変更したアセットがアップロードされるか、新しいアセットがAEM Assetsリポジトリに追加されると、アプリケーションはバックグラウンドでアセットをアップロードします。 バックグラウンドで処理されるので、サイズの大きいアセットでもアップロード完了まで待つ必要がなくなり、円滑な作業が可能になります。ユーザーは変更内容をローカルで保存するだけで、他に何かする必要はありません。これらのアセットをアプリケーションからサーバーに送信するには、ある程度の時間がかかります（利用可能な帯域幅によります）。アップロードのステータスや、その他いくつかの基本情報を確認できます。

**オプション** AEM Desktop App Trayから「オプション」をクリックまたはタップして設定にアクセスし、システム起動時にアプリケーションを起動します。をクリックします。およびを使用して、マウント後にAEM Assetsを使用できるローカルドライブ文字を変更します。

**詳細/キャッシュの管理** ：ローカルキャッシュの目的で使用できるディスク領域の量を制御できます。 AEM Assets サーバーのアーティファクトはローカルにキャッシュされ、スムーズに利用することができます。要件に応じてデフォルト設定を変更することができます。キャッシュをクリアして、すべてのアセットを取得し直すこともできます。キャッシュをクリアした場合でも、未保存の変更内容は維持されます。AEM サーバーにチェックインしていないアセットは、削除されずにそのまま保持されます。

### AEM サーバーへの接続 {#connect}

アプリは、Windows および Mac のプロキシ設定をサポートします。設定はアプリの起動時に読み込まれます。プロキシ設定を変更した場合は、変更を適用するためにアプリを再起動します。

>[!NOTE]
>
>プロキシ設定を変更した場合は、アプリを再起動して変更を有効にします。 それ以外の場合、アプリは以前に設定したプロキシサーバーを引き続き使用します。

1. AEM Desktop App を起動します。To map your AEM instance with the app, specify your AEM server in the format `https://[aem-server-url]:[port]`.

   ![Mac での認証と AEM サーバー URL の提供](assets/aem_desktop_app_server_url.png)

1. ログイン画面で、インスタンスのユーザー名とパスワードを指定します。To specify an alternate AEM instance, select the **[!UICONTROL Alternate Login URL]** option.

   ![AEM Desktop App のログイン画面での AEM サーバーの資格情報の入力](assets/chlimage_1-2.png)

### AEM Web インターフェイスでのデスクトップアクションの有効化 {#desktopactions}

ブラウザーの Assets UI から、アセットの場所を参照したり、アセットをチェックアウトしてデスクトップアプリケーションで編集用に開くことができます。これらのオプションはデスクトップアクションと呼ばれており、デフォルトでは有効になっていません。デスクトップアクションを有効にするには、以下の手順に従います。

1. In the Assets console, click/tap the **User** icon from the toolbar.
1. をクリック/タップして、 **[!UICONTROL My Preferences]** ダイアログを表示 **[!UICONTROL Preferences]** します。
1. ユーザ環境設定ダイアログで、を選択しま **[!UICONTROL Show Desktop Actions For Assets]**&#x200B;す。 クリック/タップしま **[!UICONTROL Accept]**&#x200B;す。

   ![「アセットのデスクトップアクションを表示」をチェックしてデスクトップアクションを有効化](assets/chlimage_1-3.png)

   「アセットのデスクトップアクションを表示」をチェックしてデスクトップアクションを有効化

## デスクトップでのアセットへのアクセスとオープン {#openondesktop}

>[!NOTE]
>On Windows, the [default Windows 7 setting](https://support.microsoft.com/en-us/kb/2668751) prevents AEM desktop app from handling assets that are larger than 50 MB.

### AEM Web インターフェイスからマッピングされたアセットの場所の表示 {#reveal-the-location-of-mapped-assets-from-aem-web-interface}

AEM Assets リポジトリをローカルドライブにマッピングした後で、マッピングされたアセットとフォルダーに対して追加のアイコンと「フォルダーのアップロード」機能が表示されるように設定できます。

1. AEM Assets インターフェイスを開き、フォルダーまたはアセットの上にマウスポインターを置くと、デスクトップアクションがカード表示のクイックアクションとして表示されます。

   ![Assets UI でクイックアクションメニューを開き、デスクトップアクションを表示](assets/chlimage_1-4.png)

   Assets UI でクイックアクションメニューを開き、デスクトップアクションを表示

   These desktop actions are also available when you click/tap the **Desktop Actions** icon in the toolbar after selecting the asset or from the toolbar in the asset page.

1. To open the asset in the desktop application that is associated with the specific file extension, click/tap the **Open on desktop** quick action ![Open on Desktop icon](assets/aemassets_icon_openondesktop.png).

   または、ツールバーの&#x200B;**デスクトップアクション**&#x200B;メニューから「**開く**」を選択します。

1. Click/tap the **Reveal** quick action ![Reveal icon](assets/aemassets_reveal_icon.png) to locate the particular asset on your local file system.

   Alternatively, choose **Reveal** from the **Desktop Actions** menu in the toolbar.

### Finder またはエクスプローラーから AEM アセットを開く {#open-aem-assets-from-the-finder-or-the-explorer}

Mac の場合は、コンテキストメニューで「Open」を選択し、AEM Desktop App を通してアセットを開きます。

Adobe InDesign（INDD）ファイルでは、コンテキストメニューで「**[!UICONTROL Open]」を選択します。**&#x200B;このオプションをクリックすると、リンクされたアセットがローカルファイルシステムにダウンロードされ、Adobe inDesignでINDDファイルが開きます。 この方法を使用すると、INDDファイルの編集時に必要なアセットをローカルで使用できるようになります。

Windows の場合は、コンテキストメニューで「Open on Web」を選択してアセットを開きます。アセットの状態ウィンドウで、「デスクトップで開く」アイコ ![ンをクリックまたはタップし](assets/aemassets_icon_openondesktop.png) 、アセットを開きます。

![AEM Desktop App を使用してアセットにアクセスして開くためのコンテキストメニューオプション](assets/aem_desktopapp_mac_context_menu.png)

AEM Desktop App を使用してアセットにアクセスして開くためのコンテキストメニューオプション

### アセットのステータスについて {#understand-the-asset-statuses}

| ![Windowsの既定のアプリアイコン](assets/win_default.png) | AEM Desktop App はサーバーに接続されており、すべてのアセットが同期されています。 |
|------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| ![Windows無効アイコン](assets/win_disabled.png) | AEM Desktop App は起動されていますが、サーバーに接続されていません。一部のアセットの同期が保留されている可能性があります。 |
| ![Windowsファイル同期アイコン](assets/win_sync.png) | アセットの同期中です。ファイルはアップロード中またはダウンロード中です。Asset Status ウィンドウで、ステータスの詳細を確認し、転送を一時停止できます。 |
| ![Windows再接続アイコン](assets/win_refresh.png) | AEM Desktop App は再接続を試みています。ネットワークの問題が発生し、切断された可能性があります。 |

## アセットの操作 {#workonassets}

### AEM Web インターフェイスからのアセットのチェックアウト {#check-out-assets-from-the-aem-web-interface}

AEM Assets では、編集のためにアセットをチェックアウトし、変更終了後にアセットをチェックインすることができます。アセットをチェックアウトした後は、その人だけがアセットを編集、注釈、公開、移動、削除できるようになります。アセットをチェックアウトすると、アセットがロックされ、他のユーザーがこれらの操作を実行できなくなります。 アセットをチェックイン／チェックアウトするには、アセットへの書き込み権限が必要です。

AEM Web インターフェイスからアセットをチェックアウトするには、2 つの方法があります。1 つ目の方法について詳しくは、[Assets UI からのファイルのチェックインとチェックアウト](https://helpx.adobe.com/in/experience-manager/6-4/assets/using/check-out-and-submit-assets.html)を参照してください。AEM Desktop App がインストールされている場合にアセットをチェックアウトして開く 2 つ目の方法を使用するには、以下の手順に従います。

1. AEM Assets インターフェイスを開き、フォルダーまたはアセットの上にマウスポインターを置くと、デスクトップアクションがカード表示のクイックアクションとして表示されます。

   ![カード表示のプロパティオプション](assets/chlimage_1-4.png)

   これらのデスクトップアクションは、アセットを選択した後のツールバー、またはアセットページにあるツールバーの「デスクトップアクション」アイコンをクリックまたはタップしても使用できます。

1. To open the asset, click/tap the Open on desktop quick action ![Open on Desktop icon](assets/aemassets_icon_openondesktop.png).

   または、ツールバーのデスクトップアクションメニューから「開く」を選択します。

   >[!NOTE]
   >開いただけでチェックアウトしていないファイルを編集した場合、他のユーザーにはそのアセットが更新されていることは通知されません。

1. To open an asset for editing in an Adobe Creative Cloud application, click/tap the Edit desktop quick action ![Edit Desktop icon](assets/aemassets_icon_editdesktop.png). また、これにより、アセットが編集用にチェックアウトされます。 編集が終了したら、アセットをチェックインして、AEM Assets で変更を更新します。

   または、ツールバーのデスクトップアクションメニューから「編集」を選択します。

1. [開く]メニューオプションを選択します。 選択したアセットがプレビューモードで開きます。
1. アセットを編集するには、「編集」オプションを選択します。 選択したアセットが編集モードで開きます。

### アセットのチェックアウト（Mac の場合） {#check-out-assets-on-mac}

アプリでは、アセットファイルをチェックアウトして、作業中のファイルを他のユーザーが変更できないようにすることができます。

1. Macのコンテキストメニューで、「AEM Assetsフォルダーを開く」を選択してFinderを開きます。

   ![AEM Desktop App を使用してアセットにアクセスして開くためのコンテキストメニューオプション](assets/aem_desktopapp_mac_context_menu.png)

   AEM Desktop App を使用してアセットにアクセスして開くためのコンテキストメニューオプション

1. チェックアウトするアセットに移動します。

   ![MacでAEM Assetsのコンテキストメニューで開く](assets/chlimage_1-5.png)

1. アセットを右クリックし、コンテキストメニューの「More Assets Info」を選択します。
1. アセット情報ダイアログで、「チェックアウト」アイコンをクリックまたはタップして、アセットをチェックアウトします。 「チェックアウト」アイコンは、クリックまたはタップすると、チェックインアイコンに切り替わります。

   ![チェックアウトするアセットを参照](assets/chlimage_1-6.png)

1. 他のユーザーが使用できるようにアセットをチェックインするには、Asset Info ダイアログの「Checkin」アイコンをクリックまたはタップします。

### アセットのチェックアウト（Windows の場合） {#check-out-assets-on-windows}

アプリでは、アセットファイルをチェックアウトして、作業中のファイルを他のユーザーが変更できないようにすることができます。

1. コンテキストメニューの「Explore Assets」を選択してエクスプローラーを開きます。
1. エクスプローラーで、チェックアウトするアセットの場所に移動します。

   ![チェックアウトアイコンの切り替え](assets/chlimage_1-7.png)

1. アセットを右クリックし、コンテキストメニューの「Open on Web」を選択します。
1. Asset Info ダイアログで、「Checkout」アイコンをクリックまたはタップします。「チェックアウト」アイコンが「チェックイン」アイコンに切り替わります。

   ![チェックアウトアイコンの切り替え](assets/chlimage_1-8.png)

1. エクスプローラーでアセットを確認します。The lock icon on the asset ![Asset lock icon](assets/aemassets_icon_lockcheckout.png) indicates that you have checked out the asset.

   >[!NOTE]
   >ロックアイコンは、数分遅れて表示される場合があります。AEM Desktop App は、すばやくアクセスできるようにアセットをキャッシュするので、ロック済みのステータスが更新されるまでにしばらく時間がかかることがあります。

1. 他のユーザーが使用できるようにアセットをチェックインするには、**Asset Info** ダイアログの「Checkin」アイコンをクリックまたはタップします。

### Finder またはエクスプローラー、および Web インターフェイスを使用したアセットのチェックイン {#check-in-an-asset-using-finder-or-explorer-and-using-web-interface}

アセットの編集が終了したら、デスクトップアプリケーションでアセットを保存します。コンテキストメニューで「More Assets Info」を選択して、「Checkin」をクリックまたはタップします。

アセットが AEM サーバーにアップロードされます。必要に応じて、トレイアイコンから「アセットのステータスを表示」を選択して、アップロードのステータスを確認できます。

![AEM Desktop App のファイル転送およびアップロードのステータスウィンドウ](assets/aem_desktopapp_upload_status.png)

または、AEM Web インターフェイスからアセットをチェックインすることもできます。チェックアウトされたアセットをクリックまたはタップするか、または選択します。From the toolbar, click/tap the check in icon ![Checkin icon](assets/aemassets_icon_checkin.png).

### AEM サーバーへのアセットおよびフォルダーの一括アップロード {#bulkupload}

AEM Desktop では、アセットを含むフォルダー全体を、ローカルファイルディレクトリから AEM Assets にアップロードできます。この方法では、フォルダー内のすべてのアセットが一度にアップロードされ、ファイルを 1 つずつアップロードする必要はありません。

1. アセット UI で、ツールバーの「**作成**」をクリックまたはタップし、メニューから「**アップロードフォルダー**」を選択します。
1. アップロードするフォルダーに移動し、そのフォルダーを選択します。
1. 「OK」をクリックまたはタップします。Assets Status ダイアログにアップロードのステータスが表示されます。

   ![Assets Status ウィンドウでのアップロードのステータスの確認](assets/aem_desktopapp_bulkupload_status.png)

   Assets Status ウィンドウでのアップロードのステータスの確認

   >[!NOTE]
   >該当するアイコンをクリックまたはタップして、アップロードを手動で一時停止またはキャンセルすることができます。

1. フォルダーがアップロードされたら、ダイアログを閉じて、Assets UI に移動します。アップロードされたフォルダーが Web インターフェイスに表示されます。

Please note that it is *not recommended* to copy &amp; paste or drag &amp; drop larger number of files / nested folders from your local disk in Finder or Explorer into the network share area that is mapped by AEM desktop app. その方法では、上記のアップロードフォルダー機能を使用するよりも信頼性が低くなります。

デスクトップで作業する別の方法は、FinderまたはExplorerでAEMにアップロードするファイルやフォルダを選択し、システムクリップボードにコピーして、ネットワーク共有領域でターゲットフォルダに移動し、AEMデスクトップアプリのコンテキストメニューから「アセットを貼り付け」を選択する方法です。 これにより、AEMデスクトップアプリは、上記のアップロードフォルダーに類似した貼り付け済みアセットのアップロードを開始します。

>[!MORELIKETHIS]
>
>* [AEMデスクトップアプリの概要](https://helpx.adobe.com/experience-manager/kt/eseminars/ccoo-aem-desktop-app.html)
>* [AEMデスクトップアプリケーションでのチェックイン/チェックアウトについて理解する](https://helpx.adobe.com/experience-manager/kt/assets/using/checkin-checkout-technical-video-understand.html)
>* [AEM デスクトップアプリケーションのトラブルシューティング](troubleshoot-app-v1.md)

