---
title: "DispatchState 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
dev_langs:
- C++
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76deac0daa3a8bce2880b2cc9afda0faae263558
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="dispatchstate-structure"></a>DispatchState 構造体
`DispatchState` 構造体は、状態を `IExecutionContext::Dispatch` メソッドに転送するために使用されます。 `Dispatch` メソッドが `IExecutionContext` インターフェイスで呼び出される状況を示します。  
  
## <a name="syntax"></a>構文  
  
```
struct DispatchState;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[DispatchState::DispatchState](#ctor)|新しい `DispatchState` オブジェクトを構築します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[DispatchState::m_dispatchStateSize](#m_dispatchstatesize)|この構造体のサイズ、バージョン管理のために使用します。|  
|[DispatchState::m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|このコンテキストが入力したかどうかを示す、`Dispatch`メソッド以前のコンテキストに非同期的にブロックされているためです。 これは、UMS スケジューリング コンテキストでのみ使用され、値に設定されている`0`他のすべての実行コンテキスト。|  
|[DispatchState::m_reserved](#m_reserved)|ビットが将来の情報を渡すために予約されています。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `DispatchState`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a>  Dispatchstate::dispatchstate コンス トラクター  
 新しい `DispatchState` オブジェクトを構築します。  
  
```
DispatchState();
```  
  
##  <a name="m_dispatchstatesize"></a>  Dispatchstate::m_dispatchstatesize データ メンバー  
 この構造体のサイズ、バージョン管理のために使用します。  
  
```
unsigned long m_dispatchStateSize;
```  
  
##  <a name="m_fispreviouscontextasynchronouslyblocked"></a>  DispatchState::m_fIsPreviousContextAsynchronouslyBlocked Data Member  
 このコンテキストが入力したかどうかを示す、`Dispatch`メソッド以前のコンテキストに非同期的にブロックされているためです。 これは、UMS スケジューリング コンテキストでのみ使用され、値に設定されている`0`他のすべての実行コンテキスト。  
  
```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```  
  
##  <a name="m_reserved"></a>  Dispatchstate::m_reserved データ メンバー  
 ビットが将来の情報を渡すために予約されています。  
  
```
unsigned int m_reserved : 31;
```  
  
## <a name="see-also"></a>参照  
 [concurrency 名前空間](concurrency-namespace.md)
