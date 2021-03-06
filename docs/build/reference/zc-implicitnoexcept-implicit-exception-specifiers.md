---
title: "/Zc:implicitNoexcept (暗黙の例外指定子) |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zc:implicitNoexcept
dev_langs:
- C++
helpviewer_keywords:
- /Zc:implicitNoexcept
- Zc:implicitNoexcept
- -Zc:implicitNoexcept
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 77308d262022f0cddbbb7008fe8277f7768afd68
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="zcimplicitnoexcept-implicit-exception-specifiers"></a>/Zc:implicitNoexcept (暗黙の例外指定子)

ときに、 **/Zc:implicitNoexcept**オプションを指定すると、コンパイラは暗黙的な付加[noexcept](../../cpp/noexcept-cpp.md)コンパイラ定義の特別なメンバー関数をユーザー定義のデストラクターを例外指定子とデアロケーターです。 既定では、 **/Zc:implicitNoexcept** ISO C 11 標準に準拠するように有効にします。 このオプションをオフにすると、ユーザー定義のデストラクターとデアロケーターおよびコンパイラ定義の特別なメンバー関数に対して暗黙的な `noexcept` が無効になります。

## <a name="syntax"></a>構文

> **/Zc:implicitNoexcept**[**-**]

## <a name="remarks"></a>コメント

**/Zc:implicitNoexcept** ISO C 11 標準のセクション 15.4 に従うようにコンパイラに指示します。 暗黙的に追加、`noexcept`各暗黙的に宣言または明示的に既定値にされた特殊なメンバー関数を例外指定子: 既定のコンス トラクターがコンス トラクター、移動コンス トラクター、デストラクター、コピー代入演算子をコピーまたは移動の代入演算子、および各ユーザー定義のデストラクターまたはデアロケーター関数。 ユーザー定義のデアロケーターには、暗黙的な `noexcept(true)` 例外指定子があります。 ユーザー定義のデストラクターでは、含まれているメンバー クラスまたは基底クラスに `noexcept(true)` ではないデストラクターがなければ、暗黙的な例外指定子は `noexcept(true)` です。 コンパイラにより生成された特別なメンバー関数では、この関数によって直接呼び出された任意の関数が実質的に `noexcept(false)` である場合、暗黙的な例外指定子は `noexcept(false)` です。 それ以外の場合、暗黙的な例外指定子は `noexcept(true)` です。

コンパイラは、明示的な `noexcept` や `throw` 指定子または `__declspec(nothrow)` 属性を使用して宣言された関数に対して暗黙的な例外指定子を生成しません。

既定では、 **/Zc:implicitNoexcept**を有効にします。 [寛容/-](permissive-standards-conformance.md)オプションには影響しません**/Zc:implicitNoexcept**です。

指定して、オプションが無効になっている場合**/zc: implicitnoexcept-**、コンパイラによって暗黙的な例外指定子は生成されません。 この動作は Visual Studio 2013 の場合と同じであり、例外指定子がないデストラクターとデアロケーターでは `throw` ステートメントを使用することができません。 既定とタイミング**/Zc:implicitNoexcept**を指定した場合、`throw`で暗黙的な関数の実行時にステートメントが検出された`noexcept(true)`指定子の直接の呼び出しになります`std::terminate`と例外ハンドラーに対する通常のアンワインド動作は保証されません。 このような状況を識別するには、コンパイラが生成されます[コンパイラの警告 (レベル 1) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md)です。 場合、`throw`は、意図的なことをお勧めする明示的な関数の宣言を変更する`noexcept(false)`指定子を使用せずに**/zc: implicitnoexcept-**です。

この例では、明示的な例外指定子を持たないユーザー定義のデストラクターの動作時に、 **/Zc:implicitNoexcept**オプションを設定するか、または無効になっています。 動作を示すを設定するを使用してコンパイル`cl /EHsc /W4 implicitNoexcept.cpp`です。 表示するには無効にしたときの動作を使用してコンパイル`cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp`です。

```cpp
// implicitNoexcept.cpp
// Compile by using: cl /EHsc /W4 implicitNoexcept.cpp
// Compile by using: cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp

#include <iostream>
#include <cstdlib>      // for std::exit, EXIT_FAILURE, EXIT_SUCCESS
#include <exception>    // for std::set_terminate

void my_terminate()
{
    std::cout << "Unexpected throw caused std::terminate" << std::endl;
    std::cout << "Exit returning EXIT_FAILURE" << std::endl;
    std::exit(EXIT_FAILURE);
}

struct A {
    // Explicit noexcept overrides implicit exception specification
    ~A() noexcept(false) {
        throw 1;
    }
};

struct B : public A {
    // Compiler-generated ~B() definition inherits noexcept(false)
    ~B() = default;
};

struct C {
    // By default, the compiler generates an implicit noexcept(true)
    // specifier for this user-defined destructor. To enable it to
    // throw an exception, use an explicit noexcept(false) specifier,
    // or compile by using /Zc:implicitNoexcept-
    ~C() {
        throw 1; // C4297, calls std::terminate() at run time
    }
};

struct D : public C {
    // This destructor gets the implicit specifier of its base.
    ~D() = default;
};

int main()
{
    std::set_terminate(my_terminate);

    try
    {
        {
            B b;
        }
    }
    catch (...)
    {
        // exception should reach here in all cases
        std::cout << "~B Exception caught" << std::endl;
    }
    try
    {
        {
            D d;
        }
    }
    catch (...)
    {
        // exception should not reach here if /Zc:implicitNoexcept
        std::cout << "~D Exception caught" << std::endl;
    }
    std::cout << "Exit returning EXIT_SUCCESS" << std::endl;
    return EXIT_SUCCESS;
}
```

既定の設定を使用して、コンパイル時に**/Zc:implicitNoexcept**サンプルには、次の出力が生成されます。

```Output
~B Exception caught
Unexpected throw caused std::terminate
Exit returning EXIT_FAILURE
```

設定を使用して、コンパイル時に**/zc: implicitnoexcept-**サンプルには、次の出力が生成されます。

```Output
~B Exception caught
~D Exception caught
Exit returning EXIT_SUCCESS
```

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを**/Zc:implicitNoexcept**または**/zc: implicitnoexcept-**を選択し**OK**です。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](../../build/reference/zc-conformance.md)<br/>
[noexcept](../../cpp/noexcept-cpp.md)<br/>
[例外の仕様 (スロー)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[terminate](../../standard-library/exception-functions.md#terminate)<br/>
