---
title: "入出力 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- input routines
- I/O [CRT]
- I/O routines
- I/O [CRT], routines
- output routines
ms.assetid: 1c177301-e341-4ca0-aedc-0a87fe1c75ae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 35e97e7bbbc04699e813b6890180512043c4e25d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="input-and-output"></a>入出力
I/O 関数はファイルやデバイスとの間でデータの読み書きを行います。 ファイル I/O 操作は、テキスト モードまたはバイナリ モードで行われます。 Microsoft ランタイム ライブラリには、次の 3 つの種類の I/O 関数があります。  
  
-   [ストリーム入出力](../c-runtime-library/stream-i-o.md)関数は、データを個々の文字のストリームとして処理します。  
  
-   [下位入出力](../c-runtime-library/low-level-i-o.md)関数は、ストリーム入出力の操作より下位の操作に対してオペレーティング システムを直接呼び出します。  
  
-   [コンソール入出力とポート入出力](../c-runtime-library/console-and-port-i-o.md)関数は、コンソール () または入出力ポートに対して読み書きを直接実行します。  
  
    > [!NOTE]
    >  ストリーム関数はバッファーされ、下位入出力関数はバッファーされないため、これら 2 つの種類の関数には一般的に互換性がありません。 特定のファイルを処理するとき、ストリーム関数または下位入出力関数のいずれかを排他的に使用してください。  
  
## <a name="see-also"></a>参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)