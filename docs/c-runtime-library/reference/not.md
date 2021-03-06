---
title: not | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- std::not
- std.not
- Not
dev_langs:
- C++
helpviewer_keywords:
- not function
ms.assetid: d2ddbd5c-33c0-4aff-8961-feac155b4ba1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: da6e9bef4d969f22c5ce87fd9654e4f8401b4769
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="not"></a>not
! 演算子の 代替手段。  
  
## <a name="syntax"></a>構文  
  
```  
  
#define not !  
  
```  
  
## <a name="remarks"></a>コメント  
 マクロにより ! 演算子が生成されます。  
  
## <a name="example"></a>例  
  
```  
// iso646_not.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   int a = 0;  
  
   if (!a)  
      cout << "a is zero" << endl;  
  
   if (not(a))  
      cout << "a is zero" << endl;  
}  
```  
  
```Output  
a is zero  
a is zero  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<iso646.h>