---
title: "コンパイラ エラー C3381 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3381
dev_langs:
- C++
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af632ae602cacb5204f1fac1088bef8a6cd20168
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3381"></a>コンパイラ エラー C3381
'アセンブリ' : アセンブリ アクセス指定子は、/clr オプションと共にコンパイルされたコードでのみ使用できます  
  
 ネイティブ型をアセンブリ外部から参照できることができますが、指定できるは、ネイティブな型のアセンブリのアクセス権のみ、 **/clr**コンパイルします。  
  
 詳細については、次を参照してください。[可視性を入力](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)と[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3381 を生成します。  
  
```  
// C3381.cpp  
// compile with: /c  
public class A {};   // C3381  
```