---
title: "Cdynamicparameteraccessor:setparam |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor.SetParam
- ATL.CDynamicParameterAccessor.SetParam
- SetParam
- CDynamicParameterAccessor:SetParam
- CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor::SetParam
dev_langs:
- C++
helpviewer_keywords:
- SetParam method
ms.assetid: e2349220-545c-46ad-90da-9113ac52551a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3fcedc0d54e5b25eb4490425253f6c1bfd139a85
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicparameteraccessorsetparam"></a>CDynamicParameterAccessor:SetParam
パラメーターを指定 (文字列以外の) データを使用してバッファーを設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
template <class ctype>
bool SetParam(DBORDINAL nParam,  
               constctype* pData,  
               DBSTATUS status = DBSTATUS_S_OK) throw();  

template <class ctype>  
bool SetParam(TCHAR* pParamName,  
               const ctype* pData,  
               DBSTATUS status = DBSTATUS_S_OK) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ctype`  
 データ型ではテンプレート パラメーター。  
  
 `nParam`  
 [in]パラメーターの数 (1 からのオフセット)。 に対するパラメーター 0 は、戻り値に予約されています。 パラメーター数は、SQL またはストアド プロシージャの呼び出しでその順序に基づいて、パラメーターのインデックスです。 例:  
  
 [!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-setparam_1.cpp)]  
  
 `pParamName`  
 [in]パラメーターの名前。  
  
 `pData`  
 [in]バッファーに書き込まれるデータを含むメモリへのポインター。  
  
 *status*  
 [in]`DBSTATUS`列の状態。 詳細について`DBSTATUS`値を参照してください[ステータス](https://msdn.microsoft.com/en-us/library/ms722617.aspx)で、 *OLE DB プログラマーズ リファレンス*、または検索`DBSTATUS`oledb.h でします。  
  
## <a name="return-value"></a>戻り値  
 返します**true**成功した場合または**false**エラー発生時にします。  
  
 使用して`SetParam`をバッファーに文字列以外のパラメーターのデータを設定します。 使用して[SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md)をバッファーに文字列パラメーターのデータを設定します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)