---
title: "コンパイラの警告 (レベル 1) C4185 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4185
dev_langs:
- C++
helpviewer_keywords:
- C4185
ms.assetid: 37e7063a-35b1-4e05-ae31-e811dced02b9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b2800ac3dab1e8cc13551f47a5162f975163c5fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4185"></a>コンパイラの警告 (レベル 1) C4185
不明な #import の属性 'attribute' を無視します  
  
 属性は、 `#import`の有効な属性ではありません。 これは無視されます。  
  
## <a name="example"></a>例  
  
```  
// C4185.cpp  
// compile with: /W1 /c  
#import "stdole2.tlb" no_such_attribute   // C4185  
```