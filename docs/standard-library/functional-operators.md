---
title: "&lt;functional&gt; 演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- functional/std::operator!=
- functional/std::operator==
dev_langs:
- C++
helpviewer_keywords:
- functional operators
ms.assetid: d4b3c760-f3e2-4b65-bdaa-d42e8dd6f5e1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf3e013ade27636b8cba3e2eeb5473440f9e14eb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ltfunctionalgt-operators"></a>&lt;functional&gt; 演算子
|||  
|-|-|  
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|  
  
##  <a name="op_eq_eq"></a>  operator==  
 呼び出し可能オブジェクトが空かどうかをテストします。  
  
```  
template <class Fty>  
bool operator==(const function<Fty>& f, null_ptr_type npc);

template <class Fty>  
bool operator==(null_ptr_type npc, const function<Fty>& f);
```  
  
### <a name="parameters"></a>パラメーター  
 `Fty`  
 ラップする関数の型。  
  
 `f`  
 関数オブジェクト  
  
 `npc`  
 null ポインター  
  
### <a name="remarks"></a>コメント  
 どちらの演算子も、`function` オブジェクトへの参照である引数と null ポインター定数である引数を受け取ります。 `function` オブジェクトが空の場合にのみ、両方とも true を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// std__functional__operator_eq.cpp
// compile with: /EHsc   
#include <functional>   
#include <iostream>   

int neg(int val)
{
    return (-val);
}

int main()
{
    std::function<int(int)> fn0;
    std::cout << std::boolalpha << "empty == "
        << (fn0 == 0) << std::endl;

    std::function<int(int)> fn1(neg);
    std::cout << std::boolalpha << "empty == "
        << (fn1 == 0) << std::endl;

    return (0);
}
  
```  
  
```Output  
empty == true  
empty == false  
```  
  
##  <a name="op_neq"></a>  operator!=  
 呼び出し可能オブジェクトが空かどうかをテストします。  
  
```  
template <class Fty>  
bool operator!=(const function<Fty>& f, null_ptr_type npc);

template <class Fty>  
bool operator!=(null_ptr_type npc, const function<Fty>& f);
```  
  
### <a name="parameters"></a>パラメーター  
 `Fty`  
 ラップする関数の型。  
  
 `f`  
 関数オブジェクト  
  
 `npc`  
 null ポインター  
  
### <a name="remarks"></a>コメント  
 どちらの演算子も、`function` オブジェクトへの参照である引数と null ポインター定数である引数を受け取ります。 `function` オブジェクトが空ではない場合にのみ、両方とも true を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// std__functional__operator_ne.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val)   
    {   
    return (-val);   
    }   
  
int main()   
    {   
    std::function<int (int)> fn0;   
    std::cout << std::boolalpha << "not empty == "   
        << (fn0 != 0) << std::endl;   
  
    std::function<int (int)> fn1(neg);   
    std::cout << std::boolalpha << "not empty == "   
        << (fn1 != 0) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
not empty == false  
not empty == true  
```  
  
## <a name="see-also"></a>参照  
 [\<functional>](../standard-library/functional.md)

