---
title: "コンパイラ エラー C2550 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2550
dev_langs:
- C++
helpviewer_keywords:
- C2550
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5375982b6a0140694c668f5be6b54f182b81ec5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2550"></a>コンパイラ エラー C2550
'identifier': コンス トラクター初期化子リストはコンス トラクターの定義だけに許されます。  
  
 基底クラスの初期化子リストは、コンス トラクターではない関数の定義で使用されます。  
  
 次の例では、C2550 が生成されます。  
  
```  
// C2550.cpp  
// compile with: /c  
class C {  
public:  
   C();  
};  
  
class D : public C {  
public:  
   D();  
   void func();  
};  
  
void D::func() : C() {}  // C2550  
D::D() : C() {}   // OK  
```