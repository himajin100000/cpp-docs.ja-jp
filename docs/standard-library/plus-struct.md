---
title: "plus 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xfunctional/std::plus
dev_langs:
- C++
helpviewer_keywords:
- plus class
- plus struct
ms.assetid: 4594abd5-b2f2-4fac-9b6b-fc9a2723f8cf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e40ad97ac315e368d05b62424da2f094da4beaf5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="plus-struct"></a>plus 構造体
引数に対して加算演算 (二項 `operator+`) を実行する定義済みの関数オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```
template <class Type = void>
struct plus : public binary_function <Type, Type, Type>  
{
    Type operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator+
template <>  
struct plus<void>  
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) + std::forward<U>(Right));
 };
```  
  
#### <a name="parameters"></a>パラメーター  
 `Type`、`T`、`U`  
 指定または推論された型のオペランドを受け取る二項 `operator+` をサポートする型。  
  
 `Left`  
 加算演算の左オペランド。 特殊化されていないテンプレートでは、`Type` 型の左辺値参照引数を使用します。 特殊化されたテンプレートは、推論された型 `T` の左辺値および右辺値参照引数の完全転送を行います。  
  
 `Right`  
 加算演算の右オペランド。 特殊化されていないテンプレートでは、`Type` 型の左辺値参照引数を使用します。 特殊化されたテンプレートは、推論された型 `U` の左辺値および右辺値参照引数の完全転送を行います。  
  
## <a name="return-value"></a>戻り値  
 `Left + Right` の結果。 特殊化されたテンプレートは、結果の完全転送を行います。結果には二項 `operator+` によって返された型が含まれます。  
  
## <a name="example"></a>例  
  
```cpp  
// functional_plus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   vector <double> v1, v2, v3 ( 6 );  
   vector <double>::iterator Iter1, Iter2, Iter3;  
  
   int i;  
   for ( i = 0 ; i <= 5 ; i++ )  
      v1.push_back( 4 * i );  
  
   int j;  
   for ( j = 0 ; j <= 5 ; j++ )  
      v2.push_back( -2.0 * j - 4 );  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "The vector v2 = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
  
   // Finding the element-wise sums of the elements of v1 & v2  
   transform (v1.begin( ), v1.end( ), v2.begin( ), v3.begin ( ), plus<double>( ) );  
  
   cout << "The element-wise sums are: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
\* Output:   
The vector v1 = ( 0 4 8 12 16 20 )  
The vector v2 = ( -4 -6 -8 -10 -12 -14 )  
The element-wise sums are: ( -4 -2 0 2 4 6 )  
*\  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<functional>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



