---
title: "コンパイラ エラー C2654 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2654
dev_langs:
- C++
helpviewer_keywords:
- C2654
ms.assetid: ca7de1bd-576b-40bf-96fc-a91984827d20
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fcb6ca8de876c94840e2efe98268128ec9021fab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2654"></a>コンパイラ エラー C2654
'identifier': メンバー関数の外でメンバーがアクセスしようとしました  
  
 宣言内でのメンバーにアクセスします。 メンバー データは、メンバー関数でのみアクセスできます。  
  
 宣言内で変数を初期化しようとするときは、このエラーを発生することができます。 この目的のためには、コンス トラクターを使用します。