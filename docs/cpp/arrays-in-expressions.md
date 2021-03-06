---
title: "式の配列 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29f6e16e665d8076ed5a1fe593e1bb9437f1406a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="arrays-in-expressions"></a>式の配列
配列型の識別子が表示される場合、式で以外の`sizeof`、アドレスの (**&**)、または初期化の参照、配列の最初の要素へのポインターに変換されます。 例:  
  
```  
char szError1[] = "Error: Disk drive not ready.";  
char *psz = szError1;  
```  
  
 ポインター `psz` は、配列 `szError1` の最初の要素をポイントします。 配列は、ポインターとは異なり、変更できる左辺値ではないことに注意してください。 したがって、次の割り当ては正しくありません。  
  
```  
szError1 = psz;  
```  
  
## <a name="see-also"></a>参照  
 [配列](../cpp/arrays-cpp.md)