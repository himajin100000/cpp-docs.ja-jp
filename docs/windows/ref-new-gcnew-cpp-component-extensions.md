---
title: "ref new、gcnew (C++ コンポーネント拡張) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- gcnew
- ref new
- gcnew_cpp
dev_langs:
- C++
helpviewer_keywords:
- ref new keyword (C++)
- gcnew keyword [C++]
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 616117f7274d6f68456aa23614fb354a71982fb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ref-new-gcnew--c-component-extensions"></a>ref new、gcnew (C++ コンポーネント拡張)
`ref new`集計キーワードは、ガベージ コレクトされるオブジェクトにアクセスできなくなったし、のハンドルを返すときに、型のインスタンスを割り当てます ([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)) に割り当てられたオブジェクト。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 `ref new` によって割り当てられた型のインスタンスのメモリは、自動的に解放されます。  
  
 `ref new` 演算では、メモリを割り当てることができないと `OutOfMemoryException` がスローされます。  
  
 ネイティブ C++ の型のメモリの割り当てし、割り当て解除の方法の詳細については、次を参照してください。[新しい演算子と delete 演算子](../cpp/new-and-delete-operators.md)です。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 有効期間が自動的に管理される Windows ランタイム オブジェクトのメモリを割り当てるには、`ref new` を使用します。 オブジェクトは、参照の最後のコピーがスコープ外になった後で参照カウントが 0 になると、自動的に解放されます。 詳細については、次を参照してください。 [Ref クラスと構造体](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)です。  
  
### <a name="requirements"></a>必要条件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 マネージ型 (参照型または値型) のメモリは `gcnew` によって割り当てられ、ガベージ コレクションによって解放されます。  
  
### <a name="requirements"></a>必要条件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次の例では、`gcnew` を使用して Message オブジェクトを割り当てています。  
  
```  
// mcppv2_gcnew_1.cpp  
// compile with: /clr  
ref struct Message {  
   System::String^ sender;  
   System::String^ receiver;  
   System::String^ data;  
};  
  
int main() {  
   Message^ h_Message  = gcnew Message;  
  //...  
}  
```  
  
 **例**  
  
 次の例では、`gcnew` を使用して、参照型のように使用するボックス化された値型を作成しています。  
  
```  
// example2.cpp : main project file.  
// compile with /clr  
using namespace System;  
value class Boxed {  
    public:  
        int i;  
};  
int main()  
{  
    Boxed^ y = gcnew Boxed;  
    y->i = 32;  
    Console::WriteLine(y->i);  
    return 0;  
}  
```  
  
 **出力**  
  
```Output  
32  
```  
  
## <a name="see-also"></a>参照  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)