---
title: "omp_destroy_nest_lock |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_destroy_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_destroy_nest_lock OpenMP function
ms.assetid: 0ab1352b-668f-43dd-b441-31ec4cc53e68
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f7c62ba49f98581c233966dd8d7d71bb3433ae3f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ompdestroynestlock"></a>omp_destroy_nest_lock
入れ子にできるロックの初期化を解除します。  
  
## <a name="syntax"></a>構文  
  
```  
void omp_destroy_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `lock`  
 型の変数[omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md)で初期化された[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)です。  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [3.2.2 omp_destroy_lock 関数と omp_destroy_nest_lock 関数](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)です。  
  
## <a name="example"></a>例  
 参照してください[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)の使用例については`omp_destroy_nest_lock`します。  
  
## <a name="see-also"></a>参照  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)