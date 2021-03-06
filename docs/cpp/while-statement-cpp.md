---
title: "while ステートメント (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- while_cpp
dev_langs:
- C++
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e93d31457beb3c1546b55d303fd71566176a9367
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="while-statement-c"></a>while ステートメント (C++)
実行*ステートメント*まで繰り返し*式*0 に評価します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      while ( expression )  
   statement  
```  
  
## <a name="remarks"></a>コメント  
 テスト*式*ループの各実行する前に処理を行うのため、`while`ループは、0 回以上を実行します。 *式*の整数型、ポインター型、または、整数への明確な変換を持つクラス型またはポインター型である必要があります。  
  
 A`while`ループは終了時にも、 [break](../cpp/break-statement-cpp.md)、 [goto](../cpp/goto-statement-cpp.md)、または[返す](../cpp/return-statement-cpp.md)本体の実行ステートメント内で。 使用して[続行](../cpp/continue-statement-cpp.md)を終了せず、現在のイテレーションを終了する、`while`ループします。 **続行**の次のイテレーションに制御を渡します、`while`ループします。  
  
 次のコードは、文字列の末尾のアンダースコアをトリミングするために `while` ループを使用します。  
  
```  
// while_statement.cpp  
  
#include <string.h>  
#include <stdio.h>  
char *trim( char *szSource )  
{  
    char *pszEOS = 0;  
  
    //  Set pointer to character before terminating NULL  
    pszEOS = szSource + strlen( szSource ) - 1;  
  
    //  iterate backwards until non '_' is found   
    while( (pszEOS >= szSource) && (*pszEOS == '_') )  
        *pszEOS-- = '\0';  
  
    return szSource;  
}  
int main()  
{  
    char szbuf[] = "12345_____";  
  
    printf_s("\nBefore trim: %s", szbuf);  
    printf_s("\nAfter trim: %s\n", trim(szbuf));  
}  
```  
  
 終了条件はループの先頭で評価されます。 末尾のアンダースコアがない場合、ループは実行されません。  
  
## <a name="see-also"></a>参照  
 [繰り返しステートメント](../cpp/iteration-statements-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [do-while ステートメント (C++)](../cpp/do-while-statement-cpp.md)   
 [for ステートメント (C++)](../cpp/for-statement-cpp.md)   
 [範囲ベースの for ステートメント (C++)](../cpp/range-based-for-statement-cpp.md)