---
title: "コンパイラ エラー C3038 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3038
dev_langs:
- C++
helpviewer_keywords:
- C3038
ms.assetid: 140ada3e-5636-43ef-a4ee-22a9f66a771f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 61cb06c7ebeff6dd24cdcd82026d09b5fd5d9a33
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3038"></a>コンパイラ エラー C3038
'var': 'private' 句の変数を、それを囲むコンテキスト内で減少変数にすることはできません  
  
 parallel ディレクティブの [reduction](../../parallel/openmp/reference/reduction.md) 句に出現する変数を、parallel コンストラクトにバインドされる動作共有ディレクティブの [private](../../parallel/openmp/reference/private-openmp.md) 句に指定することはできません。  
  
 次の例では C3038 が生成されます。  
  
```  
// C3038.cpp  
// compile with: /openmp /c  
int g_i, g_i2;  
  
int main() {  
   int i;  
  
   #pragma omp parallel reduction(+: g_i)  
   {  
      #pragma omp for private(g_i)   // C3038  
      // try the following line instead  
      // #pragma omp for private(g_i2)  
      for (i = 0; i < 10; ++i)  
         g_i += i;  
   }  
}  
```