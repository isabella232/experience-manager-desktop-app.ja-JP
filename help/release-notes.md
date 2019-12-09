---
title: AEM Desktop App リリースノート
description: AEMデスクトップアプリのリリースの詳細、機能強化、新機能、互換性、ダウンロードリンク。
uuid: b783c3f8-aa1e-4c05-b687-5894909769f5
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 3052549b-fe75-44fb-a55e-5cc612868f54
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ad5337c8e1697d0a37d3020d25802dc1d732f320

---


# AEM Desktop App リリースノート {#release-notes-v2}

| 製品 | Adobe Experience Manager（AEM）Desktop App |
|---------------|--------------------------------------------------------------------|
| アプリのバージョン（リビジョン） | 2.0（2.0.0.4） |
| サポートされている AEM バージョン | AEM 6.5、AEM 6.4、AEM 6.3（互換性パッケージを使用） |
| 種類 | メジャーリリース |
| リリース日 | 2019 年 9 月 1 日（Mac）、2019 年 9 月 10 日（Win） |
| ダウンロード URL | [Mac OS 64 ビット版](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-osx-2.0.0.4.dmg)、[Windows 64 ビット版](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win64-2.0.0.4.exe)、[Windows 32 ビット版](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win32-2.0.0.4.exe) |

## システム要件および使用条件 {#system-requirements-and-prerequisites-v2}

AEM Desktop App は次のオペレーティングシステムと互換性があります。

* 最新のバグ修正が適用された Mac OS X 10.10 以降
* 最新のサービスパックとバグ修正が適用された Windows 7 と Windows 10

AEM Desktop App は、オンプレミスと Adobe Managed Services（AMS）上のどちらでデプロイされている場合でも、次の AEM バージョンと連携します。

