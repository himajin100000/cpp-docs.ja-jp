---
title: "リンケージなし | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: abacc6fbd49f9f42620385a4206c9412648c173b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="no-linkage"></a>リンケージなし
ブロック内の識別子の宣言に `extern` ストレージ クラス指定子が含まれていない場合、その識別子はリンケージを持たず、関数に対して一意になります。  
  
 次の識別子にはリンケージがありません。  
  
-   オブジェクトまたは関数以外として宣言された識別子  
  
-   関数パラメーターとして宣言された識別子  
  
-   `extern` ストレージ クラス指定子なしで宣言されたオブジェクトのブロック スコープ指定子  
  
 識別子にリンケージがない場合、同じスコープ レベルで同じ名前を再度 (宣言子または型指定子で) 宣言すると、シンボルの再定義エラーが発生します。  
  
## <a name="see-also"></a>参照  
 [extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)