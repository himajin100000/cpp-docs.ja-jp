---
title: vector&lt;bool&gt;::reference::flip | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vector/std::vector<bool>::reference::flip
dev_langs:
- C++
helpviewer_keywords:
- reference::flip method
ms.assetid: ef940365-cbe4-4a87-a3e2-1f3cfa357e29
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d8e91ad188852e12a687e1ad9454fb16675cf3d5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="vectorltboolgtreferenceflip"></a>vector&lt;bool&gt;::reference::flip
参照先の [vector\<bool>](../standard-library/vector-bool-class.md) 要素のブール値を反転します。  
  
## <a name="syntax"></a>構文  
  
```  
void flip();
```  
  
## <a name="example"></a>例  
  
```cpp  
// vector_bool_ref_flip.cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    cout << boolalpha;  
  
    vector<bool> vb = { true, false, false, true, true };  
  
    cout << "The vector is: " << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
  
    vector<bool>::reference vbref = vb.front();  
    vbref.flip();  
  
    cout << "The vector with first element flipped is: " << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
}  
  
```  
  
## <a name="output"></a>出力  
  
```  
The vector is:  
    true false false true true  
The vector with first element flipped is:  
    false false false true true  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<vector>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [vector\<bool>::reference クラス](../standard-library/vector-bool-reference-class.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)

