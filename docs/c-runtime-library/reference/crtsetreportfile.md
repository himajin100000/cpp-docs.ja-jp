---
title: _CrtSetReportFile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtSetReportFile
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
- CrtSetReportFile
- _CrtSetReportFile
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a97e3f856dae60eeae9b96f3d5b422f8a262c68a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="crtsetreportfile"></a>_CrtSetReportFile
[_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) を使用して `_CRTDBG_MODE_FILE` を指定すると、メッセージ テキストを受け取るためのファイル ハンドルを指定できます。 `_CrtSetReportFile` は、[_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) によってテキストの出力先を指定するためにも使用されます (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
_HFILE _CrtSetReportFile(   
   int reportType,  
   _HFILE reportFile   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `reportType`  
 レポートの種類: `_CRT_WARN`、`_CRT_ERROR`、および `_CRT_ASSERT`。  
  
 `reportFile`  
 `reportType` の新しいレポート ファイル。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、`_CrtSetReportFile` は `reportType` で指定したレポートの種類に対して定義された前のレポート ファイルを返します。 `reportType` に無効な値が渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、この関数によって無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、 `errno` が `EINVAL` に設定され、関数から `_CRTDBG_HFILE_ERROR`が返されます。 詳しくは、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `_CrtSetReportFile` は [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 関数と一緒に使用して、`_CrtDbgReport` によって生成される特定のレポートの種類の送信先を定義するために使用されます。 特定のレポートの種類の `_CrtSetReportMode` レポート モードを割り当てるために `_CRTDBG_MODE_FILE` が呼び出された場合は、ターゲットとして使用する特定のファイルまたはストリームを定義するために `_CrtSetReportFile` を呼び出す必要があります。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtSetReportFile` の呼び出しは前処理で削除されます。  
  
 次の表は `reportFile` で使用できる選択肢の一覧と、結果となる `_CrtDbgReport` の動作を示しています。 これらのオプションは、Crtdbg.h でビット フラグとして定義されています。  
  
 `file handle`  
 メッセージの送信先となるファイルのハンドル。 ハンドルの有効性は検証されません。 ファイルのハンドルを開いたり閉じたりする必要があります。 例:  
  
```  
HANDLE hLogFile;  
hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,   
   FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,   
   FILE_ATTRIBUTE_NORMAL, NULL);  
_CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_WARN, hLogFile);  
  
_RPT0(_CRT_WARN,"file message\n");  
CloseHandle(hLogFile);  
```  
  
 `_CRTDBG_FILE_STDERR`  
 `stderr` にメッセージを書き込みます。これは次のようにリダイレクトできます。  
  
```  
freopen( "c:\\log2.txt", "w", stderr);  
_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);  
  
_RPT0(_CRT_ERROR,"1st message\n");  
```  
  
 `_CRTDBG_FILE_STDOUT`  
 `stdout` にメッセージを書き込みます。これはリダイレクトできます。  
  
 `_CRTDBG_REPORT_FILE`  
 現在のレポート モードを返します。  
  
 各レポートの種類によって使用されるレポート ファイルを個別に制御できます。 たとえば、`reportType` の `_CRT_ERROR` は `stderr` にレポートされるよう指定し、`reportType` の `_CRT_ASSERT` はユーザー定義ファイルのハンドルまたはストリームにレポートされるように指定することができます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_CrtSetReportFile`|\<crtdbg.h>|\<errno.h>|  
  
 コンソールは、ユニバーサル Windows プラットフォーム (UWP) アプリではサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル —`stdin`、 `stdout`、および`stderr`— C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
 **ライブラリ:** [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)