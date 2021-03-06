---
title: "add_volatile クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::add_volatile
dev_langs:
- C++
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0425a4b9832b21b0b77c1f2098e9b9d359da7b91
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="addvolatile-class"></a>add_volatile クラス
指定した型から volatile 型を作成します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Ty>  
struct add_volatile;  
 
template <class T>
using add_volatile_t = typename add_volatile<T>::type;  
```  
  
### <a name="parameters"></a>パラメーター  
*T*  
変更する型。  
  
## <a name="remarks"></a>コメント  
`add_volatile<T>` のインスタンスには、*T* が参照、関数、または volatile で修飾された型の場合は *T*、それ以外の場合は `volatile` *T* のメンバー typedef `type` があります。別名 `add_volatile_t` は、メンバー typedef `type` にアクセスするショートカットです。 
  
## <a name="example"></a>例  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_volatile_t<int> *p = (volatile int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_volatile<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
} 
```  
  
```Output  
add_volatile<int> == int  
```  
  
## <a name="requirements"></a>必要条件  

**ヘッダー:** \<type_traits>  
  
**名前空間:** std  
  
## <a name="see-also"></a>参照  
[<type_traits>](../standard-library/type-traits.md)   
[remove_volatile クラス](../standard-library/remove-volatile-class.md)
