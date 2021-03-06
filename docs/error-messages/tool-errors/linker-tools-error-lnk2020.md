---
title: "リンカ ツール エラー LNK2020 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2020
dev_langs:
- C++
helpviewer_keywords:
- LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 394cafe23851df5320a78a4e165a90422fc305de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2020"></a>リンカ ツール エラー LNK2020
未解決のトークン 'token'  
  
 未定義の外部エラーに似ていますが、参照がメタデータからです。 メタデータですべての関数とデータを定義する必要があります。  
  
 解決するのには  
  
-   不足している関数またはデータ定義または  
  
-   オブジェクト ファイルまたは不足している関数またはデータが既に定義されているライブラリが含まれます。  
  
## <a name="example"></a>例  
 次の例では、LNK2020 が生成されます。  
  
```  
// LNK2020.cpp  
// compile with: /clr /LD  
ref struct A {  
   A(int x);   // LNK2020  
   static int f();   // LNK2020  
};  
  
// OK  
ref struct B {  
   B(int x) {}  
   static int f() { return 0; }  
};  
```  
  
## <a name="example"></a>例  
 LNK2020 は、管理されているテンプレートの種類の変数を作成することが、型をインスタンス化しない場合にも発生します。  
  
 次の例では、LNK2020 が生成されます。  
  
```  
// LNK2020_b.cpp  
// compile with: /clr   
  
template <typename T>  
ref struct Base {  
   virtual void f1() {};  
};  
  
template <typename T>  
ref struct Base2 {  
   virtual void f1() {};  
};  
  
int main() {  
   Base<int>^ p;   // LNK2020  
   Base2<int>^ p2 = gcnew Base2<int>();   // OK  
};  
```