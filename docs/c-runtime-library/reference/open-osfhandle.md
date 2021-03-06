---
title: _open_osfhandle | Microsoft Docs
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _open_osfhandle
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
- _open_osfhandle
- open_osfhandle
dev_langs:
- C++
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 34f60a327f3bc4c6a6ce1beb6d7b399faa393a70
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="openosfhandle"></a>_open_osfhandle

C ランタイム ファイル記述子を既存のオペレーティング システムのファイル ハンドルに関連付けます。

## <a name="syntax"></a>構文

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>パラメーター

*osfhandle*  
オペレーティング システムのファイル ハンドル。

*flags*  
許可される操作の種類。

## <a name="return-value"></a>戻り値

正常に終了した場合、`_open_osfhandle` は C ランタイム ファイル記述子を返します。 それ以外の場合、-1 を返します。

## <a name="remarks"></a>コメント

`_open_osfhandle`関数が C ランタイム ファイル記述子を割り当てますで指定されたオペレーティング システム ファイル ハンドルに関連付けます*osfhandle*です。 *フラグ*引数は Fcntl.h で定義されているマニフェスト定数の 1 つ以上の整数式です。 2 つまたは複数のマニフェスト定数を使用してフォームにする場合、*フラグ*引数、定数はビットごとの OR 演算子で組み合わされます ( **&#124;** )。

Fcntl.h には、次のマニフェスト定数が定義されています。

**\_O\_追加**  
書き込み操作の前に、毎回、ファイル ポインターをファイルの末尾に位置指定します。

**\_O\_RDONLY**  
読み取り専用でファイルを開きます。

**\_O\_TEXT**  
ファイルをテキスト (変換) モードで開きます。

**\_O\_WTEXT**  
Unicode (UTF-16 に変換) モードでファイルを開きます。

使用して開いたファイルを閉じる`_open_osfhandle`、呼び出す[\_を閉じる](../../c-runtime-library/reference/close.md)です。 呼び出しによって基になる OS ファイル ハンドルが閉じられたも`_close`Win32 関数を呼び出す必要はありませんので、`CloseHandle`元のハンドル。 ファイル記述子がによって所有されている場合、`FILE *`ストリーム、呼び出すことで、 [fclose](../../c-runtime-library/reference/fclose-fcloseall.md)を`FILE *`ストリームは、ファイル記述子と基になるハンドルの両方にも閉じられます。 この場合、呼び出さない`_close`ファイル記述子。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`_open_osfhandle`|\<io.h>|

互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)  
