---
title: "Caccessorbase::gethaccessor |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
dev_langs:
- C++
helpviewer_keywords:
- GetHAccessor method
ms.assetid: 1bb98762-0752-4aae-a0b6-ba96bec03621
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 27bdf0058c2152f8797be54b28eeee7ac3e21135
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="caccessorbasegethaccessor"></a>CAccessorBase::GetHAccessor
指定されたアクセサーのアクセサー ハンドルを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      HACCESSOR GetHAccessor(ULONG nAccessor) const;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nAccessor`  
 [in]アクセサーのゼロ オフセットの数です。  
  
## <a name="return-value"></a>戻り値  
 アクセサーのハンドルです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CAccessorBase クラス](../../data/oledb/caccessorbase-class.md)