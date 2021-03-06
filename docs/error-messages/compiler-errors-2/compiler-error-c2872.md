---
title: コンパイラ エラー C2872 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2872
dev_langs:
- C++
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 88d770823efdad4f58431f20b5685dfbb6bfec3b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2872"></a>コンパイラ エラー C2872
'*シンボル*': あいまいなシンボル  
  
コンパイラを参照する記号を特定できません。 指定した名前の 2 つ以上のシンボルは、スコープでです。 コンパイラのあいまいなシンボルが次のファイルの場所と宣言のエラー メッセージは、ノートを参照してください。 この問題を解決することが完全に修飾する、あいまいなシンボル、名前空間、たとえばを使用して、`std::byte`または`::byte`です。 使用することも、[名前空間の別名](../../cpp/namespaces-cpp.md#namespace_aliases)ソース コード内のシンボルを明確化際に、使用するための便利な短い名前を含まれる名前空間に提供しています。  
  
C2872 は、ヘッダー ファイルが含まれている場合に発生することができます、[ディレクティブを使用して](../../cpp/namespaces-cpp.md#using_directives)、後続のヘッダー ファイルが含まれるともに指定された名前空間内にある型を格納している、`using`ディレクティブです。 指定して、`using`後にのみ、ヘッダー ファイルがで指定されたディレクティブ`#include`です。  
  
 C2872 の詳細については、サポート技術情報の記事を参照してください[PRB: コンパイラ エラー時に使用する #import Visual c .NET での XML で](http://support.microsoft.com/kb/316317)と["エラー C2872: 'Platform': あいまいなシンボルが"を使用すると、エラー メッセージ、。Visual Studio 2013 で名前空間を Windows::Foundation::Metadata](https://support.microsoft.com/kb/2890859)です。  
  
## <a name="example"></a>例  
 次の例では、という名前の変数に、あいまいな参照が行われるので C2872 が生成されます`i`以外の場合は 2 つと同じ名前の変数のスコープは。  
  
```cpp  
// C2872.cpp  
// compile with: cl /EHsc C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok, uses i from global namespace  
   A::i++;   // ok, uses i from namespace A  
   i++;   // C2872 ambiguous: ::i or A::i? 
   // To fix this issue, use the fully qualified name
   // for the intended variable. 
}  
```