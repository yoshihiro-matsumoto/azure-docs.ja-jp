---
title: "Azure IoT への Raspberry Pi (C) の接続 - レッスン 1: ツールの入手 (Windows) | Microsoft Docs"
description: "Windows 7 以降で、Pi の最初のサンプル アプリケーションに必要なツールとソフトウェアをダウンロードしてインストールします。"
services: iot-hub
documentationcenter: 
author: shizn
manager: timtl
tags: 
keywords: "IoT 開発, IoT ソフトウェア, モノのインターネット ソフトウェア, Windows での Git のインストール, Windows での Node.js のインストール, Windows での NPM のインストール"
ms.assetid: bd765ddd-65b7-4241-a391-dc77cb3af1c0
ms.service: iot-hub
ms.devlang: c
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 3/21/2017
ms.author: xshi
translationtype: Human Translation
ms.sourcegitcommit: 64e69df256404e98f6175f77357500b562d74318
ms.openlocfilehash: d53efc7d25714427e25d4f88279f3b0d4f61c150
ms.lasthandoff: 01/24/2017


---
# <a name="get-the-tools-windows-7-or-later"></a>ツールの入手 (Windows 7 以降)

> [!div class="op_single_selector"]
> * [Windows 7 以降](iot-hub-raspberry-pi-kit-c-lesson1-get-the-tools-win32.md)
> * [Ubuntu 16.04](iot-hub-raspberry-pi-kit-c-lesson1-get-the-tools-ubuntu.md)
> * [macOS 10.10](iot-hub-raspberry-pi-kit-c-lesson1-get-the-tools-mac.md)

## <a name="what-you-will-do"></a>学習内容
Raspberry Pi 3 の最初のサンプル アプリケーション用の開発ツールとソフトウェアをダウンロードします。 問題が発生した場合は、[トラブルシューティングのページ](iot-hub-raspberry-pi-kit-c-troubleshooting.md)で解決策を探してください。

> [!NOTE]
> メイン ロジックのプログラミング言語は C ですが、レッスンでは、デバイスの検出とサンプル アプリケーションの構築およびデプロイに Node.js ツールを使用します。

## <a name="what-you-will-learn"></a>学習内容
この記事では、次のことについて説明します。

* Git と Node.js をインストールする方法。
  * [Git](https://git-scm.com) は、オープン ソースの分散型バージョン管理システムです。 この記事のサンプル アプリケーションは、Git に格納されています。
  * [Node.js](https://nodejs.org/en/) は、豊富なパッケージ エコシステムが存在する JavaScript ランタイムです。
* NPM を使って、追加の Node.js 開発ツールをインストールする方法。
  * Node.js の最低限必要なバージョンは 4.5 LTS です。
  * [NPM](https://www.npmjs.com) は、Node.js のパッケージ マネージャーの&1; つです。

## <a name="what-you-need"></a>必要なもの

この操作を完了するには、以下が必要です。

* インターネット接続 (開発ツールとソフトウェアをダウンロードするため)。
* Windows を実行しているコンピューター。

## <a name="install-git-and-nodejs"></a>Git と Node.js のインストール

以下のリンクをクリックして、Windows 用の Git と Node.js LTS をダウンロードしてインストールします。

* [Git for Windows の入手](https://git-scm.com/download/win/)
* [Windows 用の Node.js LTS の入手](https://nodejs.org/en/)

## <a name="install-additional-nodejs-development-tools"></a>追加の Node.js 開発ツールのインストール

[gulp.js](http://gulpjs.com) を使って、Pi へのサンプル アプリケーションのデプロイを自動化します。 また、[device-discovery-cli](https://github.com/Azure/device-discovery-cli) を使って、IoT デバイスのネットワーク情報を取得します。

管理者としてコマンド プロンプトを起動します。 次のコマンドを実行して、`gulp` と `device-discovery-cli` をインストールします。

```bash
npm install -g device-discovery-cli gulp
```

コンピューターで Node.js やこれらの追加の開発ツールをインストールする際に問題が発生した場合、一般的な問題の解決策については、[トラブルシューティング ガイド](iot-hub-raspberry-pi-kit-c-troubleshooting.md)を参照してください。

## <a name="install-visual-studio-code"></a>Visual Studio Code のインストール

Visual Studio Code を[ダウンロード](https://code.visualstudio.com/docs/setup/windows)して、インストールします。 Visual Studio Code は、Windows、Linux、macOS 向けの軽量で強力なソース コード エディターです。 チュートリアルの後半で、このエディターを使ってサンプル コードを編集します。

## <a name="summary"></a>概要

最初のサンプル アプリケーションに必要な開発ツールとソフトウェアをインストールしました。 次のタスクでは、サンプル アプリケーションを作成し、Pi にデプロイして、実行します。

## <a name="next-steps"></a>次のステップ

[点滅アプリケーションを作成してデプロイする](iot-hub-raspberry-pi-kit-c-lesson1-deploy-blink-app.md)

