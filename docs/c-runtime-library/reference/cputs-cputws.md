---
title: "_cputs、_cputws | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _cputws
- _cputs
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
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- cputws
- _cputs
- _cputws
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], writing
- _cputs function
- _cputws function
- putting strings to the console
- cputs function
- console, sending strings to
- cputws function
ms.assetid: ec418484-0f8d-43ec-8d8b-198a556c659e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a7878b552624e5edd476db138bab50e254a46558
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="cputs-cputws"></a>_cputs、_cputws
コンソールに文字列を書き込みます。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、次を参照してください。[ユニバーサル Windows プラットフォーム アプリでサポートされない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
int _cputs(   
   const char *str   
);  
int _cputws(  
   const wchar_t *str   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `str`  
 出力する文字列。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、`_cputs` は 0 を返します。 関数が失敗した場合は 0 以外の値を返します。  
  
## <a name="remarks"></a>コメント  
 `_cputs` 関数は、`str` によって指される null で終わる文字列をコンソールに直接書き込みます。 "復帰 - 改行" (CR-LF) の組み合わせは文字列に自動的に追加されません。  
  
 この関数は、そのパラメーターを検証します。 `str` が **NULL** の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から -1 が返されます。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|**_cputts**|`_cputs`|`_cputs`|`_cputws`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_cputs`|\<conio.h>|\<errno.h>|  
|`_cputws`|\<conio.h>|\<errno.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```C  
// crt_cputs.c  
// compile with: /c  
// This program first displays a string to the console.  
  
#include <conio.h>  
#include <errno.h>  
  
void print_to_console(char* buffer)  
{  
   int retval;  
   retval = _cputs( buffer );  
   if (retval)  
   {  
       if (errno == EINVAL)  
       {  
         _cputs( "Invalid buffer in print_to_console.\r\n");  
       }  
       else  
         _cputs( "Unexpected error in print_to_console.\r\n");  
   }  
}  
  
void wprint_to_console(wchar_t* wbuffer)  
{  
   int retval;  
   retval = _cputws( wbuffer );  
   if (retval)  
   {  
       if (errno == EINVAL)  
       {  
         _cputws( L"Invalid buffer in wprint_to_console.\r\n");  
       }  
       else  
         _cputws( L"Unexpected error in wprint_to_console.\r\n");  
   }  
}  
  
int main()  
{  
  
   // String to print at console.   
   // Notice the \r (return) character.   
   char* buffer = "Hello world (courtesy of _cputs)!\r\n";  
   wchar_t *wbuffer = L"Hello world (courtesy of _cputws)!\r\n";  
   print_to_console(buffer);  
   wprint_to_console( wbuffer );  
}  
```  
  
```Output  
Hello world (courtesy of _cputs)!  
Hello world (courtesy of _cputws)!  
```  
  
## <a name="see-also"></a>参照  
 [コンソール入出力とポート入出力](../../c-runtime-library/console-and-port-i-o.md)   
 [_putch、_putwch](../../c-runtime-library/reference/putch-putwch.md)