---
title: "コンパイラの警告 (レベル 1) C4436 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1018d678b6105f2d727f7806326218c168d8f728
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4436"></a>コンパイラの警告 (レベル 1) C4436
仮想ベース 'class1' から 'class2' コンス トラクターまたはデストラクターでへの dynamic_cast でした/vd2 を部分的に構築されるオブジェクト コンパイルに失敗または #pragma vtordisp(2) と ' class2' を有効に定義します。  
  
 コンパイラが発生しました、`dynamic_cast`次の特性を持つ操作します。  
  
-   キャストは、基底クラスへのポインターから派生クラスへのポインターです。  
  
-   派生クラスは、事実上、基本クラスを継承します。  
  
-   派生クラスがない、`vtordisp`仮想ベースのフィールドです。  
  
-   コンス トラクターまたは、派生クラスのデストラクターで、キャストがあるまたはをさらにいくつかのクラスが派生クラスから継承します。  
  
 警告を示します、`dynamic_cast`部分的に構築されるオブジェクトで動作している場合は正しくを実行可能性があります。  さらに派生オブジェクトの下位のオブジェクトで動作している派生コンス トラクターとデストラクターを発生します。  警告でという名前の派生クラスがさらにされていない場合、派生した、警告は無視できます。  
  
## <a name="example"></a>例  
 次の例は、C4436 を生成し、欠落しているから発生するコードの生成の問題を示しています`vtordisp`フィールドです。  
  
```cpp  
// C4436.cpp  
// To see the warning and runtime assert, compile with: /W1  
// To eliminate the warning and assert, compile with: /W1 /vd2  
//       or compile with: /W1 /DFIX  
#include <cassert>  
  
struct A  
{  
public:  
    virtual ~A() {}  
};  
  
#if defined(FIX)  
#pragma vtordisp(push, 2)  
#endif  
struct B : virtual A  
{  
    B()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4436  
        assert(this == b);              // assert unless compiled with /vd2  
    }  
};  
#if defined(FIX)  
#pragma vtordisp(pop)  
#endif  
  
struct C : B  
{  
    int i;  
};  
  
int main()  
{  
    C c;  
}  
```  
  
## <a name="see-also"></a>参照  
 [dynamic_cast 演算子](../../cpp/dynamic-cast-operator.md)   
 [vtordisp](../../preprocessor/vtordisp.md)   
 [コンパイラの警告 (レベル 4) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)