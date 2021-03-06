---
title: "定義と宣言 (C++) |Microsoft ドキュメント"
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
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7391180ca83d40e6ec00688054223b2e9af48e4f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="definitions-and-declarations-c"></a>定義と宣言 (C++)
## <a name="microsoft-specific"></a>Microsoft 固有の仕様
 DLL インターフェイスは、システムの一部のプログラムによってエクスポートされることがわかっているすべての項目 (関数とデータ) を参照します。つまり、すべての項目として宣言されている`dllimport`または`dllexport`です。 DLL インターフェイスに含まれるすべての宣言は、いずれかを指定する必要があります、`dllimport`または`dllexport`属性。 ただし、定義では、`dllexport` 属性のみを指定する必要があります。 たとえば、次の関数定義はコンパイラ エラーになります。

```
__declspec( dllimport ) int func() {   // Error; dllimport
                                       // prohibited on definition.
   return 1;  
}
```

 次のコードでも、エラーが生成します。

```
__declspec( dllimport ) int i = 10;  // Error; this is a definition.
```

 ただし、次に示す構文は、正しい構文です。

```
__declspec( dllexport ) int i = 10;  // Okay--export definition
```

 使用`dllexport`は定義を意味中`dllimport`は宣言を意味します。 宣言を強制するには、`extern` と共に `dllexport` キーワードを使用する必要があります。このようにしない場合、暗黙の定義になります。 そのため、次の例は正しいコードになります。

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

extern DllExport int k; // These are both correct and imply a
DllImport int j;        // declaration.
```

 次の例に、上記の例をさらに明確に示します。

```
static __declspec( dllimport ) int l; // Error; not declared extern.

void func() {
    static __declspec( dllimport ) int s;  // Error; not declared
                                           // extern.
    __declspec( dllimport ) int m;         // Okay; this is a
                                           // declaration.
    __declspec( dllexport ) int n;         // Error; implies external
                                           // definition in local scope.
    extern __declspec( dllimport ) int i;  // Okay; this is a
                                           // declaration.
    extern __declspec( dllexport ) int k;  // Okay; extern implies
                                           // declaration.
    __declspec( dllexport ) int x = 5;     // Error; implies external
                                           // definition in local scope.
}
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照
 [dllexport、dllimport](../cpp/dllexport-dllimport.md)
