---
title: AEMデスクトップアプリのリリースノート
description: AEMデスクトップアプリのリリースの詳細、機能強化、新機能、互換性、ダウンロードリンク。
uuid: b783c3f8-aa1e-4c05-b687-5894909769f5
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 3052549b-fe75-44fb-a55e-5cc612868f54
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 850d2c21a796599ed40164e7d6f892967563c16b

---


# AEM desktop app Release Notes {#release-notes-v2}

| 商品 | Adobe Experience Manager(AEM)デスクトップアプリケーション |
|---------------|--------------------------------------------------------------------|
| アプリのバージョン（リビジョン） | 2.0 (2.0.0.4) |
| サポートされている AEM バージョン | AEM 6.5、AEM 6.4、AEM 6.3（互換パッケージ付き） |
| 種類 | メジャーリリース |
| リリース日 | 2019年8月30日(Mac)、2019年9月9日(Win) |
| ダウンロード URL | [MacOS 64-bit](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-osx-2.0.0.4.dmg); [Windows 64-bit](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win64-2.0.0.4.exe); [Windows 32ビット版](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win32-2.0.0.4.exe) |

## システム要件および使用条件 {#system-requirements-and-prerequisites-v2}

AEMデスクトップアプリケーションは、次のオペレーティングシステムと互換性があります。

* 最新のバグフィックスが適用された Mac OS X 10.10 以降
* 最新のサービスパックとバグフィックスが適用された Windows7 と Windows 10

このアプリケーションは、オンプレミスまたはAdobe Managed Services(AMS)のどちらでデプロイされている場合でも、次のAEMバージョンで動作します。

