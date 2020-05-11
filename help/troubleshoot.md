---
title: Adobe Experience Manager デスクトップアプリケーションのベストプラクティスとトラブルシューティング
description: AEM デスクトップアプリケーションのインストール、アップグレード、設定などで発生することがある問題のトラブルシューティングと、デスクトップアプリケーションのベストプラクティスについて説明します。
uuid: ce98a3e7-5454-41be-aaaa-4252b3e0f8dd
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f5eb222a-6cdf-4ae3-9cf2-755c873f397c
index: y
internal: n
snippet: y
translation-type: ht
source-git-commit: a18aa9c3dad8802c3de929ba4ebb1a1583b47165

---


# Adobe Experience Manager デスクトップアプリケーションのトラブルシューティング {#troubleshoot-v2}

Adobe Experience Manager（AEM）デスクトップアプリケーションは、リモート Adobe Experience Manager デプロイメントのデジタルアセット管理（DAM）リポジトリに接続します。デスクトップアプリケーションは、ユーザーのコンピューター上でリポジトリ情報と検索結果を取得し、ファイルやフォルダーをダウンロードおよびアップロードします。また、AEM Assets ユーザーインターフェイスとの競合を管理する機能も備えています。

デスクトップアプリケーションのトラブルシューティング、ベストプラクティス、制限事項について説明します。

## ベストプラクティス {#best-practices-to-prevent-troubles}

一般的な問題の回避やトラブルシューティングを図るには、次のベストプラクティスに従います。

