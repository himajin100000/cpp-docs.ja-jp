---
title: "TCHAR.H データ型の _MBCS 定義下での使用 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- TCHAR.H data types
- MBCS data type
- _MBCS data type
ms.assetid: 48f471e7-9d2b-4a39-b841-16a0e15c0a18
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 05f2a5ae3ccf2ec8b9d9c1766bd5b02ed43dfbf7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-tcharh-data-types-with-mbcs"></a>TCHAR.H データ型の _MBCS 定義下での使用
**Microsoft 固有の仕様**  
  
 汎用テキスト ルーチンのマッピングの表に示すように (「[汎用テキスト マップ](../c-runtime-library/generic-text-mappings.md)」をご覧ください)、マニフェスト定数の `_MBCS` が定義されていると、指定した汎用テキスト ルーチンは次のようなルーチンのいずれかにマップされます。  
  
-   マルチバイト、文字、文字列を適切に処理する SBCS ルーチン。 この場合、文字列引数は `char*` 型であることを想定しています。 たとえば、`_tprintf` は `printf` にマップされ、`printf` への文字列引数は `char*` 型になります。 文字列型として汎用テキストのデータ型である `_TCHAR` を使用する場合、`_TCHAR*` は `char*` にマップされるため `printf` の仮パラメーターと実パラメーターの型は一致します。  
  
-   MBCS 固有ルーチン。 この場合、文字列引数は `unsigned char*` 型であることを想定しています。 たとえば、`_tcsrev` は、`unsigned char*` 型の文字列を必要とし、それを返す `_mbsrev` にマップされます。 上記と同じように、文字列型として汎用テキストのデータ型である `_TCHAR` を使用する場合、`_TCHAR` が `char` にマップされるため、今度は型が競合する可能性があります。  
  
 この型の競合 (および C コンパイラの警告または C++ コンパイラのエラーという結果) を回避するためには、次のような 3 つの解決方法があります。  
  
-   既定の動作を使用します。 次の例のように、TCHAR.H はランタイム ライブラリのルーチンに対して汎用テキスト ルーチンのプロトタイプを提供します。  
  
    ```  
    char *_tcsrev(char *);  
    ```  
  
     既定では、`_tcsrev` のプロトタイプは LIBC.LIB のサンクを介して `_mbsrev` にマップされます。 これにより、`_mbsrev` 受信パラメーターと `_TCHAR *` (`char *` など) から `unsigned char *` に送信される戻り値の型が変更されます。 この方法なら `_TCHAR` を使用するときに確実に型が一致しますが、関数呼び出しのオーバーヘッドにより比較的低速になります。  
  
-   コードに次のプリプロセッサ ステートメントを組み込むことにより、関数のインライン展開を使用します。  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     この方法では、TCHAR.H で提供されるインライン関数サンクにより、汎用テキスト ルーチンが直接、適切な MBCS ルーチンにマップされます。 どのようにマップされるかについては、例として TCHAR.H から抜粋した次のコードをご覧ください。  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     インライン展開を使用できる場合は、この方法が最適な解決法になります。確実に型が一致し、追加の時間コストが発生しないからです。  
  
-   コードに次のプリプロセッサ ステートメントを組み込むことにより、"直接マッピング" を使用します。  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     この方法は、既定の動作を使用したくない場合、またはインライン展開を使用できない場合の代替手段であり、高速です。 この方法では、TCHAR.H から抜粋した次の例のように、汎用テキスト ルーチンがマクロによって直接、MBCS バージョンのルーチンにマップされます。  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
 この方法を採用する場合は、文字列の引数と文字列の戻り値に適切なデータ型を使用するように注意する必要があります。 適切に型を一致させるために型キャストを使用できます。または、汎用テキストのデータ型である `_TXCHAR` を使用できます。 `_TXCHAR` は SBCS コードでは `char` 型にマップされますが、MBCS コードでは `unsigned char` 型にマップされます。 汎用テキストのマクロの詳細については、「[汎用テキスト マップ](../c-runtime-library/generic-text-mappings.md)」をご覧ください。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [国際化](../c-runtime-library/internationalization.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)