---
title: "rename、_wrename | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- rename
- _wrename
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wrename
- _trename
- Rename
dev_langs:
- C++
helpviewer_keywords:
- trename function
- directories [C++], renaming
- renaming directories
- names [C++], changing file
- _trename function
- rename function
- wrename function
- files [C++], renaming
- _wrename function
- names [C++], changing directory
- renaming files
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 34da3f704f3350a9fbd8750c940cdc4e847cfb40
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="rename-wrename"></a>rename、_wrename
ファイルまたはディレクトリの名前を変更します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int rename(  
   const char *oldname,  
   const char *newname   
);  
int _wrename(  
   const wchar_t *oldname,  
   const wchar_t *newname   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *oldname*  
 古い名前へのポインター。  
  
 *newname*  
 新しい名前へのポインター。  
  
## <a name="return-value"></a>戻り値  
 名前が正常に変更された場合、これらの関数はそれぞれ 0 を返します。 エラーが発生した場合は 0 以外の値を返し、`errno` を次のいずれかの値に設定します。  
  
 `EACCES`  
 *newname* によって指定されたファイルまたはディレクトリが既に存在するか、(無効なパスのため) 作成できない、または *oldname* がディレクトリであり、*newname* によって異なるパスが指定されています。  
  
 `ENOENT`  
 *oldname* によって指定されたファイルまたはパスが見つかりません。  
  
 `EINVAL`  
 名前に無効な文字が含まれています。  
  
 その他の返される可能性のある戻り値については、「[_doserrno、_errno、syserrlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 **rename** 関数は、*oldname* によって指定されたファイルまたはディレクトリの名前を *newname* によって指定された名前に変更します。 古い名前は、既存のファイルまたはディレクトリのパスである必要があります。 新しい名前を既存のファイルまたはディレクトリのパスにすることはできません。 **rename** を使用して、*newname* 引数で別のパスを指定することにより、1 つのディレクトリまたはデバイスから別のディレクトリまたはデバイスにファイルを移動することができます。 ただし、**rename** を使用してディレクトリを移動することはできません。 ディレクトリの名前を変更することはできますが、移動はできません。  
  
 `_wrename` は **_rename** のワイド文字バージョンであり、`_wrename` の引数はワイド文字列です。 それ以外では、`_wrename` と **_rename** の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_trename`|**rename**|**rename**|`_wrename`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|**rename**|\<io.h> または \<stdio.h>|  
|`_wrename`|\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_renamer.c  
/* This program attempts to rename a file named  
 * CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation  
 * to succeed, a file named CRT_RENAMER.OBJ must exist and  
 * a file named CRT_RENAMER.JBO must not exist.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   int  result;  
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";  
  
   /* Attempt to rename file: */  
   result = rename( old, new );  
   if( result != 0 )  
      printf( "Could not rename '%s'\n", old );  
   else  
      printf( "File '%s' renamed to '%s'\n", old, new );  
}  
```  
  
## <a name="output"></a>出力  
  
```  
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'  
```  
  
## <a name="see-also"></a>参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)