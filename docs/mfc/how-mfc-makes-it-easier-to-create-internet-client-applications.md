---
title: MFC を使って方法を簡単にインターネット クライアント アプリケーションを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6270cdd3e64d24f1c2000acb9e8466f8c85edba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-mfc-makes-it-easier-to-create-internet-client-applications"></a>MFC を使ってインターネット クライアント アプリケーションを簡単に作成する方法
Microsoft Foundation Classes は、MFC プログラマのため、使い慣れたコンテキストを提供する方法で Win32 インターネット拡張機能 (WinInet) 機能をカプセル化します。 MFC には、次の 3 つのインターネット ファイルのクラスが用意されています ([CInternetFile](../mfc/reference/cinternetfile-class.md)、 [CHttpFile](../mfc/reference/chttpfile-class.md)、および[CGopherFile](../mfc/reference/cgopherfile-class.md)) から派生した、 [CStdioFile](../mfc/reference/cstdiofile-class.md)クラス. だけでなくはこれらのクラスを取得して、インターネットのデータの操作を使用したプログラマになじみ`CStdioFile`ローカル ファイルとインターネットのファイルを処理、透過的な一貫性のある方法で、ローカル ファイル、これらのクラスとします。  
  
 MFC WinInet クラスと同じ機能を提供する`CStdioFile`インターネット経由で転送されるデータ用です。 これらのクラスは、高度なアプリケーション プログラミング インターフェイス、インターネット対応のアプリケーションを提供するために高速で単純なパスを指定するのに HTTP、FTP、および gopher インターネット プロトコルを抽象化します。 たとえば、低レベルは、いくつかの手順が必要に FTP サーバーに接続する MFC 開発者の場合は、のみする必要しますが、あります 1 つの呼び出しを行う`CInternetSession::GetFTPConnection`その接続を作成します。  
  
 また、MFC WinInet クラスには、次の利点が提供します。  
  
-   バッファー内の I/O  
  
-   データのタイプ セーフ ハンドル  
  
-   多くの関数の既定のパラメーター  
  
-   インターネットの一般的なエラーの例外処理  
  
-   開いているハンドルと接続の自動クリーンアップ  
  
## <a name="see-also"></a>参照  
 [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [WinInet を使ってインターネット クライアント アプリケーションを簡単に作成する方法](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)

