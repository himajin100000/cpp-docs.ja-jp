---
title: "_strnset、_strnset_l、_wcsnset、_wcsnset_l、_mbsnset、_mbsnset_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mbsnset
- _strnset
- _mbsnset_l
- _wcsnset_l
- _wcsnset
- _strnset_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcsncset_l
- mbsnset_l
- _tcsnset_l
- _fstrnset
- _wcsnset_l
- _ftcsnset
- wcsnset_l
- _mbsnset_l
- _strnset
- _tcsnset
- _strnset_l
- mbsnset
- strnset_l
- _mbsnset
- _wcsnset
- _tcsncset
dev_langs:
- C++
helpviewer_keywords:
- _wcsnset function
- strnset_l function
- tcsnset function
- tcsncset function
- characters [C++], initializing to formats
- mbsnset function
- _tcsnset_l function
- _mbsnset function
- _strnset function
- _tcsncset_l function
- mbsnset_l function
- _tcsnset function
- initializing characters
- _tcsncset function
- ftcsnset function
- wcsnset_l function
- _ftcsnset function
- _wcsnset_l function
- _fstrnset function
- _mbsnset_l function
- _strnset_l function
- fstrnset function
- strings [C++], initializing
- tcsnset_l function
ms.assetid: 3f306489-5763-48e5-b939-aefee7c94ef5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3dc658ef152eb6065f9b0a310468a6880d87ead5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="strnset-strnsetl-wcsnset-wcsnsetl-mbsnset-mbsnsetl"></a>_strnset、_strnset_l、_wcsnset、_wcsnset_l、_mbsnset、_mbsnset_l
文字列の文字を所定の書式に初期化します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[_strnset_s、_strnset_s_l、_wcsnset_s、_wcsnset_s_l、_mbsnset_s、_mbsnset_s_l](../../c-runtime-library/reference/strnset-s-strnset-s-l-wcsnset-s-wcsnset-s-l-mbsnset-s-mbsnset-s-l.md)」をご覧ください。  
  
> [!IMPORTANT]
>  `_mbsnset` および `_mbsnset_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、次を参照してください。[ユニバーサル Windows プラットフォーム アプリでサポートされない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
char *_strnset(  
   char *str,  
   int c,  
   size_t count   
);  
char *_strnset_l(  
   char *str,  
   int c,  
   size_t count,  
   locale_t locale  
);  
wchar_t *_wcsnset(  
   wchar_t *str,  
   wchar_t c,  
   size_t count   
);  
wchar_t *_wcsnset_l(  
   wchar_t *str,  
   wchar_t c,  
   size_t count,  
   _locale_t locale  
);  
unsigned char *_mbsnset(  
   unsigned char *str,  
   unsigned int c,  
   size_t count   
);  
unsigned char *_mbsnset_l(  
   unsigned char *str,  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `str`  
 変更対象の文字列。  
  
 `c`  
 文字設定。  
  
 `count`  
 設定する文字数。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 変更された文字列へのポインターを返します。  
  
## <a name="remarks"></a>コメント  
 `_strnset`関数は、`count` の先頭の最大 `str` 文字を `c` に設定します (`char` に変換)。 `count` が `str` の長さを超えると、その `str` の長さが `count` の代わりに使用されます。  
  
 `_wcsnset` 関数と `_mbsnset` 関数は、`_strnset` 関数のワイド文字バージョンとマルチバイト文字バージョンです。 `_wcsnset` 関数の文字列引数と戻り値はワイド文字列で、`_mbsnset` 関数の文字列引数と戻り値はマルチバイト文字列です。 それ以外では、これらの関数の動作は同じです。  
  
 `_mbsnset` はパラメーターを検証します。`str` が Null ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`_mbsnset`は NULL を返し、`errno`を `EINVAL` に設定します。 `_strnset` および `_wcsnset` は、パラメーターを検証しません。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定に影響されます。詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。 `_l` サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsnset`|`_strnset`|`_mbsnbset`|`_wcsnset`|  
|`_tcsnset_l`|`_strnset_l`|`_mbsnbset_l`|`_wcsnset_l`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_strnset`|\<string.h>|  
|`_strnset_l`|\<tchar.h>|  
|`_wcsnset`|\<string.h> または \<wchar.h>|  
|`_wcsnset_l`|\<tchar.h>|  
|`_mbsnset`, `_mbsnset_l`|\<mbstring.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_strnset.c  
// compile with: /W3  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[15] = "This is a test";  
   /* Set not more than 4 characters of string to be *'s */  
   printf( "Before: %s\n", string );  
   _strnset( string, '*', 4 ); // C4996  
   // Note: _strnset is deprecated; consider using _strnset_s  
   printf( "After:  %s\n", string );  
}  
```  
  
```Output  
Before: This is a test  
After:  **** is a test  
```  
  
## <a name="see-also"></a>参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcat、wcscat、_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp、wcscmp、_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy、wcscpy、_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [_strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)