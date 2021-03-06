---
title: "純粋と検証可能なコード (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9ba218772bdedf772e995bb9289b18452d599e6c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="pure-and-verifiable-code-ccli"></a>純粋なコードと検証可能なコード (C++/CLI)
.NET プログラミングに対して、Visual Studio 2017 での Visual C を使用して混在アセンブリの作成をサポートして、 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプション。 **/Clr: 純粋な**と**/clr:safe**オプションは、Visual Studio 2015 の時点では廃止され、コンパイラの将来のバージョンで削除される予定です。 コードは、検証可能である必要がある場合、お勧め c# に移植することとします。
  
## <a name="mixed-clr"></a>混合 (/clr)  
 混在アセンブリ (コンパイルした**/clr**) アンマネージ両方を含めること、および .NET 機能を利用できるようにする、管理対象の部分には、ネイティブ コードですが含まれています。 このため、プロジェクト全体を書き直すことなく、.NET 機能を使用するようにアプリケーションやコンポーネントを更新できます。 Visual C を使用して、この方法でマネージ コードとネイティブ コードを混在させると、C++ Interop は呼び出されます。 詳細については、次を参照してください。[混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)と[ネイティブ モードと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)です。  
  
  
マネージ アセンブリから呼び出し P/invoke を使用してネイティブ Dll にコンパイルされますが、セキュリティ設定によっては実行時に失敗する可能性があります。  
  
コンパイラは渡されますが確認不可能なアセンブリとなる 1 つのコーディング例があります。スコープ解決演算子を使用し、オブジェクト インスタンスを通じて仮想関数を呼び出す場合です。  たとえば、`MyObj -> A::VirtualFunction();` のように指定します。  
  
## <a name="see-also"></a>参照  
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
