---
title: "CKeyColumns、CKeyColumnInfo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- m_szTableSchema
- m_szConstraintCatalog
- m_nColumnPropID
- ORDINAL_POSITION
- m_nOrdinalPosition
- COLUMN_GUID
- CKeyColumnInfo
- CONSTRAINT_NAME
- m_szColumnName
- m_szTableCatalog
- m_szConstraintSchema
- COLUMN_PROPID
- m_guidColumn
- CKeyColumns
- m_szTableName
- CONSTRAINT_CATALOG
- CONSTRAINT_SCHEMA
- m_szConstraintName
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_PROPID
- ORDINAL_POSITION
- m_szConstraintCatalog
- CONSTRAINT_CATALOG
- m_szTableSchema
- TABLE_CATALOG
- CKeyColumnInfo parameter class
- TABLE_NAME
- CONSTRAINT_NAME
- m_nOrdinalPosition
- m_nColumnPropID
- CONSTRAINT_SCHEMA
- TABLE_SCHEMA
- m_szColumnName
- COLUMN_NAME
- m_szTableCatalog
- m_szConstraintName
- CKeyColumns typedef class
- m_szTableName
- m_szConstraintSchema
- COLUMN_GUID
- m_guidColumn
ms.assetid: 40525a4f-a9cf-4e9f-886d-8a6ddd18a3d6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ab29aa12a38058611af3b593393e908cdc9a4ea5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ckeycolumns-ckeycolumninfo"></a>CKeyColumns、CKeyColumnInfo
Typedef クラスを呼び出す**CKeyColumns**そのパラメーター クラスを実装する**CKeyColumnInfo**です。  
  
## <a name="remarks"></a>コメント  
 参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)typedef クラスの使用に関する詳細についてはします。  
  
 このクラスは、カタログで定義されている制限されている列キーとして特定のユーザーを識別します。  
  
 次の表には、クラスのデータ メンバーとその対応する OLE DB 列が一覧表示します。 参照してください[KEY_COLUMN_USAGE 行セット](https://msdn.microsoft.com/en-us/library/ms712990.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマと列の詳細についてはします。  
  
|データ メンバー|OLE DB 列|  
|------------------|--------------------|  
|m_szConstraintCatalog|CONSTRAINT_CATALOG|  
|m_szConstraintSchema|CONSTRAINT_SCHEMA|  
|m_szConstraintName|CONSTRAINT_NAME|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szColumnName|COLUMN_NAME|  
|m_guidColumn|COLUMN_GUID|  
|m_nColumnPropID|COLUMN_PROPID|  
|m_nOrdinalPosition|ORDINAL_POSITION|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbsch.h  
  
## <a name="see-also"></a>参照  
 [CRestrictions クラス](../../data/oledb/crestrictions-class.md)