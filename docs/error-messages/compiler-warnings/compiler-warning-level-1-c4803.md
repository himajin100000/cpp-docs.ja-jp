---
title: "コンパイラの警告 (レベル 1) C4803 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4803
dev_langs:
- C++
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b6725685e84e1c9ce0fc5c3f58f4ff163870d278
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4803"></a>コンパイラの警告 (レベル 1) C4803
'method': raise メソッドが、イベントと異なるストレージ クラス 'event'  
  
イベント メソッドは、イベントの宣言と同じ記憶域クラスにあります。 コンパイラは、ストレージ クラスが同じになるように、イベントのメソッドを調整します。  
  
この警告は、インターフェイスからイベントを実装するクラスがある場合に発生することができます。 コンパイラに暗黙的に生成しませんイベントに raise メソッド インターフェイス内で。 クラスでそのインターフェイスを実装するときに、コンパイラが raise メソッドを生成して暗黙的にしてそのメソッドは仮想、そのため、警告します。 イベントの詳細については、次を参照してください。[イベント](../../windows/event-cpp-component-extensions.md)です。  
  
参照してください[警告](../../preprocessor/warning.md)プラグマの警告を無効にする方法についてはします。  
  
## <a name="example"></a>例  
 次の例では、C4803 を生成します。  
  
```  
// C4803.cpp  
// compile with: /clr /W1  
using namespace System;  
  
public delegate void Del();  
  
ref struct E {  
   Del ^ _pd1;  
   event Del ^ E1 {  
      void add (Del ^ pd1) {  
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));  
      }  
  
      void remove(Del^ pd1) {  
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));  
      }  
  
      virtual void raise() {   // C4803 warning (remove virtual)  
         if (_pd1)  
            _pd1();  
      }  
   }  
  
   void func() {  
      Console::WriteLine("In E::func()");  
   }  
};  
  
int main() {  
   E ^ ep = gcnew E;  
   ep->E1 += gcnew Del(ep, &E::func);  
   ep->E1();  
   ep->E1 -= gcnew Del(ep, &E::func);  
   ep->E1();  
}  
```  