* [AEM 6.5.0](https://helpx.adobe.com/experience-manager/6-5/release-notes.html) 以降
* [AEM 6.4.4](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) 以降
* AEM 6.4.0～6.4.3（[互換性パッケージ](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)を使用）
* AEM 6.3.3.1 以降（[互換性パッケージ](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)を使用）
* AEM 6.3 については、[サービスパック](https://helpx.adobe.com/experience-manager/maintenance-releases-roadmap.html)は予定されていません。より新しいバージョンの AEM にアップグレードすることをお勧めします。

ローカルマシンにインストールする AEM Desktop App のバージョンに応じて、Adobe Experience Manager サーバーの特定のバージョンや、サーバー側の追加コンポーネント（サービスパック、ホットフィックスまたは機能パック）が必要になります。不明な点がある場合は、AEM 管理者に問い合わせてください。

### 様々なアセットおよびファイルタイプのサポート {#support-for-file-types}

アプリケーションでは、AEM に保存されており基本操作のバイナリファイルを表すアセットをサポートします。ネイティブデスクトップアプリケーションでファイルを開くには、PNG や JPG などの特定のファイルタイプと Mac Preview や Adobe Photoshop などの特定のアプリケーションとの関連付けがオペレーティングシステムで設定されている必要があります。

一部のファイルタイプでは、リンクされたアセットをバイナリ内に配置することができます。このようなバイナリファイルを Desktop App で開くときにアセットが AEM リポジトリに存在する場合は、リンクされたアセットが事前にダウンロードされます。現在サポートされているファイルタイプは次のとおりです。

* Adobe inDesign ファイル（INDD 形式）
* Adobe Illustrator ファイル（AI 形式）
* Adobe Photoshop ファイル（PS 形式）

この機能は、上記アプリケーションの Adobe Creative Cloud 2018 バージョンおよび Creative Cloud 2019 バージョンでサポートされています。Desktop App は、発見的最良一致アプローチを使用して、リンクされたアセットのローカルデスクトップパスを AEM サーバー上の URL にマッピングします。このアプローチは、以下を前提としています。

* ネイティブアプリケーションでは、配置されたファイルのパスにグローバルデスクトップパスが使用されます（ローカルネットワーク共有から配置され、「表示」オプションで表示されます）。
* パスは、ネイティブアプリケーションによってファイルの XMP レコードに保存されます。
* AEM では、アセットのメタデータレコードへのパスを使用して XMP レコードの抽出が完了しています。
* パスは AEM 内のアセットと一致させることができます（つまり、配置されたファイルは AEM 内でも一致したパスの下に存在しています）。

## 新機能および機能強化 {#whats-new-added}

詳しくは、[Desktop App の新機能](introduction.md#whats-new-v2)を参照してください。

## インストール手順 {#installation-instructions-v2}

Desktop App のインストールと設定の方法については、[AEM Desktop App のインストール](install-upgrade.md)を参照してください。

以前の AEM Desktop App からアップグレードする場合は、[以前のバージョンからのアップグレード](install-upgrade.md#upgrade-from-previous-version)にリストされている移行のベストプラクティスに従う必要があります。

## Desktop App の動作の仕組みに関する重要なメモ {#how-app-works}

Desktop App とその動作の仕組みについて、以下の点を理解しておくことが重要です。

* Desktop App は、AEM との間でアセットバイナリを完全に転送する必要がある操作（開く、編集、変更のアップロード、アセットのアップロード）を完全にコントロールできます。
   * デスクトップ上でアセットを操作する場合は、個別、フォルダー単位、複数選択のいずれの場合でも、「開く」、「編集」、デスクトップへの「ダウンロード」のいずれかを明示的に実行する必要があります。
   * アセットに対するローカルな変更を AEM にアップロードする場合は、個別のアセットまたは同時に選択した複数のアセットに対して「[!UICONTROL Upload Changes]」を選択する必要があります。
   * Desktop App は、デスクトップと AEM をまたいでアセットを同期させる「同期クライアント」ではありません。
   * Desktop App は、AEM リポジトリを仮想フォルダー構造としてマッピングするネットワーク共有を提供しません。
* Desktop App に表示されるアセットのリストは、AEM Assets リポジトリのステータスに基づいています。ローカルにダウンロードされた後でローカルファイルまたはキャッシュフォルダー内で名前が変更されたファイルは、Desktop App では表示または管理されません。
* 期待した結果が Desktop App に表示されない場合は、上部のバーにある更新アイコンをクリックしてください。
* 「[!UICONTROL Reveal File]」アクションを使用したときに表示されるローカルネットワーク共有には、ローカルに使用可能なファイル（およびフォルダー）のみ表示されます。「[!UICONTROL Reveal File]」および「[!UICONTROL Reveal Folder]」アクションでは、アセットを事前にダウンロードして、適切なアセットがローカルネットワーク共有に表示されるようにします。
* Adobe Creative Cloud アプリのネイティブファイルにリンクまたは配置されたアセットファイルを Creative Cloud アプリが読み取るときに、SMB（Mac）／WebDAV（Win）ローカルネットワーク共有が使用されます。

ユーザーのアクションによってクラウドとローカルファイルシステムの間で開始されるアセットおよびファイルのフローを次の図に示します。

![Desktop App を介した AEM サーバーからネイティブデスクトップアプリへのアセットのフロー](assets/da20_flow_diagram.png)

## 既知の問題 {#known-issues-v2}

**ユーザーインターフェイスに関する問題：**
* デスクトップアプリケーションのインターフェイスが空白になる場合があります。 Right-click and click [!UICONTROL Refresh] to re-load the application. この更新後は、DAMリポジトリのルートから開始します。 アセットの更新またはステータスが保持されます。 <!-- CQ-4270267 -->
* トラックパッドやマウスポインターを使用しないと、フォルダーや検索結果を操作するのが困難。 The scroll-bar might not appear with mouse devices without mouse wheel. <!-- CQ-4269947 -->
* まれに、アセットの変更をアップロードするときに進行状況バーが正しく表示されないことがあります。
* フィルターを適用後に解除してローカルに編集されたすべてのアセットを検索すると、開始時点の検索結果やフォルダー表示に戻りません。DAM リポジトリのルートフォルダーが表示されます。
* AEM サーバーが動作していない URL に接続すると、接続画面が応答しなくなることがあります。アプリケーションを終了して、再度起動してください。

**CRUD（作成、読み取り、更新、削除）操作に関する問題：**
* 無効な文字が含まれていても、アプリケーションがファイルのアップロードを試みるので、サーバー側のアップロードが失敗する可能性があります。<!-- CQ-4273652 -->
* コメントを含むアセットに対する変更をアップロードする場合、コメントはアセットと共にAEMに保存されますが、バージョンコメントとしては表示されません。 この問題はAEM 6.4.5およびAEM 6.5.1で解決されました。アドビでは、最新のサービスパックをインストールすることを強くお勧めします。 <!-- CQ-4268990 -->
* アセット転送をユーザーがキャンセルできません。意図しない大量の転送をトリガーした場合は、アプリケーションを終了して、再度起動してください。<!-- CQ-4278940 -->

**プラットフォームに関する問題：**
* Windows では、アセットを開くと、編集していなくても、アセットのステータスがすぐに「[!UICONTROL Edited Locally]」に変わる場合があります。「[!UICONTROL Refresh]」をクリックして更新してください。

>[!MORELIKETHIS]
>
>* [AEM 6.5 ドキュメント](https://helpx.adobe.com/support/experience-manager/6-5.html)
>* [AEM Assets 6.5 ドキュメント](https://docs.adobe.com/content/help/en/experience-manager-64/assets/home.html)
>* [AEM Desktop App の使用](using.md)
>* [Desktop App のインストールとアップグレード](install-upgrade.md)
>* [ベストプラクティスとトラブルシューティングのヒント](troubleshoot.md)

