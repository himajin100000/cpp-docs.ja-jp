---
title: "_splitpath、_wsplitpath | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wsplitpath
- _splitpath
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
- wsplitpath
- _splitpath
- splitpath
- _wsplitpath
- _tsplitpath
dev_langs:
- C++
helpviewer_keywords:
- _splitpath function
- pathnames
- wsplitpath function
- splitpath function
- _wsplitpath function
- tsplitpath function
- path names
- _tsplitpath function
ms.assetid: 32bd76b5-1385-4ee8-a64c-abcb541cd2e4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 75a44cc1bf0bdd48a01e6bd2da58367451486049
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="splitpath-wsplitpath"></a>_splitpath、_wsplitpath
パス名をコンポーネントに分割します。 これらの関数のセキュリティを強化したバージョンについては、「[_splitpath_s、_wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
void _splitpath(  
   const char *path,  
   char *drive,  
   char *dir,  
   char *fname,  
   char *ext   
);  
void _wsplitpath(  
   const wchar_t *path,  
   wchar_t *drive,  
   wchar_t *dir,  
   wchar_t *fname,  
   wchar_t *ext   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `path`  
 完全パス。  
  
 `drive`  
 ドライブ文字、その後にコロン (`:`)。 ドライブ文字が不要な場合は、このパラメーターに `NULL` を渡します。  
  
 `dir`  
 末尾のスラッシュを含む、ディレクトリ パス。 スラッシュ (`/`)、バックスラッシュ (`\`)、または両方を使用できます。 ディレクトリ パスが不要な場合は、このパラメーターに `NULL` を渡します。  
  
 `fname`  
 基本ファイル名 (拡張子なし)。 ファイル名が不要な場合は、このパラメーターに `NULL` を渡します。  
  
 `ext`  
 先頭のピリオド (`.`) を含む、ファイル名の拡張子。 ファイル名の拡張子が不要な場合は、このパラメーターに `NULL` を渡します。  
  
## <a name="remarks"></a>コメント  
 `_splitpath` 関数は、パスを 4 つのコンポーネントに分割します。 `_splitpath` は、マルチバイト文字列引数を自動的に適切に処理し、現在使用しているマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識します。 `_wsplitpath` は `_splitpath` のワイド文字バージョンであり、`_wsplitpath` の引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです。  
  
 **セキュリティに関するメモ**これらの関数は、バッファー オーバーランの問題によって潜在的な脅威を引き起こすことがあります。 バッファー オーバーランは、システムを攻撃するときによく使用される方法であり、その結果、認められていない権限が昇格されます。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。 これらの関数のセキュリティを強化したバージョンについては、「[_splitpath_s、_wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)」をご覧ください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsplitpath`|`_splitpath`|`_splitpath`|`_wsplitpath`|  
  
 完全なパスの各コンポーネントは別々のバッファーに格納されています。マニフェスト定数 `_MAX_DRIVE`、`_MAX_DIR`、`_MAX_FNAME`、および `_MAX_EXT` (STDLIB.H で定義される) で、各々のファイル コンポーネントの最大サイズを指定します。 対応するマニフェスト定数よりも大きいファイル コンポーネントでは、ヒープ破損が発生します。  
  
 各バッファーは、バッファー オーバーランの発生を回避するために、対応するマニフェスト定数と同じ大きさである必要があります。  
  
 マニフェスト定数の値を次の表に示します。  
  
|name|[値]|  
|----------|-----------|  
|_MAX_DRIVE|3|  
|_MAX_DIR|256|  
|_MAX_FNAME|256|  
|_MAX_EXT|256|  
  
 完全なパスにコンポーネント (たとえばファイル名) が含まれていない場合、`_splitpath` は対応するバッファーに空の文字列を割り当てます。  
  
 `path` 以外の、必要としない任意のパラメーターについて、`NULL` を `_splitpath` に渡すことができます。  
  
 `path` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、 `errno` が `EINVAL` に設定され、関数から `EINVAL`が返されます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_splitpath`|\<stdlib.h>|  
|`_wsplitpath`|\<stdlib.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 「[_makepath](../../c-runtime-library/reference/makepath-wmakepath.md)」の例をご覧ください。  
  
## <a name="see-also"></a>参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_fullpath、_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_makepath、_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_splitpath_s、_wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)