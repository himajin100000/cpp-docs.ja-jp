---
title: "remove_volatile クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::remove_volatile
dev_langs:
- C++
helpviewer_keywords:
- remove_volatile class
- remove_volatile
ms.assetid: 8b87e2c2-a581-4eb3-8691-c5603910d61d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c0dd0e7276cb680f1ebf70771dc4deb9109c272
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="removevolatile-class"></a>remove_volatile クラス
型から非 volatile 型を作成します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class T>  
struct remove_volatile;  
 
template <class T>  
using remove_volatile_t = typename remove_volatile<T>::type;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 変更する型。  
  
## <a name="remarks"></a>コメント  
 `remove_volatile<T>` のインスタンスは、`T1` の形式が `T` である場合は、修飾型 `volatile T1` を保持します。それ以外の場合は、`T` を保持します。  
  
## <a name="example"></a>例  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_volatile_t<volatile int> *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << " remove_volatile_t<volatile int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
```  
  
```Output  
remove_volatile_t<volatile int> == int  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)   
 [add_volatile クラス](../standard-library/add-volatile-class.md)
