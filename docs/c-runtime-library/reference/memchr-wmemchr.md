---
title: "memchr、wmemchr | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- wmemchr
- memchr
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
apitype: DLLExport
f1_keywords:
- memchr
- wmemchr
dev_langs:
- C++
helpviewer_keywords:
- memchr function
- wmemchr function
ms.assetid: 5a348581-28f1-4256-8434-687245f7fc9f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d008c0dfaae7490dd23fdd5fe3206b0c5c1d76fc
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="memchr-wmemchr"></a>memchr、wmemchr
バッファー内の文字を検索します。  
  
## <a name="syntax"></a>構文  
  
```  
void *memchr(  
   const void *buf,  
   int c,  
   size_t count  
); // C only  
void *memchr(  
   void *buf,  
   int c,  
   size_t count  
); // C++ only  
const void *memchr(  
   const void *buf,  
   int c,  
   size_t count  
); // C++ only  
wchar_t *wmemchr(  
   const wchar_t * buf,   
   wchar_t c,  
   size_t count  
); // C only  
wchar_t *wmemchr(  
   wchar_t * buf,   
   wchar_t c,  
   size_t count  
); // C++ only  
const wchar_t *wmemchr(  
   const wchar_t * buf,   
   wchar_t c,  
   size_t count  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `buf`  
 バッファーへのポインター。  
  
 `c`  
 検索する文字。  
  
 `count`  
 確認する文字数。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は、`buf` 内の最初の `c` の位置へのポインターを返します。 それ以外の場合は `NULL` を返します。  
  
## <a name="remarks"></a>コメント  
 `memchr` と `wmemchr` は、`buf` の先頭 `count` バイトから `c` の最初の出現箇所を検索します。 `c` が見つかるか、または先頭 `count` バイトの確認が完了すると、検索が停止します。  
  
 C では、これらの関数は、最初の引数に `const` ポインターを受け取ります。 C++ では、2 つのオーバーロードを使用できます。 `const` へのポインターを受け取るオーバーロードでは、`const` へのポインターが返されます。非 `const` へのポインターを受け取るバージョンでは、非 `const` へのポインターが返されます。 マクロ _CRT_CONST_CORRECT_OVERLOADS が両方に定義されている、`const`と非-`const`これらの関数のバージョンを利用できます。 C++ でどちらの C++ のオーバーロードについても非 `const` の動作が求められる場合は、シンボル _CONST_RETURN を定義してください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`memchr`|\<memory.h> または \<string.h>|  
|`wmemchr`|\<wchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_memchr.c  
  
#include <memory.h>  
#include <stdio.h>  
  
int  ch = 'r';  
char str[] =    "lazy";  
char string[] = "The quick brown dog jumps over the lazy fox";  
char fmt1[] =   "         1         2         3         4         5";  
char fmt2[] =   "12345678901234567890123456789012345678901234567890";  
  
int main( void )  
{  
   char *pdest;  
   int result;  
   printf( "String to be searched:\n             %s\n", string );  
   printf( "             %s\n             %s\n\n", fmt1, fmt2 );  
  
   printf( "Search char: %c\n", ch );  
   pdest = memchr( string, ch, sizeof( string ) );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf( "Result:      %c found at position %d\n", ch, result );  
   else  
      printf( "Result:      %c not found\n" );  
}  
```  
  
## <a name="output"></a>出力  
  
```  
String to be searched:  
             The quick brown dog jumps over the lazy fox  
                      1         2         3         4         5  
             12345678901234567890123456789012345678901234567890  
  
Search char: r  
Result:      r found at position 12  
```  
  
## <a name="see-also"></a>参照  
 [バッファー操作](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memcmp、wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memcpy、wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [memset、wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strchr、wcschr、_mbschr、_mbschr_l](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)