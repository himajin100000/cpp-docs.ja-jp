---
title: "interior_ptr (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- stdcli::language::interior_ptr
- interior_ptr_cpp
- interior_ptr
dev_langs:
- C++
helpviewer_keywords:
- interior_ptr keyword [C++]
ms.assetid: 25160f74-569e-492d-9e3c-67ece7486baa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd3e79306cb97413a833e039b0b333cb85b8e56d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="interiorptr-ccli"></a>interior_ptr (C++/CLI)
*内部ポインター*オブジェクト自体ではなく、参照型の内部にポインターを宣言します。 内部ポインターは、参照ハンドル、値の型をボックス化された型のハンドル、マネージ型のメンバー、またはマネージ配列の要素を参照できます。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 (この言語機能にはランタイムに適用される特記事項がありません。)  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 (この言語機能には Windows ランタイムのみに適用される特記事項がありません。)  
  
### <a name="requirements"></a>必要条件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム  
 次の構文例では、内部ポインターを示します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
cli::interior_ptr<cv_qualifier type> var = &initializer;  
```  
  
### <a name="parameters"></a>パラメーター  
 *cv_qualifier*  
 **const**または`volatile`修飾子です。  
  
 *type*  
 型*初期化子*です。  
  
 *var*  
 名前、`interior_ptr`変数。  
  
 *initializer*  
 参照型、マネージ配列またはネイティブ ポインターに割り当てることができるその他のオブジェクトの要素のメンバー。  
  
### <a name="remarks"></a>コメント  
 ネイティブ ポインターはオブジェクトのインスタンスを移動、ガベージ コレクターからの結果、マネージ ヒープ上の場所の変更として項目を追跡するためにできません。 インスタンスを正しく参照へのポインターの順序で、ランタイムは、新しく位置指定のオブジェクトへのポインターを更新する必要があります。  
  
 `interior_ptr`ネイティブ ポインターの機能のスーパー セットを表します。  そのため、何もネイティブ ポインターに割り当てることができることができますに割り当てることも、`interior_ptr`です。  内部ポインターは、比較、ポインターの算術演算などのネイティブ ポインターとして同じ一連の操作を実行する許可します。  
  
 内部ポインターはスタックでのみ宣言できます。  クラスのメンバーとして内部ポインターを宣言することはできません。  
  
 内部ポインターはスタック上だけ残っているために、内部ポインターのアドレスを取得すると、アンマネージ ポインターが生成されます。  
  
 `interior_ptr`暗黙的な変換を持つ`bool`、条件付きステートメントで、使用できます。  
  
 ガベージ コレクトされたヒープに移動できないオブジェクトを指す内部ポインターを宣言する方法については、次を参照してください。 [pin_ptr](../windows/pin-ptr-cpp-cli.md)です。  
  
 `interior_ptr` は cli 名前空間に存在します。  参照してください[プラットフォーム、既定値、および cli 名前空間](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)詳細についてはします。  
  
 内部ポインターの詳細については、次を参照してください。  
  
-   [方法: 内部ポインターおよびマネージ配列を宣言および使用する (C++/CLI)](../windows/how-to-declare-and-use-interior-pointers-and-managed-arrays-cpp-cli.md)  
  
-   [方法: interior_ptr キーワードを含む値型を宣言する (C++/CLI)](../windows/how-to-declare-value-types-with-the-interior-ptr-keyword-cpp-cli.md)  
  
-   [方法: 内部ポインターとネイティブ ポインターを使用して関数をオーバーロードする (C++/CLI)](../windows/how-to-overload-functions-with-interior-pointers-and-native-pointers-cpp-cli.md)  
  
-   [方法: const キーワードを含む内部ポインターを宣言する (C++/CLI)](../windows/how-to-declare-interior-pointers-with-the-const-keyword-cpp-cli.md)  
  
### <a name="requirements"></a>必要条件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次の例では、宣言および内部ポインターを使用する参照型にする方法を示します。  
  
```cpp  
// interior_ptr.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyClass {  
public:  
   int data;  
};  
  
int main() {  
   MyClass ^ h_MyClass = gcnew MyClass;  
   h_MyClass->data = 1;  
   Console::WriteLine(h_MyClass->data);  
  
   interior_ptr<int> p = &(h_MyClass->data);  
   *p = 2;  
   Console::WriteLine(h_MyClass->data);  
  
   // alternatively  
   interior_ptr<MyClass ^> p2 = &h_MyClass;  
   (*p2)->data = 3;  
   Console::WriteLine((*p2)->data);  
}  
```  
  
 **出力**  
  
```Output  
1  
2  
3  
```  
  
## <a name="see-also"></a>参照  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)