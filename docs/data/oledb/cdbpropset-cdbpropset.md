---
title: "Cdbpropset::cdbpropset |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBPropSet.CDBPropSet
- CDBPropSet::CDBPropSet
- ATL::CDBPropSet::CDBPropSet
- ATL.CDBPropSet.CDBPropSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropSet class, constructor
ms.assetid: 02ae5d9e-c067-47ca-8111-a03e86b5626b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: db118c9c814d957c43f11414ee583a2ccc7a416b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cdbpropsetcdbpropset"></a>CDBPropSet::CDBPropSet
コンストラクターです。 初期化、 **rgProperties**、 **cProperties**、および**コンス トラクターは**のフィールド、 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)構造体。  
  
## <a name="syntax"></a>構文  
  
```cpp
      CDBPropSet(const GUID& guid);  

CDBPropSet(const CDBPropSet& propset);  

CDBPropSet();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `guid`  
 [in]初期化するために使用される GUID、**コンス トラクターは**フィールドです。  
  
 *propset*  
 [in]別`CDBPropSet`コピー コンス トラクターのオブジェクト。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDBPropSet クラス](../../data/oledb/cdbpropset-class.md)   
 [CDBPropSet::SetGUID](../../data/oledb/cdbpropset-setguid.md)   
 [DBPROP 構造体](https://msdn.microsoft.com/en-us/library/ms717970.aspx)