---
title: "コンパイラの警告 (レベル 4) C4131 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4131
dev_langs:
- C++
helpviewer_keywords:
- C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea37a3f210a2c379471b481fb0812b6c0630d32a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4131"></a>コンパイラの警告 (レベル 4) C4131
'function': 旧スタイルの宣言が使われています  
  
 指定された関数の宣言は、プロトタイプ形式ではありません。  
  
 旧スタイルの関数の宣言をプロトタイプ形式に変換する必要があります。  
  
 旧スタイルの関数の宣言の例を次に示します。  
  
```  
// C4131.c  
// compile with: /W4 /c  
void addrec( name, id ) // C4131 expected  
char *name;  
int id;  
{ }  
```  
  
 プロトタイプ形式の例を次に示します。  
  
```  
void addrec( char *name, int id )  
{ }  
```