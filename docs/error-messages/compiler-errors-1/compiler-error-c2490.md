---
title: "コンパイラ エラー C2490 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2490
dev_langs:
- C++
helpviewer_keywords:
- C2490
ms.assetid: 9de6bddd-b2e2-4ce6-b33b-201a8c2c8c54
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d23f61e8e720e1d59ae258132e368505c44bbb13
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2490"></a>コンパイラ エラー C2490
' keyword' は 'naked' 属性を持つ関数では使用できません。  
  
 として定義されている関数[naked](../../cpp/naked-cpp.md)構造化例外処理を使用することはできません。  
  
 次の例では、C2490 が生成されます。  
  
```  
// C2490.cpp  
// processor: x86  
__declspec( naked ) int func() {  
   __try{}   // C2490, structured exception handling  
}  
```