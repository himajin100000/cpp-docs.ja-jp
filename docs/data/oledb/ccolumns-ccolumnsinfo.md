---
title: "CColumns、CColumnsInfo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- m_szDomainSchema
- CColumns
- m_guidType
- COLLATION_CATALOG
- m_szTableSchema
- COLUMN_DEFAULT
- IS_NULLABLE
- m_nColumnPropID
- ORDINAL_POSITION
- m_szColumnDefault
- m_szCollationCatalog
- m_nDateTimePrecision
- m_szDomainCatalog
- m_nOrdinalPosition
- m_szDomainName
- COLUMN_GUID
- CHARACTER_SET_NAME
- m_nColumnFlags
- DOMAIN_NAME
- m_szCollationName
- m_szColumnName
- CHARACTER_SET_SCHEMA
- COLUMN_FLAGS
- m_szCharSetName
- NUMERIC_PRECISION
- DOMAIN_SCHEMA
- DOMAIN_CATALOG
- m_nDataType
- m_szTableCatalog
- CHARACTER_SET_CATALOG
- m_szCharSetSchema
- CHARACTER_OCTET_LENGTH
- NUMERIC_SCALE
- m_nNumericScale
- COLUMN_PROPID
- m_guidColumn
- m_szCharSetCatalog
- m_nMaxLength
- CHARACTER_MAXIMUM_LENGTH
- COLLATION_NAME
- COLLATION_SCHEMA
- m_bColumnHasDefault
- m_szTableName
- m_nNumericPrecision
- DATA_TYPE
- m_nOctetLength
- CColumnsInfo
- m_szCollationSchema
- m_bIsNullable
- COLUMN_HASDEFAULT
- DATETIME_PRECISION
dev_langs:
- C++
helpviewer_keywords:
- NUMERIC_PRECISION
- COLUMN_PROPID
- DATA_TYPE
- ORDINAL_POSITION
- m_nMaxLength
- DESCRIPTION class data member
- m_nDateTimePrecision
- m_bColumnHasDefault
- m_szCollationName
- m_guidType
- CColumnsInfo parameter class
- COLLATION_SCHEMA
- m_szDomainSchema
- COLUMN_HASDEFAULT
- CHARACTER_OCTET_LENGTH
- m_szDomainName
- DOMAIN_NAME
- DOMAIN_SCHEMA
- m_szTableSchema
- TABLE_CATALOG
- m_szCharSetCatalog
- m_szColumnDefault
- TABLE_NAME
- COLUMN_FLAGS
- m_szDomainCatalog
- m_nOrdinalPosition
- m_nColumnPropID
- NUMERIC_SCALE
- COLLATION_CATALOG
- DATETIME_PRECISION
- TABLE_SCHEMA
- m_nNumericPrecision
- m_szColumnName
- COLUMN_NAME
- m_nOctetLength
- IS_NULLABLE
- m_bIsNullable
- m_szTableCatalog
- COLLATION_NAME
- m_szDescription
- m_szTableName
- CColumns typedef class
- m_nDataType
- m_nNumericScale
- m_szCollationCatalog
- m_szCollationSchema
- CHARACTER_SET_NAME
- m_nColumnFlags
- COLUMN_GUID
- CHARACTER_MAXIMUM_LENGTH
- m_szCharSetName
- m_guidColumn
- CHARACTER_SET_SCHEMA
- CHARACTER_SET_CATALOG
- DOMAIN_CATALOG
- m_szCharSetSchema
- COLUMN_DEFAULT
ms.assetid: 7a4ca8e8-e041-4def-8c1a-00c211f7da0b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 712bfbbcd3fd5440e3e27cdf7d21709c914d7b74
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ccolumns-ccolumnsinfo"></a>CColumns、CColumnsInfo
Typedef クラスを呼び出す**CColumns**そのパラメーター クラスを実装する**CColumnsInfo**です。  
  
## <a name="remarks"></a>コメント  
 参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)typedef クラスの使用に関する詳細についてはします。  
  
 このクラスは、特定のユーザーにアクセス可能である、カタログで定義されているテーブルの列を識別します。  
  
 次の表には、クラスのデータ メンバーとその対応する OLE DB 列が一覧表示します。 参照してください[COLUMNS 行セット](https://msdn.microsoft.com/en-us/library/ms723052.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマと列の詳細についてはします。  
  
|データ メンバー|OLE DB 列|  
|------------------|--------------------|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szColumnName|COLUMN_NAME|  
|m_guidColumn|COLUMN_GUID|  
|m_nColumnPropID|COLUMN_PROPID|  
|m_nOrdinalPosition|ORDINAL_POSITION|  
|m_bColumnHasDefault|COLUMN_HASDEFAULT|  
|m_szColumnDefault|COLUMN_DEFAULT|  
|m_nColumnFlags|COLUMN_FLAGS|  
|m_bIsNullable|IS_NULLABLE|  
|m_nDataType|DATA_TYPE|  
|m_guidType|TYPE_GUID|  
|m_nMaxLength|CHARACTER_MAXIMUM_LENGTH|  
|m_nOctetLength|CHARACTER_OCTET_LENGTH|  
|m_nNumericPrecision|NUMERIC_PRECISION|  
|m_nNumericScale|NUMERIC_SCALE|  
|m_nDateTimePrecision|DATETIME_PRECISION|  
|m_szCharSetCatalog|CHARACTER_SET_CATALOG|  
|m_szCharSetSchema|CHARACTER_SET_SCHEMA|  
|m_szCharSetName|CHARACTER_SET_NAME|  
|m_szCollationCatalog|COLLATION_CATALOG|  
|m_szCollationSchema|COLLATION_SCHEMA|  
|m_szCollationName|COLLATION_NAME|  
|m_szDomainCatalog|DOMAIN_CATALOG|  
|m_szDomainSchema|DOMAIN_SCHEMA|  
|m_szDomainName|DOMAIN_NAME|  
|m_szDescription|説明|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbsch.h  
  
## <a name="see-also"></a>参照  
 [CatDB](../../visual-cpp-samples.md)   
 [CRestrictions クラス](../../data/oledb/crestrictions-class.md)