---
title: "1 次元配列 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- brackets [ ]
- brackets [ ], arrays
- one-dimensional arrays
- arrays [C++], one-dimensional
- square brackets [ ]
- square brackets [ ], arrays
- subscript expressions
ms.assetid: e28536e5-3b77-46b5-97fd-9b938c771816
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 033d772a40ddf55474ca845c9c5708423bcf5e90
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2018
---
# <a name="one-dimensional-arrays"></a>1 次元配列
角かっこ (**[ ]**) が続く後置式は、配列オブジェクトの要素の添字表現です。 添字式は、次のように表現されると、*postfix-expression* を超える *expression* 位置にあるアドレスにある値を表します。  
  
```  
  
postfix-expression  
[  
expression  
]  
  
```  
  
 通常、*postfix-expression* によって表される値はポインター値 (配列 ID など) であり、*expression* は整数値です。 ただし、構文上必要なのは、一方の式がポインター型で、もう一方が整数型であることです。 したがって、*postfix-expression* の位置に整数値があり、*expression* の角かっこ内や添字の位置にポインター値がある可能性もあります。 たとえば、次のコードは有効です。  
  
```  
// one_dimensional_arrays.c  
int sum, *ptr, a[10];  
int main() {  
   ptr = a;  
   sum = 4[ptr];  
}  
```  
  
 添字式は、通常、配列要素を参照するために使用されますが、任意のポインターに添字を適用できます。 値の順序に関係なく、*expression* は角かっこ (**[ ]**) で囲む必要があります。  
  
 添字式は、ポインター値に整数値を追加し、結果に間接演算子 (**\***) を適用することによって評価されます (間接演算子については、「[間接演算子とアドレス演算子](../c-language/indirection-and-address-of-operators.md)」を参照してください)。実際には、1 次元配列では、次の 4 つの式は、`a` がポインターで `b` が整数である場合、等価です。  
  
```  
a[b]  
*(a + b)  
*(b + a)  
b[a]  
```  
  
 加算演算子の変換規則 (「[加法演算子](../c-language/c-additive-operators.md)」で指定) に従って、ポインターによってアドレス指定される型の長さを掛けることで、整数値がアドレス オフセットに変換されます。  
  
 たとえば `line` 識別子が `int` 値の配列を参照しているとします。 次の手順は、添字式 `line[ i ]` の評価に使用されます。  
  
1.  整数値 `i` は `int` 項目の長さとして定義されたバイト数によって乗算されます。 `i` の変換後の値は、`i` `int` の位置を表します。  
  
2.  この変換された値が元のポインター値 (`line`) に追加され、`line` からのオフセットが `i` `int` の位置であるアドレスが生成されます。  
  
3.  間接演算子は新しいアドレスに適用されます。 結果は、その部分での配列要素の値です (直感的な `line [ i ]`)。  
  
 `line[0]` によって表されるアドレスからのオフセットが 0 であるため、添字式 `line` は、行の最初の要素の値を表します。 同様に、`line[5]` のような式は、行から 5 位置オフセットされた要素、つまり配列の 6 番目の要素を参照します。  
  
## <a name="see-also"></a>関連項目  
 [添字演算子:](../cpp/subscript-operator.md)