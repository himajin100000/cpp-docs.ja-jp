---
title: コンパイラ エラー C3915 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3915
dev_langs:
- C++
helpviewer_keywords:
- C3915
ms.assetid: 2b0a5e5f-3aec-4a4b-9157-233031817084
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba1c6e2ecb81796058cc6d31227a313b25979ecf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3915"></a>コンパイラ エラー C3915
'type' には、既定のインデックス付きプロパティ (クラス インデクサー) がありません。  
  
 型には、既定、インデックス付きプロパティがありません。  
  
 詳細については、「 [property](../../windows/property-cpp-component-extensions.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、C3915 を生成します。  
  
```  
// C3915.cpp  
// compile with: /clr  
ref class X {  
public:  
// uncomment property to resolve this C3915  
//   property int default[]  
//   {  
//      int get(int i)  
//      {  
//         return 863;  
//      }  
//   }  
};  
  
int main() {  
   X^ x = new X;  
   System::Console::WriteLine(x[1]);   // C3915  
}  
```  
  
## <a name="example"></a>例  
 C3915 で定義されている同じコンパイル単位で既定のインデクサーを使用しようとする場合にも発生することができます<xref:System.Reflection.DefaultMemberAttribute>です。  
  
 次の例では、C3915 を生成します。  
  
```  
// C3915_b.cpp  
// compile with: /clr  
using namespace System;  
  
[Reflection::DefaultMember("XXX")]  
ref struct A {  
   property Double XXX[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
};  
  
ref struct B {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
};  
  
int main() {  
   A ^ mya = gcnew A();  
   Console::WriteLine("{0}", mya[3]);   // C3915  
  
   B ^ myb = gcnew B();  
   Console::WriteLine("{0}", myb[3]);   // OK  
}  
```