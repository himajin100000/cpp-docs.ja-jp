---
title: "コンパイラ エラー C3364 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3364
dev_langs:
- C++
helpviewer_keywords:
- C3364
ms.assetid: 98654741-60fe-4472-a6af-e580f8c0a6e1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cdf9f9a6d4ae6584ff3b30e71a0c74b0ca777afe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3364"></a>コンパイラ エラー C3364
'delegate': delegate コンス トラクター: 引数がマネージ クラスのメンバー関数またはグローバル関数へのポインターにする必要があります  
  
 デリゲートのコンス トラクターの 2 番目のパラメーターは、メンバー関数のアドレスまたは任意のクラスの静的メンバー関数のアドレスのいずれかを取得します。 両方の単純なアドレスとして扱われます。  
  
 次の例では、C3364 が生成されます。  
  
```  
// C3364_2.cpp  
// compile with: /clr  
  
delegate int D( int, int );  
  
ref class C {  
public:  
   int mf( int, int ) {  
      return 1;  
   }  
};  
  
int main() {  
   C^ pC = gcnew C;  
   System::Delegate^ pD = gcnew D( pC,pC->mf( 1, 2 ) ); // C3364  
  
   // try the following line instead  
   // System::Delegate^ pD = gcnew D(pC, &C::mf);  
}  
```  
