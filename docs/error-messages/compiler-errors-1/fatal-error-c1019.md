---
title: "致命的なエラー C1019 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1019
dev_langs:
- C++
helpviewer_keywords:
- C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 77374884efcb7aee367e436f9dc07c8df9c398d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1019"></a>致命的なエラー C1019
予期しない #else です。  
  
 `#else` ディレクティブが、 `#if`、 `#ifdef`、または `#ifndef` 構成体の外側に置かれています。 `#else` は、これらの構成体のいずれかの内側だけで使用してください。  
  
 次の例では C1019 が生成されます。  
  
```  
// C1019.cpp  
#else   // C1019  
#endif  
  
int main() {}  
```  
  
 考えられる解決方法:  
  
```  
// C1019b.cpp  
#if 1  
#else  
#endif  
  
int main() {}  
```