---
title: "no_dual_interfaces |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- no_dual_interfaces
dev_langs:
- C++
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba20fcba43cc23dfce447d7e91955a43c28a6a31
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**C 固有の仕様**  
  
 コンパイラがデュアル インターフェイス メソッドのラッパー関数を生成する方法を変更します。  
  
## <a name="syntax"></a>構文  
  
```  
no_dual_interfaces  
```  
  
## <a name="remarks"></a>コメント  
 通常、ラッパーは、そのインターフェイスの仮想関数テーブルからメソッドを呼び出します。 `no_dual_interfaces`、ラッパーを呼び出す代わりに**idispatch::invoke**メソッドを呼び出します。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>参照  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)