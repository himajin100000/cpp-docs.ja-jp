---
title: "コンパイラ エラー C2703 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2703
dev_langs:
- C++
helpviewer_keywords:
- C2703
ms.assetid: 384295c3-643d-47ae-a9a6-865b3036aa84
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7b6f8dc12ecf0e89763998866bda0e58c855410
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2703"></a>コンパイラ エラー C2703
無効な _ _leave ステートメント  
  
 A`__leave`ステートメントは、内部になければなりません、`__try`ブロックします。  
  
 次の例では、C2703 が生成されます。  
  
```  
// C2703.cpp  
int main() {  
   __leave;   // C2703  
   __try {  
      // try the following line instead  
      __leave;  
   }  
   __finally {}  
}  
```