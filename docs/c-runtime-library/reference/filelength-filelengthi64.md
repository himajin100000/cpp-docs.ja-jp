---
title: "_filelength、_filelengthi64 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _filelengthi64
- _filelength
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
- _filelength
- _filelengthi64
- filelengthi64
dev_langs:
- C++
helpviewer_keywords:
- filelengthi64 function
- lengths, file
- filelength function
- _filelength function
- files [C++], length
- _filelengthi64 function
ms.assetid: 3ab83d5a-543c-4079-b9d9-0abfc7da0275
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bcf35d33958157a424bf78950c3b4cf23f33708e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="filelength-filelengthi64"></a>_filelength、_filelengthi64
ファイルの長さを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
long _filelength(   
   int fd   
);  
__int64 _filelengthi64(   
   int fd   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 ファイル記述子をターゲットにします。  
  
## <a name="return-value"></a>戻り値  
 `_filelength` と `_filelengthi64` のいずれも、`fd` に関連付けられているターゲット ファイルのファイルの長さ (バイト単位) を返します。 `fd` が無効なファイル記述子の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、この関数によって無効なパラメーター ハンドラーが呼び出されます。 どちらの関数がエラーを示す設定に-1 L を返しますの実行の継続が許可された場合`errno`に`EBADF`です。  
  
## <a name="requirements"></a>必要条件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`_filelength`|\<io.h>|  
|`_filelengthi64`|\<io.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 「[_chsize](../../c-runtime-library/reference/chsize.md)」の例を参照してください。  
  
## <a name="see-also"></a>参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_stat、_wstat 関数](../../c-runtime-library/reference/stat-functions.md)   
 [_stat、_wstat 関数](../../c-runtime-library/reference/stat-functions.md)