---
title: "#行ディレクティブ (C/C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 10/18/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '#line'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13760aa7c503339c16ed6418badc295170d2c938
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="line-directive-cc"></a>#line ディレクティブ (C/C++)

`#line` ディレクティブは、コンパイラの内部に格納された行番号およびファイル名を、指定された行数およびファイル名に変更するようにプリプロセッサに指示します。

## <a name="syntax"></a>構文

> **#line** *digit-sequence* ["*filename*"]

## <a name="remarks"></a>コメント

コンパイラは、行番号および省略可能なファイル名を使用して、コンパイル時に見つかったエラーを参照します。 通常、行番号は現在の入力行を参照し、ファイル名は現在の入力ファイルを参照します。 行番号は、各行が処理された後、インクリメントします。

*桁シーケンス*値は、任意の整数定数を指定できます。 マクロ置換はプリプロセス トークンで実行できますが、結果は正しい構文に評価される必要があります。 *Filename*文字の組み合わせにすることができ、二重引用符で囲む必要があります (**""**)。 場合*filename*は省略すると、前のファイル名は変更されません。

`#line` ディレクティブを記述して、ソース行番号とファイル名を変更できます。 トランスレーターは行番号とファイル名を使用して、定義済みマクロの値の決定を**&#95; &#95;です。ファイル &#95; #95**と**&#95; &#95;です。行 &#95; #95**. これらのマクロを使用して、説明的なエラー メッセージをプログラム テキストに挿入できます。 これらの定義済みマクロの詳細については、次を参照してください。[定義済みマクロ](../preprocessor/predefined-macros.md)です。

**&#95; &#95;です。ファイル &#95; #95**マクロは二重引用符で囲まれたファイル名で構成される文字列に展開されます (**""**)。

行番号とファイル名を変更すると、コンパイラでは以前の値が無視され、新しい値で処理が続行されます。 `#line` ディレクティブは、通常、プログラム ジェネレーターによって使用されます。これにより、エラー メッセージは、生成されたプログラムではなく、元のソース ファイルを参照します。

次の例を示しています`#line`と**&#95; &#95;です。行 &#95; #95**と**&#95; &#95;です。ファイル &#95; #95**マクロです。

このステートメントで内部的に格納された行番号は 151 に設定し、copy.c にファイル名を変更します。

```cpp
#line 151 "copy.c"
```

 この例では、マクロで`ASSERT`定義済みマクロを使用して**&#95; &#95;です。行 &#95; #95**と**&#95; &#95;です。ファイル &#95; #95**特定のアサーションが true でない場合は、ソース ファイルに関するエラー メッセージを印刷します。

```cpp
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>参照

[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)