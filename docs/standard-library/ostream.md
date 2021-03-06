---
title: '&lt;ostream&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <ostream>
- ostream/std::<ostream>
- std::<ostream>
dev_langs:
- C++
helpviewer_keywords:
- ostream header
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ed7238f2c0716f3eaea01bec25ebf54cc24f340
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;
テンプレート クラス [basic_ostream](../standard-library/basic-ostream-class.md) を定義します。これは iostreams への挿入を仲介します。 ヘッダーは、関連する複数のマニピュレーターを定義します  (通常このヘッダーは、別の iostream ヘッダーに含まれています。 まれに、直接含めなければならないことがあります)。  
  
## <a name="syntax"></a>構文  
  
```  
#include <ostream>  
  
```  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[ostream](../standard-library/ostream-typedefs.md#ostream)|`char` に特殊化した `basic_ostream` と、`char` に特殊化した `char_traits` に基づいて型を作成します。|  
|[wostream](../standard-library/ostream-typedefs.md#wostream)|`wchar_t` に特殊化した `basic_ostream` と、`wchar_t` に特殊化した `char_traits` に基づいて型を作成します。|  
  
### <a name="manipulators"></a>マニピュレーター  
  
|||  
|-|-|  
|[endl](../standard-library/ostream-functions.md#endl)|行を終了し、バッファーをフラッシュします。|  
|[ends](../standard-library/ostream-functions.md#ends)|文字列を終了します。|  
|[flush](../standard-library/ostream-functions.md#flush)|バッファーをフラッシュします。|  
|[swap](../standard-library/ostream-functions.md#swap)|左側の `basic_ostream` オブジェクト パラメーターの値と右側の `basic_ostream` オブジェクト パラメーターの値を交換します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator<<](../standard-library/ostream-operators.md#op_lt_lt)|さまざまな型をストリームに書き込みます。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[basic_ostream](../standard-library/basic-ostream-class.md)|このテンプレート クラスは、要素とエンコードされたオブジェクトをストリーム バッファーに挿入する操作を制御するオブジェクトを記述します。|  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)



