---
title: "名前空間と型の可視性 (C + + CX) |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: cbc01a3a-3b69-4ded-9c42-ecbf0fd0a00e
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f3a489935b72b570f18f6fd75170f215ed751e23
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="namespaces-and-type-visibility-ccx-"></a>名前空間と型の参照範囲 (C++/CX)
名前空間は、関連する機能を持つ型をグループ化し、ライブラリ内での名前の衝突を回避するための、標準の C++ 構造体です。 Windows ランタイムの型システムでは、独自のコードも含み、すべてのパブリックの Windows ランタイム型を名前空間スコープで名前空間で宣言する必要がある必要があります。 パブリック型をグローバル スコープで宣言したり、別のクラスの中に入れ子にしたりすると、コンパイル時エラーが発生します。  
  
 .winmd ファイルには、ルート名前空間と同じ名前が必要です。 たとえば、A.B.C.MyClass という名前のクラスは、A.winmd または A.B.winmd または A.B.C.winmd という名前のメタデータ ファイルで定義されている場合のみインスタンス化できます。 実行可能ファイルの名前が .winmd ファイル名と一致する必要はありません。  
  
## <a name="type-visibility"></a>型の可視性  
 名前空間、Windows ランタイム型-標準 C++ 型とは異なり、プライベートまたはパブリック アクセシビリティを持ちます。 既定では、アクセシビリティはプライベートです。 メタデータから参照できるのはパブリック型だけです。したがって、C++ 以外の言語で記述されている可能性もあるコンポーネントとアプリから利用できるのもパブリック型だけです。 一般に、参照可能な型の規則は、参照できない型の規則よりも制限的です。これは、.NET 言語および JavaScript でサポートされていない C++ 固有の概念を参照可能な型が公開できないためです。  
  
> [!NOTE]
>  .NET 言語および JavaScript がメタデータを利用できるのは、実行時のみです。 C ++ アプリまたはコンポーネントが、他の C ++ アプリまたはコンポーネント (これには、すべて C++ で記述された Windows コンポーネントも含まれます) と通信中のときは、メタデータの実行時利用は不要です。  
  
## <a name="member-accessibility-and-visibility"></a>メンバーのアクセシビリティおよび可視性  
 プライベートの ref クラス、インターフェイス、またはデリゲートでは、パブリック アクセシビリティがあっても、メンバーはメタデータには出力されません。 パブリック ref クラスでは、ソース コードでのアクセシビリティとは無関係に、メタデータのメンバーの可視性を制御できます。 標準 C++ と同様に、最小特権の基本原則を適用します。絶対にそうする必要がある場合を除き、メタデータでメンバーを可視にしないでください。  
  
 次のアクセス修飾子を使用して、メタデータの可視性およびソース コード アクセシビリティを制御します。  
  
||||  
|-|-|-|  
|修飾子|説明|メタデータに出力されるか。|  
|private|既定のアクセシビリティ。 標準 C++ の場合と同じ意味です。|×|  
|protected|標準 C++ の場合と同じ意味であり、アプリまたはコンポーネント内およびメタデータ内では両方。|はい|  
|public|標準 C++ の場合と同じ意味です。|[はい]|  
|`public protected` - または - `protected public`|メタデータでは保護されたアクセシビリティ、アプリまたはコンポーネント内ではパブリック。|[はい]|  
|`protected private` または `private protected`|メタデータでは非可視。アプリまたはコンポーネント内では保護されたアクセシビリティ。||  
|`internal` または `private public`|メンバーは、アプリまたはコンポーネント内ではパブリックですが、メタデータでは非可視です。|×|  
  
## <a name="windows-runtime-namespaces"></a>Windows ランタイム名前空間  
 Windows API は、Windows で宣言されている型で構成されます::\*名前空間。 これらの名前空間は Windows 用に予約されており、それらの名前空間に型を追加できません。 **オブジェクト ブラウザー**では、windows.winmd ファイル内でこれらの名前空間を表示できます。 これらの名前空間に関するドキュメントについては、「 [Windows API](http://msdn.microsoft.com/library/windows/apps/br211377)」を参照してください。  
  
## <a name="ccx-namespaces"></a>C++/CX 名前空間  
 C + + CX は、Windows ランタイムの型システムのプロジェクションの一部としてこれらの名前空間の特定の種類を定義します。  
  
|||  
|-|-|  
|**名前空間**|**説明**|  
|default|組み込みの数値型と char16 型を格納します。 これらの型はすべての名前空間のスコープ内にあり、 `using` ステートメントは必要ではありません。|  
|プラットフォーム|などの Windows ランタイム型に対応している、主に、パブリック型を含む`Array<T>`、 `String`、 `Guid`、および`Boolean`です。 また、 `Platform::Agile<T>` および `Platform::Box<T>`などの、特殊なヘルパー型も含まれます。|  
|Platform::Collections|Windows ランタイム コレクションのインターフェイスを実装する具体的なコレクション クラスが含まれます`IVector`、`IMap`のようにします。 これらの型は、platform.winmd ではなく、ヘッダー ファイル、collection.h で定義されます。|  
|Platform::Details|コンパイラによって使用され、パブリックでの使用を意図されていない型を格納します。|  
  
## <a name="see-also"></a>参照  
 [型システム (C++/CX)](../cppcx/type-system-c-cx.md)