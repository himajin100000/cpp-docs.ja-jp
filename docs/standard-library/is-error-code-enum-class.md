---
title: "is_error_code_enum クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- system_error/std::is_error_code_enum
dev_langs:
- C++
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5c7eb2de5bf2669f7833fffb8003ee1f0886c4bf
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="iserrorcodeenum-class"></a>is_error_code_enum クラス
[error_code](../standard-library/error-code-class.md) 列挙型をテストする型述語を表します。  
  
## <a name="syntax"></a>構文  
  
```
template <_Enum>
class is_error_code_enum;
```  
  
## <a name="remarks"></a>コメント  
 型 `_Enum` が型 `error_code` のオブジェクトを格納するのに適した列挙型の値である場合、この[型述語](../standard-library/type-traits.md)のインスタンスは true を保持します。  
  
 ユーザー定義型のこの型に特殊化を追加できます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<system_error>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)   
 [<system_error>](../standard-library/system-error.md)



