---
title: "コンパイラ エラー C3490 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3490
dev_langs:
- C++
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6439b48dc752d2bed01371cae59b2d77db16f1f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3490"></a>コンパイラ エラー C3490
'var' は const オブジェクトを通じてアクセスされているため変更できません  
  
 `const` メソッドで宣言されているラムダ式は、変更不能なメンバー データを変更することはできません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   メソッド宣言から `const` 修飾子を削除します。  
  
## <a name="example"></a>例  
 次の例では、 `_i` メソッドでメンバー変数 `const` を変更するため、C3490 が生成されます。  
  
```  
// C3490a.cpp  
// compile with: /c  
  
class C  
{  
   void f() const   
   {  
      auto x = [=]() { _i = 20; }; // C3490  
   }  
  
   int _i;  
};  
```  
  
## <a name="example"></a>例  
 次の例では、メソッド宣言から `const` 修飾子を削除して C3490 を解決します。  
  
```  
// C3490b.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      auto x = [=]() { _i = 20; };  
   }  
  
   int _i;  
};  
```  
  
## <a name="see-also"></a>参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)