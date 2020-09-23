---
title: Adobe Experience Manager デスクトップアプリケーションの概要
description: Adobe Experience Manager Assets をデスクトップから直接使用する場合、Adobe Experience Manager デスクトップアプリケーションを使用してクリエイティブユーザーのアセット管理ワークフローを最適化する方法について説明します。
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.5/ASSETS, SG_EXPERIENCEMANAGER/6.4/ASSETS, SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 39d7bcad-d7b0-4978-a790-4cb68b8a7d6a
snippet: y
translation-type: tm+mt
source-git-commit: 6a8a49865d2707f5d60fbd6d5e99b597c333d3d5
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 100%

---


# Adobe Experience Manager デスクトップアプリケーションの概要 {#overview-v2}

アドビでは、事業部門のユーザーやクリエイティブプロフェッショナルの生産性を向上させるために、ソリューション間をつなぐコネクテッドワークフローを提供しています。Adobe Experience Manager デスクトップアプリケーションは、Adobe Experience Manager リポジトリとアドビ製およびサードパーティ製のデスクトップアプリケーションとを接続することで、リソースへのすばやいアクセスとワークフローの効率化を実現します。これにより、作業にかかる時間や工数が減るので、デスクトップワークフローで Adobe Experience Manager のアセットを使用するユーザーの作業効率が向上します。

Adobe Experience Manager デスクトップアプリケーションを使用すると、Adobe Experience Manager Assets 内のアセットにローカルデスクトップから手軽にアクセスし、任意のデスクトップアプリケーションで利用できるようになります。任意のデスクトップアプリケーションでアセットを開いて編集できます。ローカル編集は、変更内容をアップロードする場合にのみ、アセットの新しいバージョンとして Adobe Experience Manager で公開されます。これにより、デスクトップ上で作業中のアセットの編集を効率的に処理できます。デスクトップアプリケーションでは、アセットおよびネストしたフォルダーの Adobe Experience Manager へのアップロードをサポートしているので、リポジトリへの新しいコンテンツの追加を簡単におこなえます。

このような統合により、組織内の様々な役割のユーザーがアセットを Adobe Experience Manager Assets で一元管理できます。マーケティング担当者やビジネスユーザーは、ブランディングやライセンスなどの様々な標準に確実に準拠できます。また、Adobe Photoshop、Illustrator、InDesign でアセットを操作するための専用の [Adobe Asset Link](https://www.adobe.com/jp/marketing/experience-manager-assets/adobe-asset-link.html) ツールを利用できるクリエイティブユーザーは、Creative Cloud アプリケーションなどのネイティブアプリケーションのデスクトップ上でアセットにアクセスすることもできます。

>[!NOTE]
>
>Adobe Experience Manager デスクトップアプリケーション（旧称 Adobe Experience Manager Assets Companion App）は、Adobe Experience Manager 6.1 リリースで導入されました。アプリのバージョン 1.x について詳しくは、左側のサイドバーの目次を参照してください。アドビでは、最新バージョン v2 へのアップグレードをお勧めします。

デスクトップアプリケーションのドキュメントには、次の役割と使用例に対応する情報が含まれています。

| 必要な情報 | ヘルプの目次 |
|--- |--- |
| 最新バージョンの新機能と機能強化の概要 | [デスクトップアプリケーションの新機能](#whats-new-v2) |
| 前提条件と技術仕様。ダウンロードリンク | [リリースノート](release-notes.md) |
| デスクトップアプリケーションの既存ユーザーの場合は、アップグレードと移行をスムーズに進める方法 | [以前のバージョンからのアップグレード](install-upgrade.md#upgrade-from-previous-version) |
| 導入方法。デフォルトの環境設定を調整する方法 | [デスクトップアプリケーションのインストールと設定](install-upgrade.md) |
| アセットの参照、検出、編集、アップロード、競合の解決、一括操作などをおこなう方法 | [Adobe Experience Manager デスクトップアプリケーションの使用](using.md) |
| 問題が発生した場合のトラブルシューティングに役立つ情報 | [Adobe Experience Manager デスクトップアプリケーションのトラブルシューティング](troubleshoot.md) |

## デスクトップアプリケーションの新機能 {#whats-new-v2}

以前のバージョンに対する数々の改善を提供するために、デスクトップアプリケーション v2.0 が新規に作成されました。この新しいバージョンは、より使いやすく、新しいアプリケーション UI を備えた専用のデスクトップエクスペリエンスを提供します。Adobe Experience Manager インターフェイスを使用しなくても、検索や参照による検出、開く、編集、変更内容のアップロード、新規アセットのアップロードなど、アセットに対する操作をおこなうことができます。このバージョンでは、Adobe Experience Manager インターフェイスからファイルを開くこともできます。

この新しいデスクトップアプリケーションでは、以前と同じ使用例に対応しながら、ユーザーエクスペリエンスを大幅に改善しました。主要な改善点を以下に示します。

* Mac Finder や Windows エクスプローラーを使用して仮想ネットワーク共有を表示するのではなく、デスクトップアプリケーションの組み込みブラウザーを使用した参照および検索でアセットを検出できます。

* 使用可能なアクションに関する明確なガイダンスが用意されています。

* 帯域幅の使用量を減らすことで、パフォーマンスが向上しました。元のバイナリファイルは、必要な場合にのみダウンロードされます。アセットの参照と検索の場合には、小さなサムネールのみ転送されます。

* 一括アップロードなどの一括操作に最適化されています。

新しいデスクトップアプリケーションの主な使用例と機能強化は、次の図に示すカスタマージャーニーに対応しています。

![Adobe Experience Manager デスクトップアプリケーションの新機能](assets/aem_desktop_app_usecases_v2.png)

デスクトップアプリケーションを使用すると、上記のすべての使用例をデスクトップアプリケーション内から直接実行できます。必要に応じて、Web インターフェイスでアセットの検出をおこなった後、デスクトップアプリケーションに制御を渡し、アセットを開いて編集することもできます。
