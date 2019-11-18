---
title: AEMデスクトップアプリケーションのベストプラクティスとトラブルシューティング
description: インストール、アップグレード、設定などに関連する時折発生する問題を解決するには、ベストプラクティスに従い、トラブルシューティングを行います。
uuid: ce98a3e7-5454-41be-aaaa-4252b3e0f8dd
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f5eb222a-6cdf-4ae3-9cf2-755c873f397c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 850d2c21a796599ed40164e7d6f892967563c16b

---


# Troubleshoot AEM desktop app {#troubleshoot-v2}

Adobe Experience Manager(AEM)デスクトップアプリは、リモートのAEM展開のDigital Asset Management(DAM)リポジトリに接続します。 アプリは、コンピューター上のリポジトリ情報と検索結果を取得し、ファイルとフォルダーをダウンロードおよびアップロードします。また、AEM Assetsユーザーインターフェイスとの競合を管理する機能が含まれます。

アプリのトラブルシューティング、ベストプラクティス、制限事項の確認について説明します。

## ベストプラクティス {#best-practices-to-prevent-troubles}

次のベストプラクティスに従って、一般的な問題やトラブルシューティングを回避します。

* **デスクトップアプリの仕組みを理解する**。アプリの使用を開始する前に、アプリの動作を数分間お待ちください。 Web UIとデスクトップ間のリンク、リポジトリマッピング、アセットキャッシュ、ローカルでの保存、バックグラウンドでのアップロードについて詳しく説明します。 See [how it works](release-notes.md#how-app-works).

* **フォルダ名にサポートされていない文字を使用しない**:フォルダの作成やアップロード時には、空白や無効な文字を使用しないでください。 文字のリストについては、「AEM Assetsでのフォ [ルダーの作成」を参照してくださ](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html#Creatingfolders)い。 一部のAEMの使用例は、フォルダー名にサポートされていない文字が原因で影響を受ける場合があります。

* **競合を回避するためのベストプラクティス**:複数のアセットでの共同作業で競合が発生する可能性を回避するには、「競合の [回避」を参照してくださ](using.md#adv-workflow-collaborate-avoid-conflicts)い。

* **大きな階層フォルダーにフォルダーのアップロードを使用**:アセットWebインターフェイスや他の方法を使用する代わりに、AEMデスクトップアプリを使用して大きなフォルダーをアップロードします。 アプリは、ログおよび監視を使用して、アセットをバックグラウンドでアップロードします。 アセットの一括 [アップロードを参照してくださ](using.md#bulk-upload-assets)い。

* **最新バージョンを使用**:新しいバージョンのアプリをインストールする前、または新しいバージョンのAEMにアップグレードする前に、最新のバージョンのアプリを使用し、必ず互換性を確認してください。 See [release notes](release-notes.md).

* **同じドライブ文字を使用**:組織全体で同じドライブ文字を使用して、AEM DAMにマッピングします。 他のユーザーが配置したアセットを表示するには、同じパスを使用する必要があります。 同じドライブ文字を使用すると、DAMアセットへの絶え間ないパスが確実に作成されます。 アセットは配置されたままで、異なるドライブ文字が別のユーザーによって使用されていても削除されません。

* **ネットワークに注意**:AEMデスクトップアプリのパフォーマンスには、ネットワークのパフォーマンスが重要です。 ファイル転送や一括操作に対する応答が遅くなる場合は、多くのネットワークトラフィックを引き起こす可能性のある機能やアプリを無効にします。

* **デスクトップアプリケーションでサポートされていない使用例**:アプリをアセットの移行に使用しない（計画や他のツールが必要）。負荷の高いDAM操作（大きなフォルダーの移動、大きなアップロード、高度なメタデータ検索を使用したファイルの検索など）同期クライアントとして（デザインの原則と使用パターンは、Microsoft oneDriveやAdobe Creative cloudデスクトップ同期などの同期クライアントとは異なります）。

## トラブルシューティング方法 {#troubleshooting-prep}

デスクトップアプリの問題のトラブルシューティングを行うには、次の情報に注意してください。 また、サポートを求める場合に、問題をアドビカスタマーケアにより適切に伝える準備を行います。

### デバッグモードの有効化 {#enable-debug-mode}

トラブルシューティングを行うには、デバッグモードを有効にして、ログに詳細情報を取得します。 アプリをデバッグモードで実行するには、ターミナルまたはコマンドプロンプトで次のコマンドラインオプションを使用します。

* Windows の場合：`SET AEM_DESKTOP_LOG_LEVEL=DEBUG & "C:\Program Files\Adobe\Adobe Experience Manager Desktop\Adobe Experience Manager Desktop.exe"`

* Macの場合： `AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app`

### ログファイルの場所 {#check-log-files-v2}

AEMデスクトップアプリケーションのログファイルは、次の場所にあります。 多数のアセットをアップロードする場合、一部のファイルのアップロードに失敗した場合は、上記の場所 `backend.log` にあるファイルを参照して、アップロードに失敗したファイルを特定します。

* Windows の場合：`%LocalAppData%\Adobe\AssetsCompanion\Logs`

* Macの場合： `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`

>[!NOTE]
>
>サポートの要請/チケットに関してアドビカスタマーケアと連絡を取る際に、ログファイルを共有して、サポートチームがこの問題を理解しやすくするよう求められる場合があります。 フォルダー全体をア `Logs` ーカイブし、カスタマーケアと共有します。

### キャッシュをクリア {#clear-cache-v2}

AEMデスクトップアプリのキャッシュをクリアするのは、いくつかの問題を解決できる暫定的なトラブルシューティングタスクです。 アプリの環境設定からキャッシュをクリアします。 詳しくは、環 [境設定を参照してくださ](install-upgrade.md#set-preferences)い。 キャッシュフォルダーのデフォルトの場所は次のとおりです。

* Windows の場合：`%LocalAppData%\Adobe\AssetsCompanion\Cache\`

* Macの場合： `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/`

ただし、AEMデスクトップで設定されているAEMエンドポイントに応じて場所が変わる場合があります。 値は、ターゲット URL のエンコードされたバージョンです。For example, if the application is targeting `http://localhost:4502`, the directory name is `http%3A%2F%2Flocalhost%3A4502%2F`. キャッシュをクリアするには、適切なフォルダーを削除します。 キャッシュをクリアするもう1つの理由は、ディスク領域が不足しているときにディスク領域を解放することです。

>[!CAUTION]
>
>AEMデスクトップのキャッシュをクリアすると、AEMサーバーと同期されないローカルアセットの変更は取り消しできなくなります。

### AEMデスクトップアプリケーションのバージョンを把握する {#know-app-version-v2}

アプリ ![メニューをクリックし](assets/do-not-localize/more_options_da2.png) 、アプリのメニューを開き、/をクリッ **[!UICONTROL Help]** クしま **[!UICONTROL About]**&#x200B;す。

## 配置されたアセットを表示できません {#placed-assets-missing}

サポートファイル（INDDファイルなど）に自分や他のクリエイティブプロフェッショナルが配置したアセットが表示されない場合は、次の項目を確認してください。

* サーバーへの接続。 フレークなネットワーク接続は、アセットのダウンロードを停止する可能性があります。
* ファイルサイズ. サイズの大きいアセットは、ダウンロードして表示するのに時間がかかります。
* ドライブ文字の一貫性。 AEM DAMを別のドライブ文字にマッピングする際に、自分または他の共同作業者がアセットを配置した場合、配置されたアセットは表示されません。
* 権限管理。配置したアセットを取得する権限を持っているかどうかを確認するには、AEM管理者に問い合わせてください。

## macOSでのアップグレード時の問題 {#issues-when-upgrading-on-macos}

macOSでAEMデスクトップアプリケーションをアップグレードする際に、場合によって問題が発生することがあります。 これは、AEMデスクトップアプリケーションのレガシーシステムフォルダーが原因で、新しいバージョンのAEMデスクトップアプリケーションが正しく読み込めないことが原因です。 この問題を修正するには、以下のフォルダーおよびファイルを手動で削除します。

次の手順を実行する前に、アプリケーションをmacOS Applications `Adobe Experience Manager Desktop` フォルダーからごみ箱にドラッグします。 次に、ターミナルを開き、次のコマンドを実行し、プロンプトが表示されたらパスワードを入力します。

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

## ファイルをアップロードできません {#upload-fails}

AEM 6.5.1以降でデスクトップアプリを使用している場合は、S3またはAzureコネクタをバージョン1.10.4以降にアップグレードします。 これにより、 [OAK-8599に関連するファイルのアップロードの失敗の問題が解決されます](https://issues.apache.org/jira/browse/OAK-8599)。 インストー [ル手順を参照してくださ](install-upgrade.md#install-v2)い。

## SSL 設定の問題 {#ssl-config-v2}

AEMデスクトップアプリケーションがHTTP通信に使用するライブラリは、厳密なSSL強制を使用します。 ブラウザーの使用に成功しても、AEMデスクトップアプリケーションの使用に失敗する場合があります。 SSL を適切に設定するには、不足している中間証明書を Apache にインストールします。[中間 CA の証明書を Apache にインストールする](https://access.redhat.com/solutions/43575)を参照してください。

## アプリが応答しない {#unresponsive}

アプリケーションが応答しなくなったり、白い画面だけが表示されたり、インターフェイスのオプションが表示されない状態でインターフェイスの下部にエラーが表示されたりすることはほとんどありません。 次の手順を順番に実行します。

1. アプリケーションインターフェイスを右クリックし、をクリックしま **[!UICONTROL Refresh]**&#x200B;す。
1. アプリケーションを終了し、再起動します。

どちらの方法でも、アプリはルートDAMフォルダーから開始します。

>[!MORELIKETHIS]
>
>* [既知の問題](release-notes.md#known-issues-v2)
>* [競合の編集を避ける](using.md#adv-workflow-collaborate-avoid-conflicts)