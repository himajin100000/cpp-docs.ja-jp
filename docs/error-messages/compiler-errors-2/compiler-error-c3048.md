---
title: "コンパイラ エラー C3048 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3048
dev_langs:
- C++
helpviewer_keywords:
- C3048
ms.assetid: 48e07091-94d9-471d-befe-7e2507631edd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bf0fb42659248012d9f1a90b7ca112ef96d69b9a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3048"></a>コンパイラ エラー C3048
'#pragma omp atomic' の後の式は、正しくない形式を含んでいます  
  
 atomic ディレクティブが正しく指定されていません。  
  
 次の例では C3048 が生成されます。  
  
```  
// C3048.cpp  
// compile with: /openmp vcomps.lib  
#include "omp.h"  
#include <stdio.h>  
  
int main() {  
   int a[10];  
   omp_set_num_threads(4);  
   #pragma omp parallel  
   {  
      #pragma omp atomic  
      a[0] = 1;   // C3048  
      // try the following line instead  
      // a[0] += 1;  
   }  
}  
```