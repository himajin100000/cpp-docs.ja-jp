---
title: "コンパイラの警告 (レベル 1) C4420 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4420
dev_langs:
- C++
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a57803cb584f5ee54ad5533366e6aadc85d1acf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4420"></a>コンパイラの警告 (レベル 1) C4420
'operator': 演算子は使用できません代わりに 'operator' を使用する。実行時のチェックは中途終了される可能性があります。  
  
 使用するときに、この警告が生成された、 [/rtcv させる](../../build/reference/rtc-run-time-error-checks.md)(新規/削除の確認をベクトル) ベクター フォームが存在しない場合。 この例では、非ベクター形式が使用されます。  
  
 /Rtcv を正しく動作させるためには、コンパイラは常に呼び出すベクトル形式の[新しい](../../cpp/new-operator-cpp.md)/[削除](../../cpp/delete-operator-cpp.md)ベクター構文を使用した場合。