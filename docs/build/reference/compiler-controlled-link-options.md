---
title: "コンパイラで制御される LINK オプション |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- LINK tool [C++], compiler-controlled options
- linker [C++], CL compiler control
- linking [C++], affected by CL features
- cl.exe compiler [C++], features that affect linking
- cl.exe compiler [C++], controlling linker
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc899fc7f1fc8c1805648e72e14ef13853841c90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-controlled-link-options"></a>Compiler-Controlled LINK Options
/C オプションを指定していない限り、CL コンパイラは自動的にリンクを呼び出します。 CL は、いくつかのコマンド ライン オプションと引数をリンカーに制御を提供します。 次の表には、CL でリンクを制御する機能をまとめたものです。  
  
|CL の仕様|リンクに影響を与える CL アクション|  
|----------------------|---------------------------------|  
|ファイル名拡張子が .c、.cxx、.cpp ファイル、または .def 以外|リンクへの入力として、ファイル名を渡します|  
|*filename*.def|/DEF を渡します:*filename*.def|  
|/F*数*|パス/STACK:*数*|  
|/Fd*ファイル名*|/PDB を渡します:*ファイル名*|  
|/Fe*ファイル名*|渡します/アウト:*ファイル名*|  
|/Fm*ファイル名*|パス/MAP:*ファイル名*|  
|/Gy|パッケージ化された関数 (Comdat); の作成します。関数レベルのリンクを可能に|  
|/LD|/DLL を渡します|  
|/LDd|/DLL を渡します|  
|/link|コマンドラインの残りの部分を LINK に渡します|  
|/MD、/MT または|.Obj ファイル内の既定のライブラリ名を配置します。|  
|/Mdd または/MTd|.Obj ファイルの既定のライブラリ名を配置します。 シンボルを定義**_DEBUG**|  
|/nologo|/NOLOGO を渡します|  
|/Zd|/DEBUG のパス|  
|/Zi または/Z7|/DEBUG のパス|  
|/Zl|.Obj ファイルから既定のライブラリ名を省略します。|  
  
 詳細については、「[コンパイラ オプション](../../build/reference/compiler-options.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)