---
title: "_mbclen、mblen、_mblen_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mbclen
- mblen
- _mblen_l
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
- mblen
- ftclen
- _mbclen
- tclen
- _ftclen
- _tclen
- mbclen
dev_langs:
- C++
helpviewer_keywords:
- tclen function
- _mblen_l function
- _tclen function
- mblen_l function
- _mbclen function
- mbclen function
- mblen function
ms.assetid: d5eb92a0-b7a3-464a-aaf7-9890a8e3ed70
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 460de51d8f969f275ed392d293f90f517c168971
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="mbclen-mblen-mblenl"></a>_mbclen、mblen、_mblen_l
長さを取得し、マルチバイト文字の有効性を決定します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、次を参照してください。[ユニバーサル Windows プラットフォーム アプリでサポートされない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
size_t _mbclen(  
   const unsigned char *c   
);  
int mblen(  
   const char *mbstr,  
   size_t count   
);  
int _mblen_l(  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 マルチバイト文字。  
  
 `mbstr`  
 マルチバイト文字のバイト シーケンスのアドレス。  
  
 `count`  
 チェックするバイト数。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `_mbclen` はマルチバイト文字 `c` の長さが 1 バイトまたは 2 バイトであるかによって、1 または 2 を返します。 `_mbclen` には、エラーの戻り値はありません。 `mbstr` が `NULL` でない場合、`mblen` は、マルチバイト文字の長さをバイト単位で返します。 `mbstr` が `NULL` であるか、またはワイド文字の null 文字を指し示す場合には、`mblen` は 0 を返します。 場合、オブジェクトを`mbstr`へのポインターは、最初に有効なマルチバイト文字を形成しません`count`文字、 `mblen` -1 を返します。  
  
## <a name="remarks"></a>コメント  
 `_mbclen` 関数は、マルチバイト文字 `c` の長さをバイト単位で返します。 `c` への暗黙の呼び出しによって、`_ismbblead` がマルチバイト文字の先行バイトを指していないと判断された場合、`_mbclen` の結果は予測できません。  
  
 `mblen` は、`mbstr` が有効なマルチバイト文字の場合はその長さをバイト単位で返し、コード ページに関連付けられているマルチバイト文字の有効性を決定します。 `mblen` は、`count` に含まれる `mbstr` 以下で、`MB_CUR_MAX` を超えない数のバイトを調べます。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定に影響されます。詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。 `_l` サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tclen`|マクロまたはインライン関数にマップされます|`_mbclen`|マクロまたはインライン関数にマップされます|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_mbclen`|\<mbstring.h>|  
|`mblen`|\<stdlib.h>|  
|`_mblen_l`|\<stdlib.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_mblen.c  
/* illustrates the behavior of the mblen function  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    int      i;  
    char    *pmbc = (char *)malloc( sizeof( char ) );  
    wchar_t  wc   = L'a';  
  
    printf( "Convert wide character to multibyte character:\n" );  
    wctomb_s( &i, pmbc, sizeof(char), wc );  
    printf( "  Characters converted: %u\n", i );  
    printf( "  Multibyte character: %x\n\n", *pmbc );  
  
    i = mblen( pmbc, MB_CUR_MAX );  
    printf( "Length in bytes of multibyte character %x: %u\n", *pmbc, i );  
  
    pmbc = NULL;  
    i = mblen( pmbc, MB_CUR_MAX );  
    printf( "Length in bytes of NULL multibyte character %x: %u\n", pmbc, i );  
}  
```  
  
## <a name="output"></a>出力  
  
```  
Convert wide character to multibyte character:  
  Characters converted: 1  
  Multibyte character: 61  
  
Length in bytes of multibyte character 61: 1  
Length in bytes of NULL multibyte character 0: 0  
```  
  
## <a name="see-also"></a>参照  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbccpy、_mbccpy_l](../../c-runtime-library/reference/mbccpy-mbccpy-l.md)   
 [strlen、wcslen、_mbslen、_mbslen_l、_mbstrlen、_mbstrlen_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)