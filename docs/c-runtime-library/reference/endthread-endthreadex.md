---
title: "_endthread、_endthreadex | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _endthread
- _endthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _endthread
- endthreadex
- _endthreadex
- endthread
dev_langs:
- C++
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 794dc5c4bbaf9653c5b6bbb08ea3e0a60ca438c4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="endthread-endthreadex"></a>_endthread、_endthreadex
スレッドを終了します。 `_endthread` は、 `_beginthread` によって作成されたスレッドを終了し、  `_endthreadex` は、 `_beginthreadex`によって作成されたスレッドを終了します。  
  
## <a name="syntax"></a>構文  
  
```  
void _endthread( void );  
void _endthreadex(   
   unsigned retval   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `retval`  
 スレッド終了コード。  
  
## <a name="remarks"></a>コメント  
 `_endthread` または `_endthreadex` を明示的に呼び出してスレッドを終了できます。ただし、 `_endthread` または `_endthreadex` は、 `_beginthread` または `_beginthreadex`にパラメーターとして渡されたルーチンからスレッドが戻ると自動的に呼び出されます。 `endthread` または `_endthreadex` を呼び出してスレッドを終了すると、スレッドに割り当てられていたリソースを確実に解放できます。  
  
> [!NOTE]
>  Libcmt.lib にリンクする実行可能ファイルでは、Win32 の [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) API を呼び出さないでください。呼び出すと、割り当てられたリソースをランタイム システムで再利用することができなくなります。 `_endthread` と `_endthreadex` は、割り当てられているスレッド リソースを解放し、 `ExitThread`を呼び出します。  
  
 `_endthread` は、スレッド ハンドルを自動的に終了します (この動作は、Win32 `ExitThread` API とは異なります)。このため、`_beginthread` および `_endthread` を使用する場合は、Win32 [CloseHandle API](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) を呼び出してスレッド ハンドルを明示的に終了しないでください。  
  
 Win32 `ExitThread` API と同様、 `_endthreadex` はスレッド ハンドルを終了しません。 このため、`_beginthreadex` および `_endthreadex` を使用するときには、Win32 `CloseHandle` API を呼び出してスレッド ハンドルを終了する必要があります。  
  
> [!NOTE]
>  `_endthread` と `_endthreadex` により、スレッドで待機中の C++ デストラクターは呼び出されなくなります。  
  
## <a name="requirements"></a>必要条件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`_endthread`|\<process.h>|  
|`_endthreadex`|\<process.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md) のマルチスレッド バージョンのみ。  
  
## <a name="example"></a>例  
 [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md)の例を参照してください。  
  
## <a name="see-also"></a>参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [_beginthread、_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)