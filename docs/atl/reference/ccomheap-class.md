---
title: "CComHeap クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3cf86ebe45cdb0a70af6eebaaed90690e83e8db7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ccomheap-class"></a>CComHeap クラス
このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) COM メモリの割り当て関数を使用します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CComHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComHeap::Allocate](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|  
|[Ccomheap::free](#free)|このメモリ マネージャーによって割り当てられたメモリ ブロックを解放するには、このメソッドを呼び出します。|  
|[CComHeap::GetSize](#getsize)|このメモリ マネージャーによって割り当てられたメモリ ブロックの割り当てサイズを取得するには、このメソッドを呼び出します。|  
|[Ccomheap::reallocate](#reallocate)|このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。|  
  
## <a name="remarks"></a>コメント  
 `CComHeap`COM 割り当て関数を使用してメモリ割り当て関数を実装する[CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727)、 [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722)、 [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226)、および[CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)です。 割り当てることができるメモリの最大量と等しい**INT_MAX** (2,147, 483,647) バイトです。  
  
## <a name="example"></a>例  
 例を参照して[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IAtlMemMgr`  
  
 `CComHeap`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** ATLComMem.h  
  
##  <a name="allocate"></a>CComHeap::Allocate  
 メモリ ブロックを割り当てるには、このメソッドを呼び出します。  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBytes`  
 新しいメモリ ブロック内の要求されたバイト数。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す[ccomheap::free](#free)または[ccomheap::reallocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。  
  
 使用して実装[CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727)です。  
  
##  <a name="free"></a>Ccomheap::free  
 このメモリ マネージャーによって割り当てられたメモリ ブロックを解放するには、このメソッドを呼び出します。  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。 NULL は有効な値であり、何も行われません。  
  
### <a name="remarks"></a>コメント  
 使用して実装[CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722)です。  
  
##  <a name="getsize"></a>CComHeap::GetSize  
 このメモリ マネージャーによって割り当てられたメモリ ブロックの割り当てサイズを取得するには、このメソッドを呼び出します。  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。  
  
### <a name="return-value"></a>戻り値  
 割り当てられたメモリ ブロックのサイズをバイト単位で返します。  
  
### <a name="remarks"></a>コメント  
 使用して実装[IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226)です。  
  
##  <a name="reallocate"></a>Ccomheap::reallocate  
 このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。  
  
 `nBytes`  
 新しいメモリ ブロック内の要求されたバイト数。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す[ccomheap::free](#free)このメソッドによって割り当てられたメモリを解放します。  
  
 使用して実装[CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)です。  
  
## <a name="see-also"></a>参照  
 [DynamicConsumer サンプル](../../visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CWin32Heap クラス](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap クラス](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr クラス](../../atl/reference/iatlmemmgr-class.md)
