---
title: パブリック (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- public_cpp
dev_langs:
- C++
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ff41d2b12f43deabd82538a3e2fb10eb35ead16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="public-c"></a>public (C++)
## <a name="syntax"></a>構文  
  
```  
public:  
   [member-list]  
public base-class  
```  
  
## <a name="remarks"></a>コメント  
 クラスのメンバーの一覧の前と、**パブリック**キーワードは、それらのメンバーが何らかの関数からアクセスできることを指定します。 これは、次のアクセス指定子またはクラスの末尾までで宣言されているすべてのメンバーに適用されます。  
  
 基底クラスの名前、**パブリック**キーワードは、基本クラスのパブリックおよびプロテクト メンバーがパブリックであるを指定され、派生クラスのメンバーをそれぞれ、保護します。  
  
 クラスのメンバーの既定のアクセスはプライベートです。 構造体または共用体のメンバーの既定のアクセスはパブリックです。  
  
 基底クラスの既定のアクセスは、クラスの場合はプライベートで、構造体の場合はパブリックです。 共用体に基底クラスを設定することはできません。  
  
 詳細については、次を参照してください[プライベート](../cpp/private-cpp.md)、[保護](../cpp/protected-cpp.md)、[フレンド](../cpp/friend-cpp.md)、とでメンバー アクセス テーブル[クラス メンバーへのアクセスの制御](member-access-control-cpp.md).  
  
## <a name="clr-specific"></a>/clr 固有  
 CLR 型では、C++ アクセス指定子のキーワード (**パブリック**、 `private`、および`protected`) 型とアセンブリに関連メソッドの可視性に影響を与えることができます。 詳細については、次を参照してください。[メンバー アクセス コントロール](member-access-control-cpp.md)です。  
  
> [!NOTE]
>  コンパイルされるファイル[/LN](../build/reference/ln-create-msil-module.md)この動作の影響は受けません。 この場合、すべてのマネージ クラス (パブリックかプライベート) が表示されます。  
  
## <a name="end-clr-specific"></a>END /clr 固有  
  
## <a name="example"></a>例  
  
```  
// keyword_public.cpp  
class BaseClass {  
public:  
   int pubFunc() { return 0; }  
};  
  
class DerivedClass : public BaseClass {};  
  
int main() {  
   BaseClass aBase;  
   DerivedClass aDerived;  
   aBase.pubFunc();       // pubFunc() is accessible   
                          //    from any function  
   aDerived.pubFunc();    // pubFunc() is still public in   
                          //    derived class  
}  
```  
  
## <a name="see-also"></a>参照  
 [クラス メンバーへのアクセスを制御します。](member-access-control-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)