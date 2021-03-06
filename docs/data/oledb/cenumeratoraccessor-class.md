---
title: "CEnumeratorAccessor クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
dev_langs:
- C++
helpviewer_keywords:
- CEnumeratorAccessor class
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5b3efe610e53d591f17d3ce227c6dbc09f0e23ce
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cenumeratoraccessor-class"></a>CEnumeratorAccessor クラス
によって使用される[CEnumerator](../../data/oledb/cenumerator-class.md)列挙子の行セットからデータにアクセスします。  
  
## <a name="syntax"></a>構文

```cpp
class CEnumeratorAccessor  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_bIsParent](../../data/oledb/cenumeratoraccessor-m-bisparent.md)|行が列挙子である場合は、列挙子は、親列挙子を回復するかどうかを示す変数です。|  
|[m_nType](../../data/oledb/cenumeratoraccessor-m-ntype.md)|行がデータ ソースまたは列挙子について説明するかどうかを示す変数です。|  
|[m_szDescription](../../data/oledb/cenumeratoraccessor-m-szdescription.md)|データ ソースまたは列挙子の説明です。|  
|[m_szName](../../data/oledb/cenumeratoraccessor-m-szname.md)|データ ソースまたは列挙子の名前。|  
|[m_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)|渡す文字列[ため](http://msdn.microsoft.com/library/windows/desktop/ms680604)をデータ ソースまたは列挙子のモニカーを取得します。|  
  
## <a name="remarks"></a>コメント  
 この行セットは、データ ソースと現在の列挙子から見えるの列挙子で構成されます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)