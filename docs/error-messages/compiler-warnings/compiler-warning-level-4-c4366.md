---
title: "コンパイラの警告 (レベル 4) C4366 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4366
dev_langs:
- C++
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 221cc02e5a2592599bad0ee9a77de59b19dda6f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4366"></a>コンパイラの警告 (レベル 4) C4366
単項 'operator' 演算子の結果は固定でない可能性があります。  
  
 場合構造体のメンバーがこれまでできません固定梱包のため、コンパイラは警告ときに固定されたポインター、メンバーのアドレスが割り当てられています。 既定では、すべてのポインターを配置します。  
  
 C4366 を解決するには、構造体のアラインメントを変更するかでマウス ポインターを宣言、 [_ _unaligned](../../cpp/unaligned.md)キーワード。  
  
 詳細については、_ _unaligned を参照してください。 および[パック](../../preprocessor/pack.md)です。  
  
## <a name="example"></a>例  
 次の例では、C4366 を生成します。  
  
```  
// C4366.cpp  
// compile with: /W4 /c  
// processor: IPF x64  
#pragma pack(1)  
struct X {  
   short s1;  
   int s2;  
};  
  
int main() {  
   X x;  
   short * ps1 = &x.s1;   // OK  
   int * ps2 = &x.s2;   // C4366  
}  
```