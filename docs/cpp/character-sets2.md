---
title: 文字の Sets2 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- Character sets
- basic source character set (C++)
- universal character names
- basic execution character set (C++)
ms.assetid: 379a2af6-6422-425f-8352-ef0bca6c0d74
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: db505809c1fbc2c49e116b9c2f850f6e14dfbdf6
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2018
---
# <a name="character-sets"></a>文字セット
C++ プログラムのテキストは、特定の文字エンコーディングを使用するソース ファイルに保存されます。 C++ 標準では、ソース ファイル用の基本ソース文字セットと、コンパイル済みファイル用の基本実行文字セットを規定しています。 Visual C++ では、ソース ファイルとコンパイル済みファイルに、ロケール固有の追加の文字セットを使用できます。  
  
## <a name="character-sets"></a>文字セット  
 C++ 標準では、ソース ファイルに使用できる *基本ソース文字セット* を規定しています。 このセットに含まれない文字を表す場合は、 *ユニバーサル文字名*を使用すると追加の文字を指定できます。 コンパイルが完了すると、 *基本実行文字セット* と *基本実行ワイド文字セット* によって、プログラムに表示できる文字と文字列を表すことができます。 Visual C++ の実装では、ソース コードとコンパイル済みコードに追加の文字を使用できます。  
  
### <a name="basic-source-character-set"></a>基本ソース文字セット  
 *基本ソース文字セット* は、96 文字で構成されています。ソース ファイルでは、この文字セットを使用できます。 この文字セットには、空白文字、水平タブ、垂直タブ、フォーム フィードおよび改行の制御文字と、このセットのグラフィック文字が含まれます。  
  
 `a b c d e f g h i j k l m n o p q r s t u v w x y z`  
  
 `A B C D E F G H I J K L M N O P Q R S T U V W X Y Z`  
  
 `0 1 2 3 4 5 6 7 8 9`  
  
 `_ { } [ ] # ( ) < > % : ; . ? * + - / ^ & | ~ ! = , \ " '`  
  
 **Microsoft 固有の仕様**  
  
 Visual C++ には、基本ソース文字セットのメンバーとして `$` 文字が含まれています。 さらに、Visual C++ では、ファイルのエンコーディングに基づいて、追加の文字セットをソース ファイルで使用できます。 既定では、Visual Studio は既定のコードページを使用して、ソース ファイルを保存します。 ロケール固有のコードページや Unicode コードページでソース コードを保存すると、Visual C++ では、そのコードページの任意の文字をソース ファイルで使用できるようになります。ただし、基本ソース文字セットで明示的に許可されていない制御コードは使用できません。 たとえば、日本語コードページを使用してファイルを保存すれば、コメントや識別子、文字列リテラルを日本語の文字で記述できます。 Visual C++ では、有効なマルチバイト文字または Unicode コード ポイントに変換できない文字シーケンスは使用できません。 コンパイラ オプションによっては、一部の文字が識別子に使用できなくなることがあります。 詳細については、「 [Identifiers](../cpp/identifiers-cpp.md)」を参照してください。  
  
 **Microsoft 固有の仕様はここまで**  
  
### <a name="universal-character-names"></a>ユニバーサル文字名  
 C++ プログラムでは、基本ソース文字セットで規定されている文字よりも多くの文字を使用できます。それらの文字は、 *ユニバーサル文字名*を使用して移植可能な方法で指定します。 ユニバーサル文字名は、Unicode コード ポイントを表す文字のシーケンスで構成されます。  これには 2 つの形式があります。 `\UNNNNNNNN` は、U+NNNNNNNN 形式の Unicode コード ポイントを表すために使用します。この NNNNNNNN は、8 桁の 16 進コード ポイント番号です。 4 桁の `\uNNNN` は、U+0000NNNN 形式の Unicode コード ポイントを表すために使用します。  
  
 ユニバーサル文字名は、識別子、文字列リテラルおよび文字リテラルに使用できます。 ユニバーサル文字名を使用して、0xD800 から 0xDFFF の範囲に含まれるサロゲート コード ポイントを表すことはできません。 その代わりに、目的とするコード ポイントを使用してください。コンパイラは、必要なサロゲートを自動的に生成します。 識別子に使用できるユニバーサル文字名には、その他の制限が適用されます。 詳細については、「 [Identifiers](../cpp/identifiers-cpp.md) 」および「 [String and Character Literals](../cpp/string-and-character-literals-cpp.md)」を参照してください。  
  
 **Microsoft 固有の仕様**  
  
 Visual C++ コンパイラの処理では、ユニバーサル文字名形式の文字とリテラル形式の文字は区別されません。 たとえば、次に示すように、ユニバーサル文字名を使用して宣言した識別子がリテラル形式で使用できます。  
  
```cpp  
auto \u30AD = 42; // \u30AD is 'キ'  
if (キ == 42) return true; // \u30AD and キ are the same to the compiler  
  
```  
  
 Windows クリップボードでの拡張文字の形式は、アプリケーションのロケール設定によって決まります。 こうした文字を別のアプリケーションから切り取って、コードに貼り付けると、予期しない文字のエンコーディングが発生することがあります。 これは、コードの外見には現れない解析エラーの発生につながります。 拡張文字を貼り付ける前に、ソース ファイルのエンコーディングを Unicode コードページに設定するようにしてください。 また、拡張文字の生成には、IME または文字コード表アプリを使用するようにしてください。  
  
 **Microsoft 固有の仕様はここまで**  
  
### <a name="basic-execution-character-set"></a>基本実行文字セット  
 *基本実行文字セット* および *基本実行ワイド文字セット* は、基本ソース文字セットに含まれるすべての文字と、アラート、バックスペース、復帰および Null 文字を表す制御文字で構成されます。   *実行文字セット* および *実行ワイド文字セット* は、基本セットのスーパセットです。 これらは、基本ソース文字セットには含まれていない、実装で定義されたソース文字を含んでいます。 実行文字セットには、ロケール固有の表現があります。