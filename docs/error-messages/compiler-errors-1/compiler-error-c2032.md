---
title: "コンパイラ エラー C2032 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2032
dev_langs:
- C++
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 87703c289dc522f62c29fd2110e969fd44abf645
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2032"></a>コンパイラ エラー C2032
'identifier': 関数 'structorunion' の構造体/共用体のメンバーであることはできません  
  
 構造体または共用体が C ではありませんが、C++ では許可されているメンバー関数エラーを解決するには、C++ プログラムとしてコンパイルするか、メンバー関数を削除します。  
  
 次の例では、C2032 が生成されます。  
  
```  
// C2032.c  
struct z {  
   int i;  
   void func();   // C2032  
};  
```  
  
 考えられる解決方法:  
  
```  
// C2032b.c  
// compile with: /c  
struct z {  
   int i;  
};  
```