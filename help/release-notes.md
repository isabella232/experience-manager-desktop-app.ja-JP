---
title: '[!DNL Adobe Experience Manager] デスクトップアプリケーションリリースノート'
description: ' [!DNL Adobe Experience Manager]  デスクトップアプリケーションのリリース詳細、機能強化、新機能、互換性、ダウンロードリンク。'
mini-toc-levels: 1
feature: デスクトップアプリ、リリース情報
exl-id: e058e7a2-fcc8-4ad1-899e-20695db6bc72
source-git-commit: ac533db59b2a5c64243b762f4b77b3148c4f1867
workflow-type: tm+mt
source-wordcount: '1523'
ht-degree: 100%

---

# [!DNL Adobe Experience Manager] デスクトップアプリケーションリリースノート {#release-notes-v2}

最新のデスクトップアプリケーションバージョン 2.1（2.1.2.0）のリリース情報は以下のとおりです。リリース日は 2021 年 3 月 26 日です。これは、機能が強化されたマイナーリリースです。

**サポートされている [!DNL Experience Manager] バージョン**&#x200B;は次のとおりです。

* [!DNL Experience Manager] as a [!DNL Cloud Service]。[リリースノート](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/home.html?lang=ja)を参照してください。
* [!DNL Experience Manager] 6.5.0 以降（Adobe Managed Services（AMS）版またはオンプレミス版）。[サービスパックのリリースノート](https://experienceleague.adobe.com/docs/experience-manager-65/release-notes/service-pack/sp-release-notes.html?lang=ja)を参照してください。
* [!DNL Experience Manager] 6.4.4 以降（Adobe Managed Services（AMS）版またはオンプレミス版）。[サービスパックのリリースノート](https://experienceleague.adobe.com/docs/experience-manager-64/release-notes/sp-release-notes.html?lang=ja)を参照してください。
* [!DNL Experience Manager] 6.4.0 ～ 6.4.3（[互換性パッケージ](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)をインストール。Adobe Managed Services（AMS）版またはオンプレミス版）。
* [!DNL Experience Manager] 6.3（互換性パッケージを使用）
* [!DNL Experience Manager] 6.3.3.1 以降（[互換性パッケージ](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)をインストール）。[!DNL Experience Manager] 6.3.3.0 以前のバージョンではデスクトップアプリケーションはサポートされていません。

[!DNL Adobe Experience Manager] デスクトップアプリケーションは次の&#x200B;**オペレーティングシステム**&#x200B;で使用できます。

* 最新のバグ修正が適用された macOS X 10.14 以降。[Apple シリコンを搭載した Mac コンピューター](https://support.apple.com/ja-jp/HT211814)はまだサポートされていません。
* 最新のサービスパックとバグ修正が適用された Windows 10。

サポートされている OS の&#x200B;**ダウンロード URL** は次のとおりです。

| オペレーティングシステム | [!DNL Experience Manager] as a [!DNL Cloud Service] | [!DNL Experience Manager] 6.x |
|---|---|---|
| macOS 64 ビット | [ダウンロードリンク](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-2.1.2.0.dmg) | [ダウンロードリンク](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-2.1.2.0.dmg) |
| Windows 64 ビット | [ダウンロードリンク](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win64-2.1.2.0.exe) | [ダウンロードリンク](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win64-2.1.2.0.exe) |
| Windows 32 ビット | [ダウンロードリンク](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win32-2.1.2.0.exe) | [ダウンロードリンク](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win32-2.1.2.0.exe) |

>[!NOTE]
>
>Windows 7 はサポートされなくなりました。[Windows 7 のサポート終了（EOL）に関する記事](https://support.microsoft.com/ja-jp/help/4057281/windows-7-support-ended-on-january-14-2020)を参照してください。

<!-- The version of the app you plan to install on your local machine requires a specific [!DNL Adobe Experience Manager] server version/additional server-side components (service packs, hot fixes, or feature packs). Contact your [!DNL Experience Manager] administrator for help.
-->

## 様々なアセットおよびファイルタイプのサポート {#support-for-file-types}

アプリケーションでは、[!DNL Experience Manager] に保存されているアセットのうち、アプリケーションの基本操作に対応するバイナリファイルを表すものをサポートします。ネイティブデスクトップアプリケーションでファイルを開くには、PNG や JPG などの特定のファイルタイプと Mac Preview や Adobe Photoshop などの特定のアプリケーションとの関連付けがオペレーティングシステムで設定されている必要があります。

一部のファイルタイプでは、リンクされたアセットをバイナリ内に配置することができます。デスクトップアプリケーションでこのようなバイナリファイルを開く際、[!DNL Experience Manager] リポジトリーにアセットがあると、リンクされたアセットが事前にダウンロードされます。現在サポートされているファイルタイプは次のとおりです。

* [!DNL Adobe InDesign] ファイル（INDD 形式）
* [!DNL Adobe Illustrator] ファイル（AI 形式）
* [!DNL Adobe Photoshop] ファイル（PS 形式）

この機能は、上記アプリケーションの [!DNL Adobe Creative Cloud] 2018 バージョンおよび [!DNL Adobe Creative Cloud] 2019 バージョンでサポートされています。デスクトップアプリケーションは、発見的最良一致アプローチを使用して、リンクされたアセットのローカルデスクトップパスを [!DNL Experience Manager] サーバー上の URL にマッピングします。このアプローチは、以下を前提としています。

* ネイティブアプリケーションでは、配置されたファイルのパスにグローバルデスクトップパスが使用されます（ローカルネットワーク共有から配置され、「[!UICONTROL Reveal]」オプションで表示されます）。

* パスは、ネイティブアプリケーションによってファイルの XMP レコードに保存されます。

* [!DNL Experience Manager] では、アセットのメタデータレコードへのパスを使用して XMP レコードの抽出が完了しています。

* パスは [!DNL Experience Manager] 内のアセットと一致させることができます。つまり、配置されたファイルは [!DNL Experience Manager] 内でも一致したパスの下に存在しています。

## 新機能、機能強化、バグ修正 {#what-is-new}

詳しくは、[v2.0 の新機能](introduction.md#whats-new-v2)を参照してください。

**AEM デスクトップアプリケーション v2.1.2.0 の更新点**

* 新しいオプション「[!UICONTROL Clear Cookies]」がアプリケーションのメインメニューに追加されました。これは、接続先のサーバーを変更した場合などに発生する可能性のある、ログインの問題を解決するのに役立ちます。[接続前に cookie をクリアする](/help/troubleshoot.md#cannot-login-cookies-issue)を参照してください。

**AEM デスクトップアプリケーション v2.1.1.0 の更新点**

* 詳細設定により、フォルダーのアップロード時に v1.10 アプリケーションの動作をエミュレートできます。v1.10 では、ユーザーが指定したフォルダー名のスペースと大文字／小文字の区別をそのまま使用した名前のノードがリポジトリー内に作成されます。v2.1 アプリケーションのデフォルトの動作はそのまま変わりません。つまり、フォルダー名の複数のスペースはリポジトリーノード名ではハイフンに置き換わり、小文字のノード名に変換されます。[デスクトップアプリケーションの環境設定](/help/install-upgrade.md#set-preferences)を参照してください。

**AEM デスクトップアプリケーション v2.1.0.0 の更新点**

* アセットをアップロードする際に、アプリケーションのインターフェイス上でファイルやフォルダーを Windows エクスプローラーまたは Mac Finder から直接ドラッグできるようになりました。これは、以前アプリケーションで使用可能だったアップロードオプションに加えて機能します。  <!-- CQ-4309527 -->

**AEM デスクトップアプリケーション v2.0.3 の更新点**

現在のバージョンで修正されたバグは次のとおりです。

* Windows 版アプリケーションのユーザーが [!DNL Adobe Experience Manager] 6.5.5.0 の DAM リポジトリーにアクセスしようとするときのログインの問題を修正しました。

**AEM デスクトップアプリケーション v2.0.2 の更新点**

バグ修正と更新点は次のとおりです。

* アップロードの高速化設定が使用可能になり、アップロードのパフォーマンスが向上しました。この設定を有効にすると、アップロードの高速化のために、AEM デスクトップアプリケーションで使用されるローカル CPU スレッドが増え、リソースがさらに大量に消費されるようになります。

* ファイル名またはパスに特定の GB18030 文字が含まれている場合に発生するアセットアップロードの問題を修正しました。<!-- CQ-4283494 -->

* 検索結果で別の並べ替えタイプに切り替えた後で、「関連性順に並べ替え」オプションを使用できます。<!-- CQ-4286874 -->

* デスクトップアプリケーションで、明示的に更新しなくてもサブフォルダーが一覧表示されるようになりました。<!-- CQ-4285711 -->

* （Windows の場合）一部の Windows コンピューターでデスクトップアプリケーションインターフェイスがまれに使用できない問題を修正しました。インターフェイス要素のクリック領域が横に「シフト」し、アプリケーションインターフェイスがゆがんで表示されるので、クリックできませんでした。<!-- CQ-4280785 -->

**AEM デスクトップアプリケーション v2.0.1 の更新点**

バグ修正と更新点は次のとおりです。

* `%APPDATA%` パスに一致する `%Temp%` ディレクトリを構成するオプションが許可されます。<!-- CQ-4282665 -->

* ユーザーが Okta SAML 認証を使用して [!DNL Experience Manager] オーサーにログインできるようになります。<!-- CQ-4278134 -->

## インストール手順 {#installation-instructions-v2}

アプリケーションのインストールと設定の方法については、[ [!DNL Experience Manager]  デスクトップアプリケーションのインストール](install-upgrade.md)を参照してください。

以前の [!DNL Experience Manager] デスクトップアプリケーションからアップグレードする場合は、[以前のバージョンからのアップグレード](install-upgrade.md#upgrade-from-previous-version)にリストされている移行のベストプラクティスに従う必要があります。

## デスクトップアプリケーションの動作の仕組みに関する重要なメモ {#how-app-works}

デスクトップアプリケーションとその動作の仕組みについて、以下の点を理解しておくことが重要です。

* アプリケーションは、[!DNL Experience Manager] との間でアセットバイナリを完全に転送する必要がある操作（開く、編集、変更のアップロード、アセットのアップロード）を完全にコントロールできます。

   * デスクトップ上でアセットを操作する場合は、個別、フォルダー単位、複数選択のいずれの場合でも、「開く」、「編集」、デスクトップへの「ダウンロード」のいずれかを明示的に実行する必要があります。

   * アセットに対するローカルな変更を [!DNL Experience Manager] にアップロードする場合は、個別のアセットまたは同時に選択した複数のアセットに対して「[!UICONTROL Upload Changes]」を選択する必要があります。

   * アプリケーションは、デスクトップと [!DNL Experience Manager] をまたいでアセットを同期させる「同期クライアント」ではありません。

   * アプリケーションは、[!DNL Experience Manager]リポジトリーを仮想フォルダー構造としてマッピングするネットワーク共有を提供しません。

* デスクトップアプリケーションに表示されるアセットのリストは、Assets リポジトリーのステータスに基づいています。ローカルにダウンロードされた後でローカルファイルまたはキャッシュフォルダー内で名前が変更されたファイルは、デスクトップアプリケーションでは表示または管理されません。

* 期待した結果がデスクトップアプリケーションに表示されない場合は、上部のバーにある更新アイコンをクリックしてください。

* 「[!UICONTROL Reveal File]」アクションを使用したときに表示されるローカルネットワーク共有には、ローカルに使用可能なファイル（およびフォルダー）のみ表示されます。「[!UICONTROL Reveal File]」および「[!UICONTROL Reveal Folder]」アクションでは、アセットを事前にダウンロードして、適切なアセットがローカルネットワーク共有に表示されるようにします。

* Adobe Creative Cloud アプリのネイティブファイルにリンクまたは配置されたアセットファイルを Creative Cloud アプリが読み取るときに、SMB（Mac）／WebDAV（Win）ローカルネットワーク共有が使用されます。

ユーザーのアクションによってクラウドとローカルファイルシステムの間で開始されるアセットおよびファイルのフローを次の図に示します。

![デスクトップアプリケーションを介した [!DNL Experience Manager] サーバーからネイティブデスクトップアプリへのアセットのフロー](assets/da20_flow_diagram.png)

## 既知の問題 {#known-issues-v2}

**ユーザーインターフェイスに関する問題：**

* デスクトップアプリケーションのインターフェイスが空白になることがあります。右クリックし「[!UICONTROL Refresh]」をクリックして、アプリケーションを再度読み込みます。更新後、DAM リポジトリーのルートから開始します。アセットのアップデートまたはステータスは保持されます。<!-- CQ-4270267 -->

* トラックパッドやマウスホイールを使用せずにフォルダーや検索結果間を移動するのが困難。マウスホイールのないマウスデバイスでは、スクロールバーが表示されないことがあります。<!-- CQ-4269947 -->

* まれに、アセットの変更をアップロードするときに進行状況バーが正しく表示されないことがあります。

* フィルターを適用後に解除してローカルに編集されたすべてのアセットを検索すると、開始時点の検索結果やフォルダー表示に戻りません。DAM リポジトリーのルートフォルダーが表示されます。

* [!DNL Experience Manager] サーバーが動作していない URL に接続すると、接続画面が応答しなくなることがあります。アプリケーションを終了して、再度起動してください。

**CRUD（作成、読み取り、更新、削除）操作に関する問題：**

* 無効な文字が含まれていても、アプリケーションがファイルのアップロードを試みるので、サーバー側のアップロードが失敗する可能性があります。<!-- CQ-4273652 -->

* アセットに対する変更をコメント付きでアップロードすると、コメントはアセットと共に [!DNL Experience Manager] に保存されますが、バージョン管理コメントとして表示されません。この問題は [!DNL Experience Manager] 6.4.5 および [!DNL Experience Manager] 6.5.1 で解決済みです。最新のサービスパックをインストールすることを強くお勧めします。 <!-- CQ-4268990 -->

* アセット転送をユーザーがキャンセルできません。意図しない大量の転送をトリガーした場合は、アプリケーションを終了して、再度起動してください。<!-- CQ-4278940 -->

**プラットフォームに関する問題：**

* Windows では、アセットを開くと、編集していなくても、アセットのステータスがすぐに「[!UICONTROL Edited Locally]」に変わる場合があります。「[!UICONTROL Refresh]」をクリックして更新してください。

>[!MORELIKETHIS]
>
>* [[!DNL Experience Manager] as a [!DNL Cloud Service] 詳細を見る](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=ja)
>* [[!DNL Experience Manager] as a [!DNL Cloud Service] [!DNL Assets] 詳細を見る](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html?lang=ja)
>* [ [!DNL Experience Manager]  デスクトップアプリケーションを使用するには、以下をおこないます。](using.md)
* [デスクトップアプリケーションのインストールとアップグレード](install-upgrade.md)
* [ベストプラクティスとトラブルシューティングのヒント](troubleshoot.md)

