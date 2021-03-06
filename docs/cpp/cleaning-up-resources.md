---
title: "リソースのクリーンアップ |Microsoft ドキュメント"
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
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fd84fdd041a3b3715c4fbfa9b4c1d78fdf2ba464
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cleaning-up-resources"></a>リソースの後処理
終了ハンドラーの実行中は、終了ハンドラーが呼び出される前に実際に割り当てられたリソースがわからない場合があります。 すべてのリソースが割り当てられる前に `__try` ステートメント ブロックへの割り込みが発生したために、一部のリソースは開いていない可能性もあります。  
  
 したがって、安全のために、終了処理のクリーンアップに進む前に、どのリソースが実際に開いているかをチェックする必要があります。 推奨される手順は、次のとおりです。  
  
1.  各ハンドルを NULL に初期化します。  
  
2.  `__try` ステートメント ブロックで、各リソースを割り当てます。 各ハンドルは、リソースが割り当てられると、正の値に設定されます。  
  
3.  `__finally` ステートメント ブロックでは、対応するハンドルまたはフラグ変数がゼロ以外であるか、NULL でない、各リソースを解放します。  
  
## <a name="example"></a>例  
 たとえば、次のコードでは、終了ハンドラーを使用して、`__try` ステートメント ブロックで割り当てられた 3 つのファイルとメモリ ブロックを閉じています。 コードでは、リソースをクリーンアップする前に、まずリソースが割り当てられているかどうかを確認しています。  
  
```  
// exceptions_Cleaning_up_Resources.cpp  
#include <stdlib.h>  
#include <malloc.h>  
#include <stdio.h>  
#include <windows.h>  
  
void fileOps() {  
   FILE  *fp1 = NULL,  
         *fp2 = NULL,  
         *fp3 = NULL;  
   LPVOID lpvoid = NULL;  
   errno_t err;  
  
   __try {  
      lpvoid = malloc( BUFSIZ );  
  
      err = fopen_s(&fp1, "ADDRESS.DAT", "w+" );  
      err = fopen_s(&fp2, "NAMES.DAT", "w+" );  
      err = fopen_s(&fp3, "CARS.DAT", "w+" );  
   }  
   __finally {  
      if ( fp1 )  
         fclose( fp1 );  
      if ( fp2 )  
         fclose( fp2 );  
      if ( fp3 )  
         fclose( fp3 );  
      if ( lpvoid )  
         free( lpvoid );  
   }  
}  
  
int main() {  
   fileOps();  
}  
```  
  
## <a name="see-also"></a>参照  
 [終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)   
 [構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)