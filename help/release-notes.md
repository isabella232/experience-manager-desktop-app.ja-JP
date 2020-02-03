---
title: Adobe Experience Managerデスクトップアプリケーションのリリースノート
description: Adobe Experience Managerデスクトップアプリケーションのリリースの詳細、機能強化、新機能、互換性およびダウンロードリンクです。
uuid: b783c3f8-aa1e-4c05-b687-5894909769f5
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 3052549b-fe75-44fb-a55e-5cc612868f54
index: y
internal: n
snippet: y
mini-toc-levels: 1
translation-type: tm+mt
source-git-commit: ac4be2cb69a112f393ec76d5d95987634d0c9c46

---


# Adobe Experience Managerデスクトップアプリケーションのリリースノート {#release-notes-v2}

| 製品 | Adobe Experience Manager（AEM）デスクトップアプリケーション |
|---------------|--------------------------------------------------------------------|
| アプリのバージョン（リビジョン） | 2.0（2.0.1.1） |
| サポートされている AEM バージョン | AEM 6.5、AEM 6.4、AEM 6.3（互換性パッケージを使用） |
| 種類 | マイナーリリース |
| リリース日 | 2019 年 12 月 12 日（MacおよびWin） |
| ダウンロード URL | [Mac OS 64 ビット版](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-osx-2.0.1.1.dmg)、[Windows 64 ビット版](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win64-2.0.1.1.exe)、[Windows 32 ビット版](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win32-2.0.1.1.exe) |

## システム要件および使用条件 {#system-requirements-and-prerequisites-v2}

Adobe Experience Managerデスクトップアプリケーションは、次のオペレーティングシステムと互換性があります。

* 最新のバグ修正が適用された Mac OS X 10.10 以降
* 最新のサービスパックとバグ修正が適用された Windows 7 と Windows 10

このアプリケーションは、オンプレミスまたはAdobe Managed Services(AMS)のどちらでデプロイされている場合でも、次のバージョンのExperience Managerで動作します。

