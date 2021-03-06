---
title: "CNoAccessor クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
dev_langs:
- C++
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 02d577350a4a4221a2dcf9a8a3364de9ea4ce44e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cnoaccessor-class"></a>CNoAccessor クラス
テンプレート引数として使用できます (`TAccessor`) テンプレート クラスのなど`CCommand`と`CTable`、アクセサー クラスの引数を必要とします。  
  
## <a name="syntax"></a>構文

```cpp
class CNoAccessor  
```  
  
## <a name="remarks"></a>コメント  
 使用して`CNoAccessor`出力列やパラメーターをサポートするクラスしたくない場合は、テンプレート引数として。  
  
 `CNoAccessor` その他のアクセサー クラスのメソッドに対応しているそれぞれの次のスタブ メソッドを実装します。  
  
-   **BindColumns** -アクセサーに列をバインドします。  
  
-   `BindParameters` -列に作成されたパラメーターをバインドします。  
  
-   **バインド**-バインドを作成します。  
  
-   **閉じる**-アクセサーを閉じます。  
  
-   `ReleaseAccessors` クラスで作成したアクセサーを解放します。  
  
-   `FreeRecordMemory` -現在のレコードを解放する必要があるすべての列を解放します。  
  
-   `GetColumnInfo` -開かれた行セットから列情報を取得します。  
  
-   `GetNumAccessors` -クラスで作成したアクセサーの数を取得します。  
  
-   `IsAutoAccessor` 移動操作中に、アクセサーのデータが自動的に取得される場合に true を返します。  
  
-   `GetHAccessor` -指定されたアクセサーのアクセサー ハンドルを取得します。  
  
-   `GetBuffer` -ブックマーク バッファーへのポインターを取得します。  
  
-   **NoBindOnNullRowset** -空の行セットのデータ バインディングを防止します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)