---
title: "コンパイラ エラー C2896 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2896
dev_langs:
- C++
helpviewer_keywords:
- C2896
ms.assetid: b600407b-cb05-42e3-9069-2aa6960f0eaa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 33be17290af0c678d080f0164c63d39c5893be70
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2896"></a>コンパイラ エラー C2896
'function1': 関数テンプレート 'function2' を引数として使用できません  
  
 関数テンプレートは、別の関数テンプレートの引数にすることはできません。  
  
 次の例では、C2896 が生成されます。  
  
```  
// C2896.cpp  
template<class T1, class T2> void f1(void(*)(T1, T2));  
template<class T1, class T2> void f2(T1, T2);  
  
int main() {  
   f1(f2);   // C2896  
}  
```  
  
 C2896 は、ジェネリックを使用するときにも発生することができます。  
  
```  
// C2896b.cpp  
// compile with: /clr  
generic<class T1> void gf1(T1){}  
generic<class T1> void gf2(T1){}  
  
int main() {  
   gf1(gf2);   // C2896  
   gf1(1);   // OK  
}  
```