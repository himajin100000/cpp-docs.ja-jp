---
title: "input_iterator_tag 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xutility/std::input_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- input_iterator_tag class
- input_iterator_tag struct
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cd73fd177c43d8720bf341014a61930afcfc07c1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="inputiteratortag-struct"></a>input_iterator_tag 構造体
入力反復子を表す **iterator_category** 関数の戻り値の型を提供するクラス。  
  
## <a name="syntax"></a>構文  
  
struct input_iterator_tag {};  
  
## <a name="remarks"></a>コメント  
 カテゴリ タグ クラスはアルゴリズムの選択にコンパイル タグとして使用されます。 テンプレート関数は、コンパイル時に最も効率的なアルゴリズムを利用できるように、その反復子引数の最も具体的なカテゴリを見つける必要があります。 `Iterator` 型の反復子ごとに、反復子の動作を表す最も具体的なカテゴリ タグとして `iterator_traits`< `Iterator`> **::iterator_category** を定義する必要があります。  
  
 この型は、**Iter** が入力反復子としてサービスを提供するオブジェクトを表すとき、**iterator**\< **Iter**> **::iterator_category** と同じになります。  
  
## <a name="example"></a>例  
 **iterator_tag** の使用例については、「[iterator_traits](../standard-library/iterator-traits-struct.md)」または「[random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<iterator>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



