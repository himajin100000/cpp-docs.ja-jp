---
title: CString の例外の後処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 496fdfe6a609bd4eceae225c2568c915d38aef07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cstring-exception-cleanup"></a>文字列: CString の例外の後処理
MFC の以前のバージョンでクリーンアップを行うことが重要でした[CString](../atl-mfc-shared/reference/cstringt-class.md)使用後にオブジェクト。 MFC バージョン 3.0 以降では、明示的なクリーンアップが必要な不要です。  
  
 C++ 例外処理機構 MFC が使用する、例外の後のクリーンアップについて心配する必要はありません。 方法の詳細については C++""がスタックをアンワインド例外がキャッチされた後は、「 [try catch、および throw ステートメント](../cpp/try-throw-and-catch-statements-cpp.md)です。 MFC を使用する場合でも**を再試行してください**/**キャッチ**C++ のキーワードの代わりにマクロ**を再試行してください**と**キャッチ**MFC で C++ を使用下には、例外処理機構それでもようにする必要はありませんを明示的にクリーンアップします。  
  
## <a name="see-also"></a>参照  
 [文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [例外処理](../mfc/exception-handling-in-mfc.md)

