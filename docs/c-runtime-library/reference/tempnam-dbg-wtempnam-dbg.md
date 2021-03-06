---
title: "_tempnam_dbg、_wtempnam_dbg | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wtempnam_dbg
- _tempnam_dbg
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
- wtempnam_dbg
- tempnam_dbg
- _tempnam_dbg
- _wtempnam_dbg
dev_langs:
- C++
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7fc8ef1427937ce4f263c81c55100045b30d24a3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="tempnamdbg-wtempnamdbg"></a>_tempnam_dbg、_wtempnam_dbg
`malloc, _malloc_dbg` デバッグ バージョンを使用する [_tempnam、_wtempnam、tmpnam、_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) の関数バージョン。  
  
## <a name="syntax"></a>構文  
  
```  
char *_tempnam_dbg(  
   const char *dir,  
   const char *prefix,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wtempnam_dbg(  
   const wchar_t *dir,  
   const wchar_t *prefix,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dir`  
 TMP 環境変数がない場合、または TMP が有効なディレクトリではない場合にファイル名で使用されるパス。  
  
 `prefix`  
 `_tempnam` によって返された名前の前に付けられる文字列。  
  
 `blockType`  
 要求するメモリ ブロックの種類。`_CLIENT_BLOCK` または `_NORMAL_BLOCK`。  
  
 `filename`  
 割り当て操作を要求したソース ファイル名へのポインターまたは `NULL`。  
  
 `linenumber`  
 割り当て操作が要求されたソース ファイル内の行番号または `NULL`。  
  
## <a name="return-value"></a>戻り値  
 各関数は、生成された名前へのポインター、または失敗した場合は `NULL` を返します。 TMP 環境変数および `dir` パラメーターに無効なディレクトリ名が指定されている場合は、失敗する可能性があります。  
  
> [!NOTE]
>  `free` および `free_dbg` によって割り当てられたポインターに対して、`_tempnam_dbg` (または `_wtempnam_dbg`) を呼び出す必要があります。  
  
## <a name="remarks"></a>コメント  
 `_tempnam_dbg`と`_wtempnam_dbg`関数と同じ`_tempnam`と`_wtempnam`する点を除いて、`_DEBUG`が定義されている場合、これらの関数でのデバッグ バージョンを使用`malloc`と`_malloc_dbg`メモリを割り当てる場合`NULL`は最初のパラメーターとして渡されます。 詳細については、「[_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)」をご覧ください。  
  
 多くの場合、これらの関数を明示的に呼び出す必要はありません。 代わりに、フラグ `_CRTDBG_MAP_ALLOC` を定義することができます。 `_CRTDBG_MAP_ALLOC` が定義されている場合、`_tempnam` および `_wtempnam` の呼び出しはそれぞれ `_tempnam_dbg` および `_wtempnam_dbg` にマップし直され、`blockType` が `_NORMAL_BLOCK` に設定されます。 そのため、ヒープ ブロックを `_CLIENT_BLOCK` としてマークする場合以外は、これらの関数を明示的に呼び出す必要はありません。 詳細については、[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)に関する記事をご覧ください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttempnam_dbg`|`_tempnam_dbg`|`_tempnam_dbg`|`_wtempnam_dbg`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_tempnam_dbg`, `_wtempnam_dbg`|\<crtdbg.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
 [_tempnam、_wtempnam、tmpnam、_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)