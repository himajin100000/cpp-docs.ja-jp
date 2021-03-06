---
title: "重要な |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Critical
dev_langs:
- C++
helpviewer_keywords:
- critical OpenMP directive
ms.assetid: 2ab87d6d-5ca4-43ae-9f0a-1f517a6a2bab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ef2ce946fed85fbedce2a1ad0401ad0a36aab783
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="critical"></a>critical
されたコードが、一度に 1 つのスレッドで実行するのみを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp critical [(name)]  
{  
   code_block  
}  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 (`name`) (省略可能)  
 クリティカルなコードを識別する名前。 その名前は、かっこで囲む必要がありますに注意してください。  
  
## <a name="remarks"></a>コメント  
 **重大**ディレクティブに OpenMP 句がサポートされていません。  
  
 詳細については、次を参照してください。 [2.6.2 重要な構築](../../../parallel/openmp/2-6-2-critical-construct.md)です。  
  
## <a name="example"></a>例  
  
```  
// omp_critical.cpp  
// compile with: /openmp   
#include <omp.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
#define SIZE 10  
  
int main()   
{  
    int i;  
    int max;  
    int a[SIZE];  
  
    for (i = 0; i < SIZE; i++)   
    {  
        a[i] = rand();  
        printf_s("%d\n", a[i]);  
    }  
  
    max = a[0];  
    #pragma omp parallel for num_threads(4)  
        for (i = 1; i < SIZE; i++)   
        {  
            if (a[i] > max)  
            {  
                #pragma omp critical  
                {  
                    // compare a[i] and max again because max   
                    // could have been changed by another thread after   
                    // the comparison outside the critical section  
                    if (a[i] > max)  
                        max = a[i];  
                }  
            }  
        }  
  
    printf_s("max = %d\n", max);  
}  
```  
  
```Output  
41  
18467  
6334  
26500  
19169  
15724  
11478  
29358  
26962  
24464  
max = 29358  
```  
  
## <a name="see-also"></a>参照  
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)