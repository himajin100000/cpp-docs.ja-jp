---
title: "コンパイラ エラー C3668 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3668
dev_langs:
- C++
helpviewer_keywords:
- C3668
ms.assetid: 53a96698-bde4-4447-95b5-b5108291f60c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7cb10e80a28526ec83db2bbca388be990a08466d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3668"></a>コンパイラ エラー C3668
'method': オーバーライド指定子 'override' を持つメソッドは、基底クラス メソッドをオーバーライドしませんでした  
  
 関数が存在しない関数をオーバーライドしようとするとします。  
  
 詳細については、次を参照してください。[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3668 を生成します。  
  
```  
// C3668.cpp  
// compile with: /c  
__interface I {  
   void f(int);   // virtual by default  
};  
  
class J {  
public:  
   void g(int);  
   virtual void h(int);  
};  
  
struct R : I,J {  
   virtual void f() override {}   // C3668  
   virtual void f(int) override {}   // OK  
  
   virtual void g(int) override {}   // C3668  
   virtual void h(int) override {}   // OK  
};  
```