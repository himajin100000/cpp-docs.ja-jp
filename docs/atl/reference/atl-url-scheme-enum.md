---
title: "ATL_URL_SCHEME 列挙 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATLUTIL/ATL::ATL_URL_SCHEME
ms.assetid: f4131046-8ba0-4ec1-8209-84203f05d20e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3aa6cf05204f4483245073b5c260e552e935dd0f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="atlurlscheme"></a>ATL_URL_SCHEME  

この列挙体のメンバーがで認識されるスキームの定数を提供[CUrl](curl-class.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      enum ATL_URL_SCHEME{  
   ATL_URL_SCHEME_UNKNOWN = -1,  
   ATL_URL_SCHEME_FTP     = 0,  
   ATL_URL_SCHEME_GOPHER  = 1,  
   ATL_URL_SCHEME_HTTP    = 2,  
   ATL_URL_SCHEME_HTTPS   = 3,  
   ATL_URL_SCHEME_FILE    = 4,  
   ATL_URL_SCHEME_NEWS    = 5,  
   ATL_URL_SCHEME_MAILTO  = 6,  
   ATL_URL_SCHEME_SOCKS   = 7  
};  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlutil.h  
  
## <a name="see-also"></a>参照  
 [概念](../active-template-library-atl-concepts.md)   
 [CUrl::SetScheme](curl-class.md#setscheme)   
 [CUrl::GetScheme](curl-class.md#getscheme)