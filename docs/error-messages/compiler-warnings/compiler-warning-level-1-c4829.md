---
title: "コンパイラの警告 (レベル 1) C4829 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4829
dev_langs:
- C++
helpviewer_keywords:
- C4829
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d662aaf24526320c0ced706534099d4c94a3c9f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4829"></a>コンパイラの警告 (レベル 1) C4829
関数 main への正しくないパラメーターである可能性があります。 検討 ' intmain (platform::array\<platform::string ^ > ^ argv)'  
  
 main などの特定の関数は、参照型パラメーターを受け取れません。 コンパイルは成功しても、結果のイメージは実行できない場合があります。  
  
 次の例では C4829 が生成されます。  
  
```  
// C4829.cpp  
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp  
int main(Platform::String ^ s) {}   // C4829  
  
```