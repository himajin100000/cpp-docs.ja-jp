---
title: "Srwlockexclusivetraits::unlock メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 7fd6b0fb-8b88-4a43-aa74-0d7fe47a0da6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9b6c9fab4863c1d77e61a3cc5f48806a1d2ea8a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="srwlockexclusivetraitsunlock-method"></a>SRWLockExclusiveTraits::Unlock メソッド
指定した SRWLock オブジェクトの排他的に制御を解放します。  
  
## <a name="syntax"></a>構文  
  
```  
inline static void Unlock(  
   _In_ Type srwlock  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `srwlock`  
 SRWLock オブジェクトへのハンドルします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>参照  
 [SRWLockExclusiveTraits 構造体](../windows/srwlockexclusivetraits-structure.md)