---
title: "メイクファイルのコマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- commands, makefiles
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5361012fd388f49d8eb956ec1a4fa1bdd53a2dcc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="commands-in-a-makefile"></a>メイクファイルのコマンド
説明のブロックまたは推論のルールは、依存関係が最新でない場合に実行するコマンドのブロックを指定します。 しない限り、(nmake の) を実行する前に各コマンドが表示されます、/S**です。サイレント**、 **!CMDSWITCHES**、または @ を使用します。 記述ブロックの後にコマンドのブロックがありません (nmake の) に一致する推論規則の表示されます。  
  
 コマンドのブロックには、それぞれ独自の行に 1 つまたは複数のコマンドが含まれています。 依存関係またはルールとコマンドのブロックの間に空白行は表示できません。 ただし、スペースまたはタブのみが含まれる行も表示されます。この行は null のコマンドとして解釈され、エラーは発生しません。 空白行は、コマンドラインの間で許可されます。  
  
 コマンド ラインは、1 つ以上のスペースまたはタブから始まります。 改行文字が続く円記号 (\) は、コマンド内の領域として解釈されます。行の末尾に円記号を使用して、次の行にコマンドを続行します。 NMAKE が文字どおり、円記号を解釈し、スペースまたはタブを含む、他の文字が円記号に続く場合。  
  
 コマンドの前に、セミコロン (;) が、コマンドのブロックに依存しているかどうかを示す依存関係の行または推論規則に表示されます。  
  
```  
project.obj : project.c project.h ; cl /c project.c  
```  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
 [コマンド修飾子](../build/command-modifiers.md)  
  
 [ファイル名分割構文](../build/filename-parts-syntax.md)  
  
 [メイクファイルのインライン ファイル](../build/inline-files-in-a-makefile.md)  
  
## <a name="see-also"></a>参照  
 [NMAKE リファレンス](../build/nmake-reference.md)