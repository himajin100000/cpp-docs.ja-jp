---
title: "継承 (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- derived classes [C++]
- derived classes [C++], about derived classes
- classes [C++], derived
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 50b6b180a6def741daa47a5054f1c61d3265ebd7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="inheritance--c"></a>継承 (C++)
このセクションでは、派生クラスを使用して拡張可能プログラムを生成する方法について説明します。  
  
## <a name="overview"></a>概要  
 新しいクラスを「継承」というメカニズムを使用して既存のクラスから派生させることができます (始まる情報を参照してください[単一継承](../cpp/single-inheritance.md))。 派生に使用されるクラスは、特定の派生クラスの "基底クラス" と呼ばれます。 派生クラスは、次の構文を使用して宣言します。  
  
```  
 class Derived : [virtual] [access-specifier] Base  
{  
   // member list  
};  
 class Derived : [virtual] [access-specifier] Base1,  
 [virtual] [access-specifier] Base2, . . .  
{  
   // member list  
};  
```  
  
 クラスのタグ (名前) の後ろにコロンを指定し、その後ろに基本指定のリストが続きます。  したがって、基底クラスは、あらかじめ宣言しておく必要があります。  基本指定に、アクセス指定子、キーワードのいずれかであるには可能性がありますが含まれて**パブリック**、`protected`または`private`です。  これらのアクセス指定子は、基底クラス名の前に指定され、その基底クラスにのみ適用されます。  これらの指定子は、派生クラスで基底クラスのメンバーに対して使用されるアクセス許可を制御します。  参照してください[メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)については、基本クラスのメンバーへのアクセスにします。  アクセス指定子を省略すると、その基底クラスへのアクセスは `private` と見なされます。  基本の仕様は、キーワードを含めることがあります**仮想**仮想継承を示します。  このキーワードがある場合は、アクセス指定子の前または後に指定されます。  仮想継承を使用する場合、基底クラスは、仮想基底クラスと呼ばれます。  
  
 複数の基底クラスをコンマで区切って指定できます。  継承モデルは、1 つの基本クラスを指定すると場合、[単一継承](../cpp/single-inheritance.md)です。1 つ以上の基底クラスが指定されている場合、継承モデルと呼びます[多重継承](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca)、  
  
 ここでは、次のトピックについて説明します。  
  
-   [単一継承](../cpp/single-inheritance.md)  
  
-   [多重継承](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca)  
  
-   [複数の基本クラス](../cpp/multiple-base-classes.md)  
  
-   [仮想関数](../cpp/virtual-functions.md)  
  
-   [明示的なオーバーライド](../cpp/explicit-overrides-cpp.md)  
  
-   [抽象クラス](../cpp/abstract-classes-cpp.md)  
  
-   [スコープ規則の概要](../cpp/summary-of-scope-rules.md)  
  
 [_ _Super](../cpp/super.md)と[_ _interface](../cpp/interface.md)キーワードは、このセクションに記載されています。  
  
## <a name="see-also"></a>参照  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)