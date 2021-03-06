---
title: "典型的なインターネット クライアント アプリケーションでの手順 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], general table
- WinInet classes [MFC], programming
- Internet applications [MFC], client applications
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ce4f5b91ebd68f13510f887c65927dbe5f84133
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="steps-in-a-typical-internet-client-application"></a>典型的なインターネット クライアント アプリケーションの作成手順
次の表は、典型的なインターネット クライアント アプリケーションで必要な手順を示します。  
  
|目標|操作を実行します。|効果|  
|---------------|----------------------|-------------|  
|インターネット セッションを開始します。|作成、 [CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクト。|WinInet を初期化し、サーバーに接続します。|  
|タイムアウトの制限 (たとえばの再試行の回数) のインターネット クエリ オプションを設定します。|使用して[CInternetSession::SetOption](../mfc/reference/cinternetsession-class.md#setoption)です。|操作が成功した場合は、FALSE を返します。|  
|セッションの状態を監視するコールバック関数を確立します。|使用して[CInternetSession::EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback)です。|コールバックを確立[:onstatuscallback](../mfc/reference/cinternetsession-class.md#onstatuscallback)です。 オーバーライド`OnStatusCallback`を独自のコールバック ルーチンを作成します。|  
|インターネット サーバー、イントラネット サーバー、またはローカル ファイルに接続します。|使用して[できます](../mfc/reference/cinternetsession-class.md#openurl)です。|URL を解析し、指定されたサーバーへの接続を開きます。 返します、 [CStdioFile](../mfc/reference/cstdiofile-class.md) (を渡した場合`OpenURL`ローカルのファイル名)。 これは、サーバーまたはファイルから取得されたデータにアクセスするオブジェクトです。|  
|ファイルから読み取られました。|使用して[細かい](../mfc/reference/cinternetfile-class.md#read)です。|指定した数の入力バッファーを使用してバイトを読み取ります。|  
|例外を処理する|使用して、 [CInternetException](../mfc/reference/cinternetexception-class.md)クラスです。|すべての一般的なインターネット例外タイプを処理します。|  
|インターネット セッションを終了します。|破棄、 [CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクト。|開いているファイル ハンドルと接続を自動的にクリーンアップします。|  
  
## <a name="see-also"></a>参照  
 [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット クライアント クラスの前提条件](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
