---
title: "空白文字 | Microsoft Docs"
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
- white space, characters
- characters, white space
ms.assetid: 030ccbdc-2db3-4dd0-88c8-f5c2669ddebf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 51476c05774103ed439ae45888717378e9f59fac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="white-space-characters"></a>空白文字
スペース、タブ、改行、復帰、書式送り、垂直タブ、復帰改行の文字は、ページ出力時には単語と行を区切るスペースとして同じ目的で使用されるため、"空白文字" と呼ばれます。空白文字があると、コードが読みやすくなります。 トークンは、空白文字によって、および、演算子や句読点などの他のトークンによって区切られます。 コードを解析するとき、C コンパイラは、空白文字が区切り記号として、または、文字定数か文字列リテラルの構成要素として使用されていない限り、空白文字を無視します。 空白文字を使用してプログラムを読みやすくしてください。 コンパイラは、コメントも空白として扱います。  
  
## <a name="see-also"></a>参照  
 [C トークン](../c-language/c-tokens.md)