---
title: "4.4 OMP_NESTED |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 50b2b110f191252702da9a2b6eed99baa40b7814
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED
`OMP_NESTED`環境変数を有効または入れ子になった並列処理が有効になっている、または呼び出すことによって無効になっている場合を除き、入れ子になった並列処理を無効になります、 `o` **mp_set_nested**ライブラリ ルーチンです。 場合に設定**TRUE**、入れ子になった並列処理が有効である場合に設定されている**FALSE**、入れ子になった並列処理が無効になっています。 既定値は**FALSE**です。  
  
 例:  
  
```  
setenv OMP_NESTED TRUE  
```  
  
## <a name="cross-reference"></a>クロス リファレンス  
  
-   `omp_set_nested`関数を参照してください[セクション 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 ページのです。