---
title: "Comptr::attach メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method
ms.assetid: 5b911f2d-9830-4dc7-b9e3-527abd55d2c8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2096a0ae38d00a0fe23789e21a039df76bfb9c58
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comptrattach-method"></a>ComPtr::Attach メソッド
この ComPtr と、現在のテンプレート型パラメーターで指定されたインターフェイスの種類を関連付けます。  
  
## <a name="syntax"></a>構文  
  
```  
void Attach(  
   _In_opt_ InterfaceType* other  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `other`  
 インターフェイスの型。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [ComPtr クラス](../windows/comptr-class.md)