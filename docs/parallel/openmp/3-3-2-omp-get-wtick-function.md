---
title: "3.3.2 omp_get_wtick 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 1ad08500-bcb0-40d9-a81f-f131819006c9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 926ed8551ce032a52232a023a3f191a1b7efb233
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="332-ompgetwtick-function"></a>3.3.2 omp_get_wtick 関数
`omp_get_wtick`連続するクロックのティック間関数が秒の数と等しくにある倍精度浮動小数点値を返します。 形式は次のとおりです。  
  
```  
#include <omp.h>  
double omp_get_wtick(void);  
```