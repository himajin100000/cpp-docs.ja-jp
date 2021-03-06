---
title: "Cdynamicparameteraccessor::getparam |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicParameterAccessor::GetParam
- ATL.CDynamicParameterAccessor.GetParam
- CDynamicParameterAccessor::GetParam<ctype>
- CDynamicParameterAccessor.GetParam
- GetParam
- ATL::CDynamicParameterAccessor::GetParam<ctype>
- ATL::CDynamicParameterAccessor::GetParam
dev_langs:
- C++
helpviewer_keywords:
- GetParam method
ms.assetid: 893a6bf8-7b55-4f6d-8a10-a43b13be7f56
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 61d1a15cd148120914e22a566da45f579fdd72ae
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicparameteraccessorgetparam"></a>CDynamicParameterAccessor::GetParam
パラメーターのバッファーから、指定したパラメーターに文字列以外のデータを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
template <class ctype>bool GetParam(DBORDINAL nParam,   
  ctype* pData) const throw();  

template <class ctype> bool GetParam(TCHAR* pParamName,   
   ctype* pData) const throw();  

void* GetParam(DBORDINAL nParam) const throw();  

void* GetParam(TCHAR* pParamName) const throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ctype`  
 データ型ではテンプレート パラメーター。  
  
 `nParam`  
 [in]パラメーターの数 (1 からのオフセット)。 に対するパラメーター 0 は、戻り値に予約されています。 パラメーター数は、SQL またはストアド プロシージャの呼び出しでその順序に基づいて、パラメーターのインデックスです。 参照してください[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)例についてはします。  
  
 `pParamName`  
 [in]パラメーターの名前。  
  
 `pData`  
 [out]バッファーから取得されたデータを含むメモリへのポインター。  
  
## <a name="return-value"></a>戻り値  
 Template 宣言されていないバージョンでは、バッファーからデータを含むメモリへのポインターを取得します。 テンプレートのバージョンを返します**true**成功した場合または**false**エラー発生時にします。  
  
 使用して`GetParam`バッファーから文字列以外のパラメーターのデータを取得します。 使用して[GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md)バッファーから文字列パラメーターのデータを取得します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)