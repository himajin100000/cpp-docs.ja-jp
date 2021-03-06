---
title: _get_printf_count_output | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _get_printf_count_output
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_printf_count_output
- _get_printf_count_output
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 05184838f9ac68e697cc7ff326c33c266f865875
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="getprintfcountoutput"></a>_get_printf_count_output
[printf、_printf_l、wprintf、_wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) ファミリの関数で `%n` 形式がサポートされているかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```  
int _get_printf_count_output();  
```  
  
## <a name="return-value"></a>戻り値  
 `%n` がサポートされている場合は 0 以外の値、`%n` がサポートされていない場合は 0。  
  
## <a name="remarks"></a>コメント  
 `%n` がサポートされていない場合 (既定)、いずれかの `printf` 関数の書式文字列に `%n` が含まれていると、「[Parameter Validation](../../c-runtime-library/parameter-validation.md)」(パラメーターの検証) で説明されているように無効なパラメーター ハンドラーが呼び出されます。 場合`%n`サポートが有効になっている (を参照してください[_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md)) し、 `%n` 」の説明に従って動作[書式指定構文: printf 関数と wprintf 関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)です。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_get_printf_count_output`|\<stdio.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 例については「[_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md)」をご覧ください。  
  
## <a name="see-also"></a>参照  
[_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md)  
