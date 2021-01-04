---
title: ' [!DNL Adobe Experience Manager] デスクトップアプリの紹介'
description: デスクトップから直接 [!DNL Adobe Experience Manager] desktop app to optimize the asset management workflows for creative users when using [!DNL Adobe Experience Manager Assets] を使用する方法を学びます。
translation-type: tm+mt
source-git-commit: a25c1fa13895ae9eb7268e3e01c83a5f0b9d7d1d
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 68%

---


# [!DNL Adobe Experience Manager] デスクトップアプリの概要  {#overview-v2}

アドビでは、事業部門のユーザーやクリエイティブプロフェッショナルの生産性を向上させるために、ソリューション間をつなぐコネクテッドワークフローを提供しています。[!DNL Adobe Experience Manager]デスクトップアプリケーションは、リポジトリとデスクトップアプリケーション(Adobeやサードパーティのアプリケーションを含む)を接続し、リソースへの迅速なアクセスと合理化されたワークフローを提供します。 この時間の節約と労力の削減により、デスクトップワークフローーで[!DNL Adobe Experience Manager]のアセットを扱うユーザーの効率が向上します。

[!DNL Experience Manager Assets]内のアセットは、アプリを使用すると、ローカルデスクトップ上で簡単にアクセスでき、どのデスクトップアプリケーションでも使用できます。 任意のデスクトップアプリケーションでアセットを開いて編集できます。ローカル編集は、変更をアップロードする場合にのみ、新しいバージョンのアセットとして[!DNL Experience Manager]で利用できます。これにより、デスクトップ上で作業中のアセットの編集を効率的に処理できます。 このアプリケーションは、[!DNL Experience Manager]へのアセットとネストされたフォルダーのアップロードをサポートしており、リポジトリへの新しいコンテンツの追加を簡略化しています。

このような統合により、組織の様々な役割が[!DNL Experience Manager Assets]内でアセットを一元的に管理できます。 マーケティング担当者やビジネスユーザーは、ブランディングやライセンスなどの様々な標準に確実に準拠できます。また、Adobe Photoshop、Illustrator、InDesign でアセットを操作するための専用の [Adobe Asset Link](https://www.adobe.com/jp/marketing/experience-manager-assets/adobe-asset-link.html) ツールを利用できるクリエイティブユーザーは、Creative Cloud アプリケーションなどのネイティブアプリケーションのデスクトップ上でアセットにアクセスすることもできます。

>[!NOTE]
>
>[!DNL Adobe Experience Manager] デスクトップアプリは、 [!DNL Adobe Experience Manager] 6.1リリースで導入され、以前は [!DNL Adobe Experience Manager Assets] Companion Appと呼ばれていました。アプリのバージョン 1.x について詳しくは、左側のサイドバーの目次を参照してください。アドビでは、最新バージョン v2 へのアップグレードをお勧めします。

デスクトップアプリケーションのドキュメントには、次の役割と使用例に対応する情報が含まれています。

| 必要な情報 | ヘルプの目次 |
|--- |--- |
| 最新バージョンの新機能と機能強化の概要 | [デスクトップアプリケーションの新機能](#whats-new-v2) |
| 前提条件と技術仕様。ダウンロードリンク | [リリースノート](release-notes.md) |
| デスクトップアプリケーションの既存ユーザーの場合は、アップグレードと移行をスムーズに進める方法 | [以前のバージョンからのアップグレード](install-upgrade.md#upgrade-from-previous-version) |
| 導入方法。デフォルトの環境設定を調整する方法 | [デスクトップアプリケーションのインストールと設定](install-upgrade.md) |
| アセットの参照、検出、編集、アップロード、競合の解決、一括操作などをおこなう方法 | [ [!DNL Experience Manager]  デスクトップアプリケーションの使用 ](using.md) |
| 問題が発生した場合のトラブルシューティングに役立つ情報 | [ [!DNL Experience Manager]  デスクトップアプリケーションのトラブルシューティング](troubleshoot.md) |

## デスクトップアプリケーションの新機能 {#whats-new-v2}

以前のバージョンに対する数々の改善を提供するために、デスクトップアプリケーション v2.0 が新規に作成されました。この新しいバージョンは、より使いやすく、新しいアプリケーション UI を備えた専用のデスクトップエクスペリエンスを提供します。ユーザは、[!DNL Experience Manager]インターフェイスを使用しなくても、検索または参照、開く、編集、変更のアップロード、新しいアセットのアップロードを行うことができます。 このバージョンでは、[!DNL Experience Manager]インターフェイスからファイルを開くこともサポートしています。

この新しいデスクトップアプリケーションでは、以前と同じ使用例に対応しながら、ユーザーエクスペリエンスを大幅に改善しました。主要な改善点を以下に示します。

* Mac Finder や Windows エクスプローラーを使用して仮想ネットワーク共有を表示するのではなく、デスクトップアプリケーションの組み込みブラウザーを使用した参照および検索でアセットを検出できます。

* 使用可能なアクションに関する明確なガイダンスが用意されています。

* 帯域幅の使用量を減らすことで、パフォーマンスが向上しました。元のバイナリファイルは、必要な場合にのみダウンロードされます。アセットの参照と検索の場合には、小さなサムネールのみ転送されます。

* 一括アップロードなどの一括操作に最適化されています。

新しいデスクトップアプリケーションの主な使用例と機能強化は、次の図に示すカスタマージャーニーに対応しています。

![[!DNL Experience Manager] デスクトップアプリケーションの新機能 ](assets/aem_desktop_app_usecases_v2.png)

デスクトップアプリケーションを使用すると、上記のすべての使用例をデスクトップアプリケーション内から直接実行できます。必要に応じて、Web インターフェイスでアセットの検出をおこなった後、デスクトップアプリケーションに制御を渡し、アセットを開いて編集することもできます。
