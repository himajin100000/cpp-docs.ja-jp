---
title: "NMAKE の致命的なエラー U1035 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1035
dev_langs:
- C++
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0d7730f882b40c24822cb4b8e2c6a12147cacf2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1035"></a>NMAKE の致命的なエラー U1035
構文エラー: 予想 ':' または '=' 区切り記号  
  
 いずれか、コロン (**:**) または等号 (=) (**=**) が必要です。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  ターゲットの後ろにコロンがありません。  
  
2.  1 文字のターゲットの後にコロンと (a:) などの領域がありません。 (Nmake の) には、ドライブの指定とそれが解釈されます。  
  
3.  推論規則の後ろにコロンがありません。  
  
4.  マクロ定義は、等号 (=) で後にありません。  
  
5.  後ろに円記号の文字 (**\\**) が新しい行にコマンドを続行することが使用されました。  
  
6.  NMAKE の構文規則に従っていない文字列が表示されます。  
  
7.  メイクファイルのワード プロセッサで形式でした。