---
title: "コンパイラの警告 (レベル 4) C4336 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4336
dev_langs:
- C++
helpviewer_keywords:
- C4336
ms.assetid: 93f199dd-d6dd-42c0-82d8-c12d101a7235
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 524d5d1aab2b63854ec334f6eb94a62e9fb127c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4336"></a>コンパイラの警告 (レベル 4) C4336
クロスレファレンスしたタイプ ライブラリ 'type_lib1' を 'type_lib2' をインポートする前にインポートします。  
  
 タイプ ライブラリが参照された、 [#import](../../preprocessor/hash-import-directive-cpp.md)ディレクティブです。 ただし、タイプ ライブラリがで参照されていない別のタイプ ライブラリへの参照を含まれている`#import`です。 コンパイラによってこの別の .tlb ファイルが見つかりました。  
  
 (Midl.exe でコンパイルされた) 次の 2 つのファイルから作成されたディスクに指定された 2 つのタイプ ライブラリ:  
  
```  
// c4336a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library c4336aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C4336  
   {  
      one, two, three  
   };  
};  
```  
  
 2 番目のタイプ ライブラリ:  
  
```  
// c4336b.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
library C4336bLib  
{  
   importlib ("c4336a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
   struct S_C4336  
   {  
      enum E_C4336 e;  
   };  
};  
```  
  
 次の例では、C4336 が生成されます。  
  
```  
// C4336.cpp  
// compile with: /W4 /LD  
// #import "C4336a.tlb"  
#import "C4336b.tlb"   // C4336, uncomment previous line to resolve  
```