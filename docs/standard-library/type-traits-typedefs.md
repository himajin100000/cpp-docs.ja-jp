---
title: '&lt;type_traits&gt; typedef | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::false_type
- xtr1common/std::false_type
- type_traits/std::true_type
- xtr1common/std::true_type
dev_langs:
- C++
ms.assetid: 8ac040ca-ed2d-4570-adc9-cb5626530053
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 2c66e7420a06c7af41b42ceb6f3b8c91c4aaa4eb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="lttypetraitsgt-typedefs"></a>&lt;type_traits&gt; typedef
|||  
|-|-|  
|[false_type](#false_type)|[true_type](#true_type)|  
  
##  <a name="false_type"></a>  false_type Typedef  
 false 値を持つ整数定数を保持します。  
  
```  
typedef integral_constant<bool, false> false_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート `integral_constant` から特化したテンプレートのシノニムです。  
  
### <a name="example"></a>例  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main() {   
    std::cout << "false_type == " << std::boolalpha   
        << std::false_type::value << std::endl;   
    std::cout << "true_type == " << std::boolalpha   
        << std::true_type::value << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
false_type == false  
true_type == true  
```  
  
##  <a name="true_type"></a>  true_type Typedef  
 true 値を持つ整数定数を保持します。  
  
```  
typedef integral_constant<bool, true> true_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート `integral_constant` から特化したテンプレートのシノニムです。  
  
### <a name="example"></a>例  
  
```cpp  
// std__type_traits__true_type.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main() {   
    std::cout << "false_type == " << std::boolalpha   
        << std::false_type::value << std::endl;   
    std::cout << "true_type == " << std::boolalpha   
        << std::true_type::value << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
false_type == false  
true_type == true  
```  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)

