---
title: "_sopen、_wsopen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _sopen
- _wsopen
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
- _wsopen
- wsopen
- _sopen
- _tsopen
dev_langs:
- C++
helpviewer_keywords:
- sopen function
- sharing files
- opening files, for sharing
- _sopen function
- wsopen function
- files [C++], opening
- files [C++], sharing
- _wsopen function
ms.assetid: a9d4cccf-06e9-414d-96fa-453fca88cc1f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6429eefe8c79337086fb8ec94215f171ae4b0bb
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="sopen-wsopen"></a>_sopen、_wsopen
共有用にファイルを開きます。 これらの関数のセキュリティを強化したバージョンを使用できます。「[_sopen_s、_wsopen_s (_sopen_s、_wsopen_s)](../../c-runtime-library/reference/sopen-s-wsopen-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
int _sopen(  
   const char *filename,  
   int oflag,  
   int shflag [,  
   int pmode ]   
);  
int _wsopen(  
   const wchar_t *filename,  
   int oflag,  
   int shflag [,  
   int pmode ]   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `filename`  
 ファイル名。  
  
 `oflag`  
 許可される操作の種類。  
  
 `shflag`  
 許可される共有の種類。  
  
 `pmode`  
 アクセス許可の設定。  
  
## <a name="return-value"></a>戻り値  
 これらの各関数は、開かれたファイルのファイル記述子を返します。  
  
 `filename` または `oflag` が `NULL` ポインターの場合や、`oflag` または `shflag` が有効な値の範囲内にない場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は -1 を返し、`errno` を次のいずれかの値に設定します。  
  
 `EACCES`  
 指定されたパスがディレクトリであるか、またはファイルが読み取り専用ですが、書き込み用に開く操作が試行されました。  
  
 `EEXIST`  
 `_O_CREAT` および `_O_EXCL` フラグが指定されましたが、`filename` が既に存在します。  
  
 `EINVAL`  
 `oflag` または `shflag` 引数が無効です。  
  
 `EMFILE`  
 ファイル記述子をこれ以上使用できません。  
  
 `ENOENT`  
 ファイルまたはパスが見つかりません。  
  
 リターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_sopen` 関数は、`filename` で指定されたファイルを開き、`oflag` および `shflag` による定義に従って、共有読み取りまたは書き込み用にファイルを準備します。 `_wsopen` 関数は、`_sopen` 関数のワイド文字バージョンです。`filename` 関数の引数 `_wsopen` は、ワイド文字列です。 それ以外では、`_wsopen` と `_sopen` の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tsopen`|`_sopen`|`_sopen`|`_wsopen`|  
  
 整数式 `oflag` は、\<fcntl.h> で定義されている次のマニフェスト定数の 1 つまたは複数を組み合わせることによって構成されます。 引数 `oflag` が複数の定数で構成される場合、これらはビットごとの OR 演算子を使用して組み合わされます ( `|` )。  
  
 `_O_APPEND`  
 書き込み操作の前に、毎回、ファイル ポインターをファイルの末尾に位置変更します。  
  
 `_O_BINARY`  
 ファイルをバイナリ (無変換) モードで開きます。 (バイナリ モードの詳細については、「[fopen](../../c-runtime-library/reference/fopen-wfopen.md)」を参照してください)。  
  
 `_O_CREAT`  
 ファイルを作成し、書き込み用に開きます。 `filename` で指定されたファイルが存在する場合は無効です。 
          `pmode` が指定された場合は `_O_CREAT` 引数が必要です。  
  
 `_O_CREAT | _O_SHORT_LIVED`  
 ファイルを一時ファイルとして作成し、可能な場合は、ディスクにフラッシュしません。 `pmode` が指定された場合は `_O_CREAT` 引数が必要です。  
  
 `_O_CREAT | _O_TEMPORARY`  
 ファイルを一時ファイルとして作成します。最後のファイル記述子が閉じられると、ファイルは削除されます。 `pmode` が指定された場合は `_O_CREAT` 引数が必要です。  
  
 `_O_CREAT | _O_EXCL`  
 
          `filename` で指定されたファイルが存在する場合、エラー値を返します。 `_O_CREAT` と共に使用された場合にのみ適用されます。  
  
 `_O_NOINHERIT`  
 共有ファイル記述子の作成を禁止します。  
  
 `_O_RANDOM`  
 主にディスクからのランダム アクセスを指定します。  
  
 `_O_RDONLY`  
 読み取り専用でファイルを開きます。 `_O_RDWR` または `_O_WRONLY` と共に指定することはできません。  
  
 `_O_RDWR`  
 読み取りと書き込みの両方用にファイルを開きます。 `_O_RDONLY` または `_O_WRONLY` と共に指定することはできません。  
  
 `_O_SEQUENTIAL`  
 主にディスクからの順次アクセスを指定します。  
  
 `_O_TEXT`  
 ファイルをテキスト (変換) モードで開きます。 (詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」および「[fopen](../../c-runtime-library/reference/fopen-wfopen.md)」を参照してください。)  
  
 `_O_TRUNC`  
 ファイルを開き、長さゼロに切り詰めます。ファイルに書き込みアクセス許可が必要です。 `_O_RDONLY` と共に指定することはできません。 `_O_TRUNC` を `_O_CREAT` と共に使用すると、既存のファイルが開かれるか、新しいファイルが作成されます。  
  
> [!NOTE]
>  
          `_O_TRUNC` フラグによって、指定したファイルの内容は破棄されます。  
  
 `_O_WRONLY`  
 書き込み専用でファイルを開きます。 
          `_O_RDONLY` または `_O_RDWR` と共に指定することはできません。  
  
 `_O_U16TEXT`  
 Unicode UTF-16 モードでファイルを開きます。  
  
 `_O_U8TEXT`  
 Unicode UTF-8 モードでファイルを開きます。  
  
 `_O_WTEXT`  
 Unicode モードでファイルを開きます。  
  
 ファイル アクセス モードを指定するには、`_O_RDONLY`、`_O_RDWR`、または `_O_WRONLY` を指定する必要があります。 アクセス モードに既定値はありません。  
  
 `_O_WTEXT`、`_O_U8TEXT`、または `_O_U16TEXT` を使用してファイルが Unicode モードで開かれると、Input 関数によって、ファイルから読み取られたデータは `wchar_t` 型として格納された UTF-16 データに変換されます。 Unicode モードで開かれたファイルに書き込む関数は、`wchar_t` 型として格納された UTF-16 データがバッファーに含まれていると想定します。 ファイルが UTF-8 としてエンコードされている場合、UTF-16 データは書き込まれるときに UTF-8 に変換され、ファイルの UTF-8 でエンコードされた内容は読み取られるときに UTF-16 に変換されます。 Unicode モードで奇数バイトの読み取りまたは書き込みを試みると、パラメーター検証エラーが発生します。 UTF-8 としてプログラムに格納されたデータを読み取るか書き込む場合は、Unicode モードではなくテキストまたはバイナリ ファイル モードを使用します。 必要なエンコード変換は各自が行う必要があります。  
  
 `_sopen` は、`_O_WRONLY | _O_APPEND` (追加モード) および `_O_WTEXT`、`_O_U16TEXT`、または `_O_U8TEXT` を使用して呼び出された場合、最初に読み取りおよび書き込み用にファイルを開き、BOM を読み取り、次に書き込み専用で再度開こうとします。 読み取りおよび書き込み用にファイルを開くのに失敗した場合、書き込み専用でファイルを開き、Unicode モード設定の既定値を使用します。  
  
 引数 `shflag` は、\<share.h> で定義されている次のマニフェスト定数のいずれかで構成される定数式です。  
  
 `_SH_DENYRW`  
 ファイルへの読み取りおよび書き込みアクセスを拒否します。  
  
 `_SH_DENYWR`  
 ファイルへの書き込みアクセスを拒否します。  
  
 `_SH_DENYRD`  
 ファイルへの読み取りアクセスを拒否します。  
  
 `_SH_DENYNO`  
 読み取りおよび書き込みアクセスを許可します。  
  
 `pmode` が指定された場合にのみ `_O_CREAT` 引数が必要です。 ファイルが存在しない場合、`pmode` によってファイルのアクセス許可の設定が指定されます。これは、新しいファイルが最初に閉じられたときに設定されます。 それ以外の場合は、`pmode` は無視されます。 `pmode` は、\<sys\stat.h> で定義されているマニフェスト定数 `_S_IWRITE` と `_S_IREAD` のいずれか、または両方が含まれた整数式です。 両方の定数が指定されると、これらはビットごとの OR 演算子を使用して組み合わされます。 
          `pmode` の意味は次のとおりです。  
  
 `_S_IWRITE`  
 書き込みが許可されます。  
  
 `_S_IREAD`  
 読み取りが許可されます。  
  
 `_S_IREAD | _S_IWRITE`  
 読み取りと書き込みが許可されます。  
  
 書き込みアクセス許可が与えられない場合、ファイルは読み取り専用になります。 Windows オペレーティング システムでは、すべてのファイルは読み取り可能です。書き込み専用のアクセス許可を与えることはできません。 したがって、`_S_IWRITE` モードと `_S_IREAD | _S_IWRITE` モードは等価です。  
  
 `_sopen` では、アクセス許可が設定される前に、現在のファイル アクセス許可マスクが `pmode` に適用されます。 (「[_umask](../../c-runtime-library/reference/umask.md)」を参照。)  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_sopen`|\<io.h>|\<fcntl.h>、\<sys\types.h>、\<sys\stat.h>、\<share.h>|  
|`_wsopen`|\<io.h> または \<wchar.h>|\<fcntl.h>、\<sys\types.h>、\<sys\stat.h>、\<share.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 「[_locking](../../c-runtime-library/reference/locking.md)」の例をご覧ください。  
  
## <a name="see-also"></a>参照  
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen、_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_fsopen、_wfsopen](../../c-runtime-library/reference/fsopen-wfsopen.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)