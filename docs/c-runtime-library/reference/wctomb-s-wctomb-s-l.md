---
title: "wctomb_s、_wctomb_s_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wctomb_s_l
- wctomb_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wctomb_s
- _wctomb_s_l
dev_langs:
- C++
helpviewer_keywords:
- wctomb_s function
- wctomb_s_l function
- string conversion, wide characters
- wide characters, converting
- _wctomb_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3025340d4af81f20fd086d07058ac820828dda75
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="wctombs-wctombsl"></a>wctomb_s、_wctomb_s_l
ワイド文字を対応するマルチバイト文字に変換します。 「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [wctomb、_wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t wctomb_s(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar   
);  
errno_t _wctomb_s_l(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `pRetValue`  
 バイト数、または結果を示すコード。  
  
 [出力] `mbchar`  
 マルチバイト文字のアドレス。  
  
 [入力] `sizeInBytes`  
 バッファー `mbchar` のサイズ。  
  
 [入力] `wchar`  
 ワイド文字。  
  
 [入力] `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
 エラー条件  
  
|`mbchar`|`sizeInBytes`|戻り値|`pRetValue`|  
|--------------|-------------------|------------------|-----------------|  
|`NULL`|>0|`EINVAL`|変更されない|  
|任意|>`INT_MAX`|`EINVAL`|変更されない|  
|任意|小さすぎる|`EINVAL`|変更されない|  
  
 上記のいずれかのエラー条件が発生すると、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラ―が呼び出されます。 実行の継続が許可された場合、`wctomb` は `EINVAL` を返し、`errno` を `EINVAL` に設定します。  
  
## <a name="remarks"></a>コメント  
 `wctomb_s` 関数はその `wchar` 引数を対応するマルチバイト文字に変換し、結果を `mbchar` に格納します。 任意のプログラムの任意のポイントからこの関数を呼び出すことができます。  
  
 `wctomb_s` がワイド文字をマルチバイト文字に変換する場合、ワイド文字のバイト数 (常に `MB_CUR_MAX` 以内) を `pRetValue` によって示される整数に与えます。 `wchar` がワイド文字の null 文字 (L'\0') である場合、`wctomb_s` は 1 で `pRetValue` を塗りつぶします。 ターゲット ポインター `mbchar` が NULL の場合、`wctomb_s` は `pRetValue` に 0 を格納します。 現在のロケールで変換が不可能な場合`wctomb_s`に-1 を配置`pRetValue`です。  
  
 `wctomb_s` は、ロケールに依存する情報に現在のロケールを使用します。`_wctomb_s_l` は、渡されたロケールを代わりに使用することを除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`wctomb_s`|\<stdlib.h>|  
|`_wctomb_s_l`|\<stdlib.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 このプログラムは、`wctomb` 関数の動作を示しています。  
  
```  
// crt_wctomb_s.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    int i;  
    wchar_t wc = L'a';  
    char *pmb = (char *)malloc( MB_CUR_MAX );  
  
    printf_s( "Convert a wide character:\n" );  
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );  
    printf_s( "   Characters converted: %u\n", i );  
    printf_s( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
```Output  
Convert a wide character:  
   Characters converted: 1  
   Multibyte character: a  
```  
  
## <a name="see-also"></a>参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [_mbclen、mblen、_mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs、_mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs、_wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)