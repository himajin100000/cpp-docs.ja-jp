---
title: "コンパイラの警告 (レベル 1) C4997 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4997
dev_langs:
- C++
helpviewer_keywords:
- C4997
ms.assetid: d39678fd-0c1a-4104-8a45-9e3f20de0407
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f23fe4ba0c12b12ca71412f88fb3fea3f6a07da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4997"></a>コンパイラの警告 (レベル 1) C4997
'class': コクラスは COM インターフェイスまたは擬似インターフェイスを実装しません  
  
 [coclass](../../windows/coclass.md) 属性でマークされているクラスがインターフェイスを実装しませんでした。  
  
 次の例では C4997 が生成されます。  
  
```  
// C4997.cpp  
// compile with: /WX  
// to resolve this C4997, uncomment all code  
#include <objbase.h>  
  
[ object ]  
__interface I {  
   HRESULT func();  
};  
  
[ coclass ]  
struct C /*: I*/ {  
   /*  
   HRESULT func() {  
      return S_OK;  
   }  
   */  
};   // C4997  
```