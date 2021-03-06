---
title: "noncreatable |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.noncreatable
dev_langs:
- C++
helpviewer_keywords:
- noncreatable attribute
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb9f67b4efac28a1cacd6301c8ca849246f9a481
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="noncreatable"></a>noncreatable
単独でインスタンス化できないオブジェクトを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[noncreatable]  
  
```  
  
## <a name="remarks"></a>コメント  
 **Noncreatable** C++ 属性と同じ機能を持つ、 [noncreatable](http://msdn.microsoft.com/library/windows/desktop/aa367118) MIDL 属性、生成されたに自動的に渡されるとします。コンパイラで IDL ファイルです。  
  
 ATL を使用するプロジェクト内でこの属性を使用する場合、属性の動作を変更します。 上記の動作だけでなく、属性でもは挿入、[役立つ](../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto)マクロです。 このマクロは ATL にそのオブジェクトを外部で作成できないことを示します。  
  
## <a name="example"></a>例  
  
```  
// cpp_attr_ref_noncreatable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("11111111-1111-1111-1111-111111111111")]  
__interface A   
{  
};  
  
[coclass, uuid("11111111-1111-1111-1111-111111111112"), noncreatable]  
class CMyClass : public A   
{  
   HRESULT xx();  
};  
```  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`|  
|**反復可能**|×|  
|**必要な属性**|**coclass**|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
