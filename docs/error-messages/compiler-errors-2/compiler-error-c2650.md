---
title: "コンパイラ エラー C2650 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2650
dev_langs:
- C++
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b975eb131951712fd5615041dcdb2391784e8003
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2650"></a>コンパイラ エラー C2650
'operator': 仮想関数をすることはできません  
  
 A`new`または`delete`演算子が宣言されて`virtual`です。 これらの演算子は`static`メンバー関数し、することはできません`virtual`です。  
  
## <a name="example"></a>例  
 次の例では、C2650 が生成されます。  
  
```  
// C2650.cpp  
// compile with: /c  
class A {  
   virtual void* operator new( unsigned int );   // C2650  
   // try the following line instead  
   // void* operator new( unsigned int );  
};  
```