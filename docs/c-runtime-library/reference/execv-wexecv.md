---
title: "_execv、_wexecv | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wexecv
- _execv
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _execv
- _wexecv
- wexecv
dev_langs:
- C++
helpviewer_keywords:
- _wexecv function
- _execv function
- wexecv function
- execv function
ms.assetid: 8dbaf7bc-9040-4316-a0c1-db7e866b52af
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a9520c8975d342b423bf61a1f5973a4bdabfcc37
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="execv-wexecv"></a>_execv、_wexecv
新しい子プロセスを読み込んで実行します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、次を参照してください。[ユニバーサル Windows プラットフォーム アプリでサポートされない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
intptr_t _execv(   
   const char *cmdname,  
   const char *const *argv   
);  
intptr_t _wexecv(   
   const wchar_t *cmdname,  
   const wchar_t *const *argv   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cmdname`  
 実行するファイルのパス。  
  
 `argv`  
 パラメーターへのポインターの配列。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、これらの関数が呼び出しプロセスに戻ることはありません。 戻り値-1 がいる場合、エラーを示す、`errno`グローバル変数を設定します。  
  
|`errno` の値|説明|  
|-------------------|-----------------|  
|`E2BIG`|引数と環境設定には、32 KB を超える領域が必要です。|  
|`EACCES`|指定されたファイルでロック違反または共有違反が発生しています。|  
|`EINVAL`|無効なパラメーター。|  
|`EMFILE`|開いているファイルの数が多すぎます (指定されたファイルは、実行可能ファイルであるかどうかを確認するために開く必要があります)。|  
|`ENOENT`|ファイルまたはパスが見つかりません。|  
|`ENOEXEC`|指定されたファイルが実行可能ファイルでないか、無効な実行可能ファイル形式です。|  
|`ENOMEM`|新しいプロセスを実行するのに十分なメモリがないか、使用できるメモリが破損しているか、または無効なブロックが存在します (呼び出しプロセスが正しく割り当てられていないことを示します)。|  
  
 リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 これらの各関数は新しいプロセスを読み込んで実行し、コマンド ライン引数へのポインターの配列を渡します。  
  
 `_execv` 関数は、パラメーターを検証します。 `cmdname` が null ポインターの場合、または `argv` が null ポインター、または空の配列へのポインターである場合、または配列に最初の引数として空の文字列が含まれている場合、`_execv` 関数は「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、-1 を返します。 プロセスは起動されません。  
  
## <a name="requirements"></a>必要条件  
  
|関数|必須ヘッダー|オプション ヘッダー|  
|--------------|---------------------|---------------------|  
|`_execv`|\<process.h>|\<errno.h>|  
|`_wexecv`|\<process.h> または \<wchar.h>|\<errno.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 「[_exec 関数、_wexec 関数](../../c-runtime-library/exec-wexec-functions.md)」の例を参照してください。  
  
## <a name="see-also"></a>参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [_exec 系関数と _wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit、_Exit、_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit、_onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn関数、_wspawn 関数](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system、_wsystem](../../c-runtime-library/reference/system-wsystem.md)