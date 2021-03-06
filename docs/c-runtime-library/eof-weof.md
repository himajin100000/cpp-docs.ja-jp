---
title: "EOF、WEOF | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- EOF
dev_langs:
- C++
helpviewer_keywords:
- EOF function
- WEOF function
- end of file
ms.assetid: a7150563-cdae-4cdf-9798-ad509990e505
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1e9881d28f0f8f4a32c5bc049d4f9bac805124d9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="eof-weof"></a>EOF、WEOF
## <a name="syntax"></a>構文  
  
```  
  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>コメント  
 EOF は、ファイルの終わり (場合によっては、エラー) が検出された場合に I/O ルーチンによって返されます。  
  
 WEOF は、ワイド型ストリームの終端を示すために、またはエラー状態を報告するために使用される **wint_t** 型の戻り値です。  
  
## <a name="see-also"></a>参照  
 [putc、putwc](../c-runtime-library/reference/putc-putwc.md)   
 [ungetc、ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)   
 [scanf、_scanf_l、wscanf、_wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [fflush](../c-runtime-library/reference/fflush.md)   
 [fclose、_fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)   
 [_ungetch、_ungetwch、_ungetch_nolock、_ungetwch_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)   
 [_putch、_putwch](../c-runtime-library/reference/putch-putwch.md)   
 [isascii、__isascii、iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)