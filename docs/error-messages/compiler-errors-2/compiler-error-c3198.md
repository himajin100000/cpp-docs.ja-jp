---
title: コンパイラ エラー C3198 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3198
dev_langs:
- C++
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c0a82564b8c2f9e8ba785cb54dd66895c5772d3b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3198"></a>コンパイラ エラー C3198
無効な浮動小数点プラグマの使用: fenv_access プラグマは precise モードでのみ動作  
  
 [fenv_access](../../preprocessor/fenv-access.md)プラグマは、使用された、 [/fp](../../build/reference/fp-specify-floating-point-behavior.md)以外に設定**/fp: 正確な**します。  
  
 次の例では、C3198 が生成されます。  
  
```  
// C3198.cpp  
// compile with: /fp:fast  
#pragma fenv_access(on)   // C3198  
```