* **デスクトップアプリケーションの動作の仕組みを理解する**：使用を開始する前に、少し時間を割いてデスクトップアプリケーションの動作の仕組みを理解してください。Adobe Experience Manager の Web インターフェイスとデスクトップアプリケーションの連携、リポジトリマッピング、アセットキャッシング、ローカルでの保存、バックグラウンドでのアップロードについて把握します。[動作の仕組み](release-notes.md#how-app-works)を参照してください。

* **サポートされていない文字をフォルダー名に使用しない**：フォルダーの作成やアップロードの際には、空白や無効な文字を使用しないでください。該当する文字のリストについては、[Adobe Experience Manager Assets でのフォルダーの作成](https://docs.adobe.com/content/help/ja-JP/experience-manager-65/assets/managing/managing-assets-touch-ui.html#Creatingfolders)を参照してください。Adobe Experience Manager の一部の使用例では、サポートされていない文字がフォルダー名に使用されていた場合、影響を受ける可能性があります。

* **競合を回避するためのベストプラクティス**：複数のアセットに対する共同作業で競合が発生する可能性を避けるには、[編集上の競合の回避](using.md#adv-workflow-collaborate-avoid-conflicts)を参照してください。

* **大きな階層フォルダーにはフォルダーアップロードを使用する**：Assets Web インターフェイスなどの方法を使用するのではなく、Adobe Experience Manager デスクトップアプリケーションを使用して大きなフォルダーをアップロードしてください。デスクトップアプリケーションでは、ログ記録と監視をおこないながら、アセットをバックグラウンドでアップロードします。[アセットの一括アップロード](using.md#bulk-upload-assets)を参照してください。

* **最新バージョンを使用する**：常にデスクトップアプリケーションの最新バージョンを使用します。デスクトップアプリケーションの新しいバージョンをインストールする場合や Adobe Experience Manager の新しいバージョンにアップグレードする場合は、その前に必ず互換性を確認してください。[リリースノート](release-notes.md)を参照してください。

* **同じドライブ文字を使用する**：組織全体で同じドライブ文字を使用して、Adobe Experience Manager DAM にマッピングします。他のユーザーが配置したアセットを表示するには、同じパスを使用する必要があります。同じドライブ文字を使用することで、DAM アセットのパスが一定になります。別のユーザーが異なるドライブ文字を使用した場合でも、アセットはそのまま残り、削除されません。

* **ネットワークに注意を払う**：Adobe Experience Manager デスクトップアプリケーションのパフォーマンスには、ネットワークのパフォーマンスが重要です。ファイル転送や一括操作に対する応答が遅くなった場合は、大量のネットワークトラフィックを発生させる可能性のある機能やアプリを無効にしてください。

* **デスクトップアプリケーションでサポートされていない使用例**：Assets の移行（計画ツールなどのツールが必要）や負荷の高い DAM 操作（大きなフォルダーの移動、大規模なアップロード、高度なメタデータ検索を使用したファイル検索など）にはデスクトップアプリケーションを使用しません。また、同期クライアントとしても使用しないでください（Microsoft OneDrive や Adobe Creative Cloud デスクトップ同期などの同期クライアントとは設計原則や使用パターンが異なります）。

* **タイムアウト**：現在、デスクトップアプリケーションには、一定時間の経過後に Adobe Experience Manager サーバーとデスクトップアプリケーションの間の接続を切断するための設定可能なタイムアウト値がありません。サイズの大きいアセットをアップロードする際に、しばらくして接続がタイムアウトした場合、アプリケーションはアップロードタイムアウトを長くして、アセットのアップロードを数回再試行します。デフォルトのタイムアウト設定を変更するお勧めの方法はありません。

## トラブルシューティング方法 {#troubleshooting-prep}

デスクトップアプリケーションの問題をトラブルシューティングするには、以下の情報を把握しておいてください。また、それにより、サポートを依頼する場合にも、アドビカスタマーケアに問題を伝えやすくなります。

### デバッグモードの有効化 {#enable-debug-mode}

トラブルシューティングをおこなう場合、デバッグモードを有効にして、ログに詳細情報を取得できます。Mac においてバッグモードでアプリケーションを実行するには、ターミナルまたはコマンドプロンプトで次のコマンドラインオプションを使用します。`AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app`

Windows でデバッグモードを有効にするには、次の手順に従います。

1. デスクトップアプリケーションのインストールフォルダーで `Adobe Experience Manager Desktop.exe.config` ファイルを見つけます。デフォルトでは、フォルダーは `C:\Program Files\Adobe\Adobe Experience Manager Desktop` です。ファイルを保存して閉じます。

1. ファイルの末尾に向かって `<level value="INFO"/>` を見つけます。値を `DEBUG`（`<level value="DEBUG"/>`）に変更します。

1. デスクトップアプリケーションのインストールフォルダーで `logging.json` ファイルを見つけます。デフォルトでは、フォルダーは `C:\Program Files\Adobe\Adobe Experience Manager Desktop\javascript\` です。

1. `logging.json` ファイル内で、`level` パラメーターのすべてのインスタンスを見つけます。値を `info`から `debug` に変更します。ファイルを保存して閉じます。

1. アプリの環境設定で設定した場所にある、キャッシュされたディレクトリを消去します。

1. デスクトップアプリケーションを再起動します。

<!-- The Windows command doesn't work for now.
* On Windows: `SET AEM_DESKTOP_LOG_LEVEL=DEBUG & "C:\Program Files\Adobe\Adobe Experience Manager Desktop\Adobe Experience Manager Desktop.exe"`
-->

### ログファイルの場所 {#check-log-files-v2}

AEM デスクトップアプリケーションのログファイルは次の場所にあります。多数のアセットをアップロードする際に一部のファイルをアップロードできなかった場合は、`backend.log` ファイルを参照して、アップロードに失敗したファイルを特定します。

* Windows でのパス：`%LocalAppData%\Adobe\AssetsCompanion\Logs`

* Mac でのパス：`~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`

>[!NOTE]
>
>サポート依頼やサポートチケットに基づいてアドビカスタマーケアと共同でトラブルシューティングをおこなう場合は、問題がカスタマーケアチームに理解しやすいように、ログファイルの提供を求められる場合があります。`Logs` フォルダー全体をアーカイブして、カスタマーケアの担当者と共有します。

### キャッシュのクリア {#clear-cache-v2}

AEM デスクトップアプリケーションのキャッシュのクリアは、トラブルシューティングの予備的作業で、これによりいくつかの問題を解決できます。キャッシュのクリアは、アプリの環境設定からおこないます。[環境設定の指定](install-upgrade.md#set-preferences)を参照してください。キャッシュフォルダーのデフォルトの場所は次のとおりです。

* Windows の場合： `%LocalAppData%\Adobe\AssetsCompanion\Cache\`

* Mac の場合： `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/`

ただし、AEM デスクトップアプリケーションの AEM エンドポイントの設定によっては、場所が異なる場合があります。値は、ターゲット URL のエンコードされたバージョンです。例えば、アプリケーションのターゲットが `http://localhost:4502` の場合、ディレクトリ名は `http%3A%2F%2Flocalhost%3A4502%2F` となります。キャッシュをクリアするには、該当するフォルダーを削除します。キャッシュをクリアするもう 1 つの理由は、ディスク容量が不足している場合にディスク領域を解放するためです。

>[!CAUTION]
>
>AEM デスクトップアプリケーションのキャッシュをクリアすると、AEM サーバーに同期されていないローカルのアセット変更内容は失われます。

### AEM デスクトップアプリケーションのバージョンの把握 {#know-app-version-v2}

![アプリメニュー](assets/do-not-localize/more_options_da2.png) をクリックしてデスクトップアプリケーションのメニューを開き、**[!UICONTROL Help]**／**[!UICONTROL About]**&#x200B;を選択します。

## 配置されたアセットが表示されない {#placed-assets-missing}

サポートファイル（INDD ファイルなど）に自分自身または他のクリエイティブプロフェッショナルが配置したアセットが表示されない場合は、次の点を確認してください。

* サーバーへの接続。信頼性の低いネットワーク接続では、アセットのダウンロードが停止するおそれがあります。
* ファイルサイズ。サイズの大きいアセットは、ダウンロードと表示に時間がかかります。
* ドライブ文字の一貫性。AEM DAM を別のドライブ文字にマッピングしている間に、自分自身または他の共同利用者がアセットを配置した場合、配置されたアセットは表示されません。
* 権限。配置されたアセットを取得する権限があるかどうかを確認するには、AEM 管理者に問い合わせてください。

## macOS でアップグレードする際の問題 {#issues-when-upgrading-on-macos}

macOS で AEM デスクトップアプリケーションをアップグレードするときに問題が発生することがあります。これは、AEM デスクトップアプリケーションの古いシステムフォルダーによって、AEM デスクトップアプリケーションの新しいバージョンが正しく読み込まれなくなるからです。この問題を修正するには、以下のフォルダーおよびファイルを手動で削除します。

以下の手順を実行する前に、`Adobe Experience Manager Desktop` アプリケーションを macOS のアプリケーションフォルダーからゴミ箱にドラッグします。次に、ターミナルを開き、以下のコマンドを実行します。パスワードを求められたら入力します。

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

## ファイルをアップロードできない {#upload-fails}

デスクトップアプリケーションを AEM 6.5.1 以降で使用している場合は、S3 または Azure コネクタをバージョン 1.10.4 以降にアップグレードします。これで、[OAK-8599](https://issues.apache.org/jira/browse/OAK-8599) に関連するファイルアップロード失敗の問題が解決されます。[インストール手順](install-upgrade.md#install-v2)を参照してください。

## SSL 設定の問題 {#ssl-config-v2}

AEM デスクトップアプリケーションが HTTP 通信に使用するライブラリは SSL を厳格に適用します。ブラウザーでは成功する接続が、AEM デスクトップアプリケーションでは失敗することがあります。SSL を適切に設定するには、不足している中間証明書を Apache にインストールします。[中間 CA の証明書を Apache にインストールする](https://access.redhat.com/solutions/43575)を参照してください。

## デスクトップアプリケーションが応答しない {#unresponsive}

まれに、デスクトップアプリケーションが応答しなくなって、白い画面だけが表示されたり、インターフェイスにオプションが表示されずにインターフェイスの下部にエラーが表示されたりする場合があります。このような場合には、以下をこの順に試します。

* デスクトップアプリケーションインターフェイスを右クリックし、「**[!UICONTROL Refresh]**」を選択します。
* アプリケーションを終了して、再度開きます。

どちらの方法でも、DAM のルートフォルダーがデスクトップアプリケーションの初期状態として表示されます。

>[!MORELIKETHIS]
>
>* [既知の問題](release-notes.md#known-issues-v2)
>* [編集上の競合の回避](using.md#adv-workflow-collaborate-avoid-conflicts)