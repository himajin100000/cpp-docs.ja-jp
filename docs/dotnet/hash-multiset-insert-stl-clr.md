---
title: "hash_multiset::insert (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::insert
dev_langs:
- C++
helpviewer_keywords:
- insert member [STL/CLR]
ms.assetid: e7254f30-a514-4ddc-bf53-38aafbe9e8eb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3e309fa84ad67b7148ae92d95fa083c24173b6c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultisetinsert-stlclr"></a>hash_multiset::insert (STL/CLR)
要素を追加します。  
  
## <a name="syntax"></a>構文  
  
```  
iterator insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 先頭  
 挿入する範囲の開始しています。  
  
 last  
 挿入する範囲の終了。  
  
 右  
 列挙型を挿入します。  
  
 val  
 挿入するキー値。  
  
 where  
 (ヒントのみ) を挿入するためのコンテナー内の場所。  
  
## <a name="remarks"></a>コメント  
 各メンバー関数は、残りのオペランドで指定されたシーケンスを挿入します。  
  
 最初のメンバー関数は、値を持つ要素を挿入します。 `val`、し、新しく挿入される要素を指定する反復子を返します。 使用する 1 つの要素を挿入します。  
  
 2 番目のメンバー関数は、値を持つ要素を挿入します。`val`を使用して、 `where` (パフォーマンスを向上させる) をヒントとしてし、新しく挿入される要素を指定する反復子を返します。 使用することがわかって要素に隣接する可能性のある 1 つの要素を挿入します。  
  
 3 番目のメンバー関数は、シーケンスを挿入します。 [`first`、 `last`)。 使用する別のシーケンスからコピーした 0 個以上の要素を挿入します。  
  
 4 番目のメンバー関数で指定されたシーケンスを挿入する、`right`です。 使用する列挙子によって説明されているシーケンスを挿入します。  
  
 各要素の挿入では、被制御シーケンス内の要素の数の対数に比例して時間がかかります。 挿入は、カーソル位置に隣接する要素を指定するヒントの指定、償却定数時間でただし、実行できます。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_multiset_insert.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    System::Console::WriteLine("insert(L'x') = {0}",   
        *c1.insert(L'x'));   
  
    System::Console::WriteLine("insert(L'b') = {0}",   
        *c1.insert(L'b'));   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    System::Console::WriteLine("insert(begin(), L'y') = {0}",   
        *c1.insert(c1.begin(), L'y'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Myhash_multiset c2;   
    Myhash_multiset::iterator it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Myhash_multiset c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(L'x') = x  
insert(L'b') = b  
 a b b c x  
insert(begin(), L'y') = y  
 a b b c x y  
 a b b c x  
 a b b c x y  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)