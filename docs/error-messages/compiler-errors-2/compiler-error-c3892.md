---
title: "コンパイラ エラー C3892 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3892
dev_langs:
- C++
helpviewer_keywords:
- C3892
ms.assetid: 83fff42c-ea48-442f-bc2e-b33a6b99d890
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76c09acf49d5099e3b8e8de0c14021b119c89199
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3892"></a>コンパイラ エラー C3892
'var': const である変数に割り当てることはできません  
  
 Const 変数は、宣言および初期化後に変更することはできません。  
  
 次の例では、C3892 が生成されます。  
  
```  
// C3892.cpp  
// compile with: /clr  
ref struct Y1 {  
   static const int staticConst = 9;  
};  
  
int main() {  
   Y1::staticConst = 0;   // C3892  
}  
```