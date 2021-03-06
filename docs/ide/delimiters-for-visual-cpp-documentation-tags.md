---
title: "Visual C ドキュメント タグの区切り記号 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- XML documentation, delimiters
ms.assetid: debfbdd9-63fa-4c58-a18e-a4d203d241d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 134605f86ef8019d34f5246fd75abbbf94d40fbc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="delimiters-for-visual-c-documentation-tags"></a>Visual C++ ドキュメント タグの区切り記号
ドキュメント タグの使用には、区切り記号は、ドキュメント コメントの開始位置し、終了位置をコンパイラに示す必要があります。  
  
 XML ドキュメント タグでは、次の種類の区切り記号を使用できます。  
  
 `///`  
 これは、ドキュメントの例に示すおよび Visual C プロジェクト テンプレートで使用されるフォームです。  
  
 `/** */`  
 これらは、複数行の区切り記号です。  
  
 使用する場合に規則を書式設定の一部がある、`/** */`区切り記号。  
  
-   含む行の`/**`行の残りの部分が空白文字、行の場合は区切り記号がコメントとして扱われません。 最初の文字が空白の場合は、空白文字は無視され、行の残りの部分を処理します。 それ以外の場合、`/**` 区切り記号の後にある行のテキスト全体が、コメントの一部として処理されます。  
  
-   含む行の`*/`まで空白のみがある場合、区切り記号、`*/`区切り記号、その行は無視されます。 それ以外の場合、以下の箇条書きで説明するパターン一致規則に従って、その行の `*/` 区切り記号までのテキストがコメントの一部として処理されます。  
  
-   始まる 1 つ後の行の`/**`区切り記号、コンパイラは、省略可能な空白文字とアスタリスクで構成される各の行の先頭に、一般的なパターンを探します (`*`)、その後に省略可能な空白を追加します。 コンパイラでは、各行の先頭の文字の共通セットが検出されると後のすべての行のパターンは無視されます、`/**`までとを含む行を含む可能性のある、区切り記号、`*/`区切り記号。  
  
 以下に、いくつかの例を示します。  
  
-   次のコメントでは、`<summary>` で始まる行だけがコメントの一部として処理されます。 次の 2 つのタグ形式のコメントが生成されます。  
  
    ```  
    /**  
    <summary>text</summary>   
    */  
    /** <summary>text</summary> */  
    ```  
  
-   コンパイラのパターンを適用する"*"を 2 番目と 3 番目の行の先頭に無視します。  
  
    ```  
    /**  
     * <summary>  
     *  text </summary>*/  
    ```  
  
-   コンパイラが検出されないパターンこのコメントで、2 行目にアスタリスクがないためです。 そのため、すべてのテキスト、2 番目と 3 番目の行まで、`*/`コメントの一部として処理されます。  
  
    ```  
    /**  
     * <summary>  
       text </summary>*/  
    ```  
  
-   コンパイラが検出されないパターンこのコメントで 2 つの理由。 最初に、一定のアスタリスクの前にスペース数で始まる行はありません。 次に、5 行目がタブで始まっています。空白とタブは一致しません。 そのため、すべて行のテキストを 2 つ目まで、`*/`コメント部分として処理されます。  
  
    ```  
    /**  
      * <summary>  
      * text   
     *  text2  
       *  </summary>  
    */  
    ```  
  
## <a name="see-also"></a>参照  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)