* [Experience Manager 6.5.0](https://helpx.adobe.com/experience-manager/6-5/release-notes.html) 以降
* [Experience Manager 6.4.4](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) 以降
* Experience Manager 6.4.0 - 6.4.3と互換性パッケ [ージ](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)

>[!NOTE]
>
>Experience Manager 6.3のデスクトップアプリケーションのサポートは廃止されました。 アドビでは、新しいサポート対象のAdobe Experience Managerバージョンにアップグレードすることをお勧めします。
>Experience Manager 6.3.3.1 or later works with desktop app after installing the [compatibility package](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support). No such package is available for Experience Manager 6.3 as no [service packs are planned](https://helpx.adobe.com/experience-manager/maintenance-releases-roadmap.html).

ローカルマシンにインストールする AEM デスクトップアプリケーションのバージョンに応じて、Adobe Experience Manager サーバーの特定のバージョンや、サーバー側の追加コンポーネント（サービスパック、ホットフィックスまたは機能パック）が必要になります。Adobe Experience Manager管理者に問い合わせてください。

### 様々なアセットおよびファイルタイプのサポート {#support-for-file-types}

アプリケーションは、基本操作のバイナリファイルを表すAdobe Experience Managerに保存されたアセットをサポートします。 ネイティブデスクトップアプリケーションでファイルを開くには、PNG や JPG などの特定のファイルタイプと Mac Preview や Adobe Photoshop などの特定のアプリケーションとの関連付けがオペレーティングシステムで設定されている必要があります。

一部のファイルタイプでは、リンクされたアセットをバイナリ内に配置することができます。デスクトップアプリケーションを使用してこのようなバイナリファイルを開いた場合、Experience Managerリポジトリにアセットが存在すると、アプリケーションはリンクされたアセットを事前にダウンロードします。 現在サポートされているファイルタイプは次のとおりです。

* Adobe inDesign ファイル（INDD 形式）
* Adobe Illustrator ファイル（AI 形式）
* Adobe Photoshop ファイル（PS 形式）

この機能は、上記アプリケーションの Adobe Creative Cloud 2018 バージョンおよび Adobe Creative Cloud 2019 バージョンでサポートされています。アプリは、発見的で最適一致アプローチを使用して、リンクされたアセットのローカルデスクトップパスをExperience Managerサーバー上のURLにマッピングします。 このアプローチは、以下を前提としています。

* ネイティブアプリケーションでは、配置されたファイルのパスにグローバルデスクトップパスが使用されます（ローカルネットワーク共有から配置され、「[!UICONTROL Reveal]」オプションで表示されます）。
* パスは、ネイティブアプリケーションによってファイルの XMP レコードに保存されます。
* Experience Managerは、アセットのメタデータレコードへのパスを使用してXMPレコードを抽出しました。
* パスはExperience Managerでアセットと一致させることができます。つまり、配置されたファイルもExperience Managerの一致するパスの下に配置されます。

## 新機能および機能強化 {#whats-new-added}

詳しくは、[v2.0 の新機能](introduction.md#whats-new-v2)を参照してください。

v 2.0.1 リリースでおこなわれたバグ修正とアップデートは次のとおりです。

* `%APPDATA%` パスに一致する `%Temp%` ディレクトリを構成するオプションが許可されます。 <!-- CQ-4282665 -->
* ユーザーが Okta SAML 認証を使用して AEM author にログインできるようになります。 <!-- CQ-4278134 -->

## インストール手順 {#installation-instructions-v2}

To know how to install and configure the app, see [Install Experience Manager desktop app](install-upgrade.md).

If you are upgrading from a previous Experience Manager desktop app, you must follow these best practices for transitioning that are listed at [upgrade from previous version](install-upgrade.md#upgrade-from-previous-version).

## デスクトップアプリケーションの動作の仕組みに関する重要なメモ {#how-app-works}

デスクトップアプリケーションとその動作の仕組みについて、以下の点を理解しておくことが重要です。

* デスクトップアプリケーションは、AEM との間でアセットバイナリを完全に転送する必要がある操作（開く、編集、変更のアップロード、アセットのアップロード）を完全にコントロールできます。
   * デスクトップ上でアセットを操作する場合は、個別、フォルダー単位、複数選択のいずれの場合でも、「開く」、「編集」、デスクトップへの「ダウンロード」のいずれかを明示的に実行する必要があります。
   * アセットに対するローカルな変更を AEM にアップロードする場合は、個別のアセットまたは同時に選択した複数のアセットに対して「[!UICONTROL Upload Changes]」を選択する必要があります。
   * デスクトップアプリケーションは、デスクトップと AEM をまたいでアセットを同期させる「同期クライアント」ではありません。
   * デスクトップアプリケーションは、AEM リポジトリを仮想フォルダー構造としてマッピングするネットワーク共有を提供しません。
* デスクトップアプリケーションに表示されるアセットのリストは、AEM Assets リポジトリのステータスに基づいています。ローカルにダウンロードされた後でローカルファイルまたはキャッシュフォルダー内で名前が変更されたファイルは、デスクトップアプリケーションでは表示または管理されません。
* 期待した結果がデスクトップアプリケーションに表示されない場合は、上部のバーにある更新アイコンをクリックしてください。
* 「[!UICONTROL Reveal File]」アクションを使用したときに表示されるローカルネットワーク共有には、ローカルに使用可能なファイル（およびフォルダー）のみ表示されます。「[!UICONTROL Reveal File]」および「[!UICONTROL Reveal Folder]」アクションでは、アセットを事前にダウンロードして、適切なアセットがローカルネットワーク共有に表示されるようにします。
* Adobe Creative Cloud アプリのネイティブファイルにリンクまたは配置されたアセットファイルを Creative Cloud アプリが読み取るときに、SMB（Mac）／WebDAV（Win）ローカルネットワーク共有が使用されます。

ユーザーのアクションによってクラウドとローカルファイルシステムの間で開始されるアセットおよびファイルのフローを次の図に示します。

![デスクトップアプリケーションを介した AEM サーバーからネイティブデスクトップアプリへのアセットのフロー](assets/da20_flow_diagram.png)

## 既知の問題 {#known-issues-v2}

**ユーザーインターフェイスに関する問題：**

* デスクトップアプリケーションのインターフェイスが空白になることがあります。右クリックし「[!UICONTROL Refresh]」をクリックして、アプリケーションを再度読み込みます。更新後、DAM リポジトリのルートから開始します。アセットのアップデートまたはステータスは保持されます。 <!-- CQ-4270267 -->
* トラックパッドやマウスホイールを使用せずにフォルダーや検索結果間を移動するのが困難。マウスホイールのないマウスデバイスでは、スクロールバーが表示されないことがあります。<!-- CQ-4269947 -->
* まれに、アセットの変更をアップロードするときに進行状況バーが正しく表示されないことがあります。
* フィルターを適用後に解除してローカルに編集されたすべてのアセットを検索すると、開始時点の検索結果やフォルダー表示に戻りません。DAM リポジトリのルートフォルダーが表示されます。
* AEM サーバーが動作していない URL に接続すると、接続画面が応答しなくなることがあります。アプリケーションを終了して、再度起動してください。

**CRUD（作成、読み取り、更新、削除）操作に関する問題：**

* 無効な文字が含まれていても、アプリケーションがファイルのアップロードを試みるので、サーバー側のアップロードが失敗する可能性があります。<!-- CQ-4273652 -->
* アセットに対する変更をコメント付きでアップロードすると、コメントはアセットと共に AEM に保存されますが、バージョン管理コメントとして表示されません。この問題は AEM 6.4.5 および AEM 6.5.1 で解決済みです。Adobe では、最新のサービスパックをインストールすることを強くお勧めします。 <!-- CQ-4268990 -->
* アセット転送をユーザーがキャンセルできません。意図しない大量の転送をトリガーした場合は、アプリケーションを終了して、再度起動してください。<!-- CQ-4278940 -->

**プラットフォームに関する問題：**

* Windows では、アセットを開くと、編集していなくても、アセットのステータスがすぐに「[!UICONTROL Edited Locally]」に変わる場合があります。「[!UICONTROL Refresh]」をクリックして更新してください。

>[!MORELIKETHIS]
>
>* [AEM 6.5 ドキュメント](https://helpx.adobe.com/support/experience-manager/6-5.html)
>* [AEM Assets 6.5 ドキュメント](https://docs.adobe.com/content/help/en/experience-manager-65/assets/home.html)
>* [Experience Managerデスクトップアプリケーションの使用方法](using.md)
>* [デスクトップアプリケーションのインストールとアップグレード](install-upgrade.md)
>* [ベストプラクティスとトラブルシューティングのヒント](troubleshoot.md)

