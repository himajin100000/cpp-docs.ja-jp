---
title: "COLUMN_ENTRY_TYPE_SIZE |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_TYPE_SIZE
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_ENTRY_TYPE_SIZE macro
ms.assetid: d8b169e8-af22-464b-8cb3-eaa346f7a739
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cec18aa88ea5d34589e69e41b4a08136d6edf525
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="columnentrytypesize"></a>COLUMN_ENTRY_TYPE_SIZE
データベースの特定の列へのバインドを表します。 サポート`type`と`size`パラメーター。  
  
## <a name="syntax"></a>構文  
  
```cpp
COLUMN_ENTRY_TYPE_SIZE(nOrdinal, wType, nLength, data)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nOrdinal`  
 [in]列番号。  
  
 `wType`  
 [in]列のエントリのデータ型。  
  
 `nLength`  
 [in](バイト単位) の列のエントリのサイズです。  
  
 `data`  
 [in]ユーザー レコードに対応するデータ メンバーです。  
  
## <a name="remarks"></a>コメント  
 このマクロは、の特殊なバリアント、 [COLUMN_ENTRY](../../data/oledb/column-entry.md)マクロをデータのサイズと種類を指定する手段を提供します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)