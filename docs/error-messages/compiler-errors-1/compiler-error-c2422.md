---
title: "コンパイラ エラー C2422 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 852a495406a8baf147fc53262f8fe856fce726b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2422"></a>コンパイラ エラー C2422
'のオペランド' で誤ったセグメント オーバーライド  
  
 インライン アセンブラー コードで、オペランドに対してセグメント オーバーライド演算子 (:)  以下の原因が考えられます。  
  
-   演算子の直前のレジスタは、セグメント レジスタではありません。  
  
-   演算子の直前のレジスタは、オペランド内の唯一のセグメント レジスタではありません。  
  
-   間接演算子 (かっこ) 内のセグメント オーバーライド演算子が表示されます。  
  
-   セグメント オーバーライド演算子の後の式は、イミディ エイトのオペランドまたはメモリ オペランドではありません。  
  
 次の例では、C2422 が生成されます。  
  
```  
// C2422.cpp  
// processor: x86  
int main() {  
   _asm {  
      mov AX, [BX:ES]   // C2422  
      mov AX, ES   // OK  
   }  
}  
```