* [AEM 6.5.0](https://helpx.adobe.com/experience-manager/6-5/release-notes.html) 以降
* [AEM 6.4.4](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) 以降
* AEM 6.4.0 - 6.4.3(互換パッケ [ージ付き)](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)
* AEM 6.3.3.1以降と互換性パッケー [ジ](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)
* AEM 6.3では、サービスパックは計 [画されていません](https://helpx.adobe.com/experience-manager/maintenance-releases-roadmap.html)。 アドビでは、新しいバージョンのAEMにアップグレードすることをお勧めします。

ローカルコンピューターにインストールする予定のアプリケーションのバージョンには、特定のAdobe Experience Managerサーバーのバージョンと、追加のサーバー側コンポーネント（サービスパック、ホットフィックス、または機能パック）が必要です。 AEM管理者に問い合わせてください。

### 様々なアセットとファイルタイプのサポート {#support-for-file-types}

アプリケーションは、基本操作のバイナリファイルを表すAEMに保存されたアセットをサポートします。 ネイティブデスクトップアプリケーションでファイルを開く場合は、PNGやJPGなどの特定のファイルタイプとMac PreviewやAdobe Photoshopなどの特定のアプリケーションとのオペレーティングシステムの関連付けが必要です。

いくつかのファイルタイプでは、リンクされたアセットのバイナリへの配置がサポートされています。 デスクトップアプリケーションを使用してこのようなバイナリファイルを開いた場合、AEMリポジトリにアセットが存在すると、アプリケーションはリンクされたアセットを事前にダウンロードします。 現在サポートされているファイルの種類は次のとおりです。

* Adobe inDesignファイル（INDD形式）
* Adobe Illustratorファイル（AI形式）
* Adobe Photoshopファイル（PS形式）

この機能は、上記のアプリケーションのAdobe Creative Cloud 2018およびCreative Cloud 2019バージョンでサポートされています。 アプリは、発見的で最適一致アプローチを使用して、リンクされたアセットのローカルデスクトップパスをAEMサーバー上のURLにマッピングします。 これは、次のいくつかの前提に依存しています。

* ネイティブアプリケーションに配置されたファイルへのパスは、グローバルデスクトップパスを使用します（ローカルネットワーク共有から配置され、「表示」オプションが表示されます）
* パスは、ネイティブアプリケーションによってファイルのXMPレコードに保存されます
* AEMは、アセットのメタデータレコードへのパスを使用してXMPレコードを抽出しました
* パスはAEM内のアセットと一致させることができます（つまり、配置されたファイルもAEM内の一致するパスの下に配置されます）。

## New features and enhancements {#whats-new-added}

詳しくは、「アプリの新 [機能」を参照してください](introduction.md#whats-new-v2)。

## インストール手順 {#installation-instructions-v2}

アプリケーションのインストールと設定の方法について詳しくは、「AEMデスクトップアプリケーションのイ [ンストール」を参照してくださ](install-upgrade.md)い。

以前のAEMデスクトップアプリケーションからアップグレードする場合は、以前のバージョンからのアップグレード時に表示される移行のベストプラクティスに従 [う必要がありま](install-upgrade.md#upgrade-from-previous-version)す。

## アプリの動作に関する重要なメモ {#how-app-works}

アプリケーションとその仕組みについて、以下の点を理解することが重要です。

* アプリケーションは、AEM（開く、編集、変更のアップロード、アセットのアップロード）との間でアセットバイナリの完全な転送を必要とする操作を完全に制御します。
   * デスクトップでアセットを操作する場合は、デスクトップに対して、個別に、フォルダー内で、または複数選択を使用して、「開く」、「編集」または「ダウンロード」を明示的に指定する必要があります。
   * AEMにアップロードされたアセットに対するローカルな変更を取得する場合は、個別に選択するか、複 [!UICONTROL Upload Changes]数選択を使用して選択する必要があります。
   * アプリケーションは、デスクトップとAEM間でアセットを同期する「同期クライアント」ではありません。
   * アプリケーションは、AEMリポジトリを仮想フォルダー構造としてマップするネットワーク共有を提供しません。
* アプリケーションによって表示されるアセットのリストは、AEM Assetsリポジトリのステータスに基づいています。 ローカルにダウンロードされ、ローカルファイルまたはキャッシュフォルダー内で名前が変更されたファイルは、アプリケーションによって表示または管理されません。
* アプリで期待した結果が表示されない場合は、上部のバーにある「更新」アイコンをクリックします。
* アクションを使用すると表示されるローカルネットワーク共有は、 [!UICONTROL Reveal File] ローカルで使用可能なファイル（およびフォルダ）のみを表示します。 [!UICONTROL Reveal File] およびは、 [!UICONTROL Reveal Folder] アセットを事前にダウンロードし、ローカルネットワーク共有に正しいアセットを表示するのに役立ちます。
* SMB(Mac OS)/WebDAV(Win)ローカルネットワーク共有は、Adobe Creative cloudアプリケーションが、Creative cloudアプリケーションのネイティブファイルにリンクまたは配置されたアセットファイルを読み取るときに使用されます。

次の図は、ユーザーの操作によって開始される、クラウドからローカルファイルシステムへのアセットとファイルのフローを示しています。

![デスクトップアプリケーションを使用したAEMサーバーからネイティブデスクトップアプリケーションへのアセットのフロー](assets/do-not-localize/da20_flow_diagram.png)

## 既知の問題 {#known-issues-v2}

**ユーザーインターフェイスに関する問題：**
* デスクトップアプリケーションのインターフェイスが空白になる場合があります。 右クリックし、をクリックして、アプ [!UICONTROL Refresh] リケーションを再び読み込みます。 このような更新を行うと、アプリの状態がリセットされ、DAMリポジトリのルートにあるスタートアップスクリーンで開始します。 <!-- CQ-4270267 -->
* トラックパッドやマウスホイールを使用せずにフォルダや検索結果を操作するのが難しい。 マウスホイールを使用しないと、マウスデバイスではスクロールバーが表示されない場合があります。 <!-- CQ-4269947 -->
* まれに、アップロードするアセットが変更された場合に、プログレスバーが正しく表示されないことがあります。
* フィルターを適用して削除した後で、ローカルで編集されたすべてのアセットが検索されると、アプリはユーザーをそのユーザーが開始した検索結果やフォルダービューに移動させません。 アプリは、DAMリポジトリのルートフォルダーを表示します。
* AEMサーバーが実行されていないURLに接続すると、接続画面が応答しなくなることがあります。 アプリケーションを終了し、再び起動します。

**CRUD（作成、読み取り、更新、削除）の問題：**
* 無効な文字が含まれていても、アプリケーションがファイルのアップロードを試みると、サーバー側のアップロードエラーが発生する可能性があります。 <!-- CQ-4273652 -->
* コメントを含むアセットに対する変更をアップロードする場合、コメントはAEMにアセットと共に保存されますが、バージョンコメントとしては表示されません（AEM 6.4.5、6.5.1で解決済み）。 <!-- CQ-4268990 -->
* 資産転送をユーザーがキャンセルできません。 意図しない大きな転送をトリガーした場合は、アプリケーションを終了し、再び起動します。 <!-- CQ-4278940 -->

**プラットフォームの問題：**
* Windowsでは、編集していない場合でも、アセットのステータスが開いた直後 [!UICONTROL Edited Locally] に変わる場合があります。 をクリック [!UICONTROL Refresh] して更新します。

>[!MORELIKETHIS]
>
>* [AEM 6.5 ドキュメント](https://helpx.adobe.com/support/experience-manager/6-5.html)
>* [AEM Assets 6.5ドキュメント](https://docs.adobe.com/content/help/en/experience-manager-64/assets/home.html)
>* [AEMデスクトップアプリを使用する](using.md)
>* [デスクトップアプリケーションのインストールとアップグレード](install-upgrade.md)
>* [ベストプラクティスとトラブルシューティングのヒント](troubleshoot.md)

