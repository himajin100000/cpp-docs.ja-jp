---
title: "コンパイラの警告 (レベル 2) C4099 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4099
dev_langs:
- C++
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1eb64e859ef40397edeb872cc7f6f228f7ae89e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4099"></a>コンパイラの警告 (レベル 2) C4099
'identifier': 'objecttype1' 使われて '%objecttype2' を使用して 1 つ目の種類名  
  
 クラスと構造体として宣言されたオブジェクトが定義されているまたは構造体としてをクラスとして宣言されたオブジェクトを定義します。 コンパイラは、定義で指定された型を使用します。  
  
## <a name="example"></a>例  
 次の例では、C4099 を生成します。  
  
```  
// C4099.cpp  
// compile with: /W2 /c  
struct A;  
class A {};   // C4099, use different identifer or use same object type  
```