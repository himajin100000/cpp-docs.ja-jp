---
title: "コンパイラ エラー C2369 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2369
dev_langs:
- C++
helpviewer_keywords:
- C2369
ms.assetid: 2a3933f6-2313-40ff-800f-921b296fdbbf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dc635f4527c40adb09d76d8fa57ae6837203b57d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2369"></a>コンパイラ エラー C2369
'array': 再定義されています。異なる添字です  
  
 配列は異なる添字で既に宣言されています。  
  
 次の例では C2369 が生成されます。  
  
```  
// C2369.cpp  
// compile with: /c  
int a[10];  
int a[20];   // C2369  
int b[20];   // OK  
```