---
title: "CComQIPtr クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
dev_langs:
- C++
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b63e584b7c4620be0e77da034a2a419b80cf741
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ccomqiptr-class"></a>CComQIPtr クラス
COM インターフェイス ポインターを管理するためのスマート ポインター クラスです。  
  
## <a name="syntax"></a>構文  
  
```
template<class T, const IID* piid= &__uuidof(T)>  
class CComQIPtr: public CComPtr<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 格納するポインターの種類を指定する COM インターフェイスです。  
  
 `piid`  
 IID へのポインター`T`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComQIPtr::CComQIPtr](#ccomqiptr)|コンストラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CComQIPtr::operator =](#operator_eq)|メンバーのポインターにポインターを割り当てます。|  
  
## <a name="remarks"></a>コメント  
 ATL を使用して`CComQIPtr`と[CComPtr](../../atl/reference/ccomptr-class.md)から派生する COM インターフェイス ポインターを管理する[CComPtrBase](../../atl/reference/ccomptrbase-class.md)です。 両方のクラスを呼び出すことでカウント自動参照を実行する`AddRef`と**リリース**です。 オーバー ロードされた演算子は、ポインターの操作を処理します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 [CComPtr](../../atl/reference/ccomptr-class.md)  
  
 `CComQIPtr`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcomcli.h  
  
##  <a name="ccomqiptr"></a>CComQIPtr::CComQIPtr  
 コンストラクターです。  
  
```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lp`  
 インターフェイス ポインターを初期化するために使用します。  
  
 `T`  
 COM インターフェイスです。  
  
 `piid`  
 IID へのポインター`T`です。  
  
##  <a name="operator_eq"></a>CComQIPtr::operator =  
 代入演算子です。  
  
```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lp`  
 インターフェイス ポインターを初期化するために使用します。  
  
 `T`  
 COM インターフェイスです。  
  
 `piid`  
 IID へのポインター`T`です。  
  
### <a name="return-value"></a>戻り値  
 更新後にポインターを返します`CComQIPtr`オブジェクト。  
  
## <a name="see-also"></a>参照  
 [CComPtr::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)   
 [CComQIPtr::CComQIPtr](#ccomqiptr)   
 [CComPtrBase クラス](../../atl/reference/ccomptrbase-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComQIPtrElementTraits クラス](../../atl/reference/ccomqiptrelementtraits-class.md)
