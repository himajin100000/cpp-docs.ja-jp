---
title: コンパイラ エラー C3483 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- C3483
dev_langs:
- C++
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e2ea5c703e9617bd419a3e390f143c0defd7ca9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3483"></a>コンパイラ エラー C3483
'var' は既にラムダ キャプチャ リストに含まれています  
  
 ラムダ式のキャプチャ リストに同じ変数を複数回渡しました。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   キャプチャ リストから変数のすべての追加インスタンスを削除します。  
  
## <a name="example"></a>例  
 次の例では、変数 `n` がラムダ式のキャプチャ リストに複数回出現するため、C3483 が生成されます。  
  
```  
// C3483.cpp  
  
int main()  
{  
   int m = 6, n = 5;  
   [m,n,n] { return n + m; }(); // C3483  
}  
```  
  
## <a name="see-also"></a>参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)