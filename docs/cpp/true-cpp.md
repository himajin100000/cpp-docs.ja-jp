---
title: true (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- true_cpp
dev_langs:
- C++
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 453857447c9bf0b07cd40d9158d7e2ed0ba0121f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="true-c"></a>true (C++)
## <a name="syntax"></a>構文  
  
```  
  
      bool-identifier = true ;  
bool-expression logical-operator true ;  
```  
  
## <a name="remarks"></a>コメント  
 このキーワードは、型の変数の 2 つの値のいずれかの[bool](../cpp/bool-cpp.md)または (条件式は true ブール式では今すぐ) 条件式。 場合`i`の種類は`bool`、then ステートメント`i = true;`割り当てます**true**に`i`です。  
  
## <a name="example"></a>例  
  
```  
// bool_true.cpp  
#include <stdio.h>  
int main()  
{  
    bool bb = true;  
    printf_s("%d\n", bb);  
    bb = false;  
    printf_s("%d\n", bb);  
}  
```  
  
```Output  
1  
0  
```  
  
## <a name="see-also"></a>参照  
 [キーワード](../cpp/keywords-cpp.md)