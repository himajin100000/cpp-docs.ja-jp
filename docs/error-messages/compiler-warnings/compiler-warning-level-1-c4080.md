---
title: "コンパイラの警告 (レベル 1) C4080 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4080
dev_langs:
- C++
helpviewer_keywords:
- C4080
ms.assetid: 964fb3f4-b9fd-450b-aa23-35cece126172
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7218b2ffff179cdf17231d010f600c5ed8eafde9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4080"></a>コンパイラの警告 (レベル 1) C4080
セグメント名の識別子が必要です。'symbol' が見つかりました。  
  
 [#pragma alloc_text](../../preprocessor/alloc-text.md) 内のセグメントの名前は、文字列または識別子である必要があります。 有効な識別子が見つからない場合、コンパイラはプラグマを無視します。  
  
 次の例では C4080 が生成されます。  
  
```  
// C4080.cpp  
// compile with: /W1  
extern "C" void func(void);  
  
#pragma alloc_text()   // C4080  
  
// try this line to resolve the warning  
// #pragma alloc_text("mysection", func)  
  
int main() {  
}  
  
void func(void) {  
}  
```