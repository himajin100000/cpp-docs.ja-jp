---
title: "コンパイラの警告 (レベル 4) C4210 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4210
dev_langs:
- C++
helpviewer_keywords:
- C4210
ms.assetid: f8600adf-dfe2-4022-a37a-3d4997641dfd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f4c75203bdd821612a7cd289e52702e606c41344
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4210"></a>コンパイラの警告 (レベル 4) C4210
使用される標準の拡張機能: ファイル スコープを指定された関数  
  
 既定の Microsoft 拡張機能 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md))、関数宣言は、ファイル スコープを持ちます。  
  
```  
// C4210.c  
// compile with: /W4 /c  
void func1()  
{  
   extern int func2( double );   // C4210 expected  
}  
  
int main()  
{  
   func2( 4 );   //  /Ze passes 4 as type double  
}                //  /Za passes 4 as type int  
```  
  
 この拡張機能によっては、他のコンパイラに移植できないコードができなくなります。