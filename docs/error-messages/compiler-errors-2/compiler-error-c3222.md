---
title: "コンパイラ エラー C3222 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3222
dev_langs:
- C++
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0028b9540127433bdbd17b01f1a5a3dfd9361558
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3222"></a>コンパイラ エラー C3222
'parameter': ジェネリック関数またはマネージあるいは WinRT 型のメンバー関数に対して、既定引数を宣言できません  
  
既定の引数を持つメソッド パラメーターを宣言することは許可されていません。 メソッドのオーバーロードは、この問題を回避する方法の 1 つです。 つまり、同じ名前でパラメーターを持たないメソッドを定義し、メソッド本体で変数を初期化します。  
  
次の例では C3222 が生成されます。  
  
```  
// C3222_2.cpp  
// compile with: /clr  
public ref class G {  
   void f( int n = 0 );   // C3222  
};  
```  
