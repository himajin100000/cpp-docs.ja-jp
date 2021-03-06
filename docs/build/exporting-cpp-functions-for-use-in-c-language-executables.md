---
title: "C 言語の実行可能ファイルで使う C++ 関数のエクスポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], C++ functions in C executables
- exporting DLLs [C++], C++ functions in C executables
- exporting functions [C++], C++ functions in C executables
- functions [C++], exporting
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0511ae4c16332b2a8e98c2319e148249b66c8461
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exporting-c-functions-for-use-in-c-language-executables"></a>C 言語の実行形式で使う C++ 関数のエクスポート  
  
C++ で記述された DLL 内の関数に C 言語のモジュールからアクセスするには、C++ リンケージではなく C リンケージを使って関数を宣言する必要があります。 特に指定しない限り、C++ コンパイラは C++ のタイプ セーフな名前付け規約 (名前の装飾) と C++ の呼び出し規則を使います。C++ の規約を使うと、C からの呼び出しが難しくなります。  
  
C リンケージを指定する`extern "C"`関数の宣言にします。 例:  
  
```  
extern "C" __declspec( dllexport ) int MyFunc(long parm1);  
```  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [.Def ファイルを使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [関数を使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS を使ったエクスポート/インポート](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C または C++ 言語の実行可能ファイルで使用するための C 関数をエクスポートします。](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [エクスポート方式を使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [_Declspec (dllimport) を使用してアプリケーションをインポートします。](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL を初期化します。](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [装飾名](../build/reference/decorated-names.md)  
  
-   [extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)  
  
## <a name="see-also"></a>参照  
 [DLL からのエクスポート](../build/exporting-from-a-dll.md)