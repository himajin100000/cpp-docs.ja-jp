---
title: strftime、wcsftime、_strftime_l、_wcsftime_l | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcsftime
- strftime
- wcsftime
- _strftime_l
- _wcsftime_l
dev_langs:
- C++
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc71dc09b6634e01b1ba78621344dfb5c589c8d5
ms.sourcegitcommit: 604907f77eb6c5b1899194a9877726f3e8c2dabc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="strftime-wcsftime-strftimel-wcsftimel"></a>strftime、wcsftime、_strftime_l、_wcsftime_l

時刻の文字列の書式を指定します。

## <a name="syntax"></a>構文

```
size_t strftime(
   char *strDest,
   size_t maxsize,
   const char *format,
   const struct tm *timeptr
);
size_t _strftime_l(
   char *strDest,
   size_t maxsize,
   const char *format,
   const struct tm *timeptr,
   _locale_t locale
);
size_t wcsftime(
   wchar_t *strDest,
   size_t maxsize,
   const wchar_t *format,
   const struct tm *timeptr
);
size_t _wcsftime_l(
   wchar_t *strDest,
   size_t maxsize,
   const wchar_t *format,
   const struct tm *timeptr,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*strDest*<br/>
出力する文字列。

*maxsize*<br/>
サイズ、*追加される文字*バッファー、単位は文字 (**char**または**wchar_t**)。

*format*<br/>
書式指定文字列。

*timeptr*<br/>
**tm**データ構造体。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

`strftime` 配置する文字数を返します*追加される文字*と`wcsftime`対応するワイド文字数を返します。

場合は、文字、終端の null の合計数は、複数の*maxsize*の両方を`strftime`と`wcsftime`0 との内容を返す*追加される文字*は不確定になります。

文字数*追加される文字*のリテラル文字の数と等しく、*形式*に追加することがありますの文字だけでなく*形式*書式設定コードを使用しています。 文字列の終端の NULL は戻り値にはカウントされません。

## <a name="remarks"></a>コメント

`strftime`と`wcsftime`関数形式、 **tm**時刻の値*timeptr*に従って、指定された*形式*引数の結果を格納し、バッファー*追加される文字*です。 最大で*maxsize*文字は、文字列に配置されます。 内のフィールドの詳細については、 *timeptr*構造体は、「 [asctime](../../c-runtime-library/reference/asctime-wasctime.md)です。 `wcsftime` は `strftime` のワイド文字版です。その文字列ポインター引数はワイド文字の文字列を指します。 それ以外では、これらの関数の動作は同じです。

> [!NOTE]
>  Visual C 2005 以前のバージョン、ドキュメントの説明、*形式*のパラメーター`wcsftime`データ型として`const wchar_t *`がの実際の実装、*形式*データ型が`const char *`です。 実装、*形式*データ型が、現在と以前のドキュメントを反映するように更新された`const wchar_t *`です。

この関数は、パラメーターを検証します。 場合*追加される文字*、*形式*、または*timeptr*が null ポインターの場合、または、 **tm**によってアドレス指定されるデータ構造体*timeptr*が正しくありません (たとえば、日付や時刻の値が範囲外が含まれる場合)、または、*形式*文字列に無効な書式設定コードが含まれている場合、無効なパラメーター ハンドラーが呼び出されます」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、関数の戻り値 0 とセットの実行が許可された場合**errno**に**EINVAL**です。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcsftime`|`strftime`|`strftime`|`wcsftime`|

*形式*引数は、コードを 1 つまたは複数の; とで構成されます。 `printf`、書式指定コードには、パーセント記号が付きます (**%**)。 文字で始まらないが**%**をそのままコピーされる`strDest`です。 **LC_TIME** 、現在のロケールのカテゴリは、の出力の書式設定に影響が`strftime`です。 (詳細について**LC_TIME**を参照してください[setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md))。`strftime`と`wcsftime`関数を使用して、現在設定されているロケール。 `_strftime_l`と`_wcsftime_l`ロケールをパラメーターとして受け取る、し、現在設定されているのではなくそれを使用する点を除いて、これらの関数のバージョンが同一のロケールです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

`strftime`関数では、これらのコードを書式指定をサポートします。

|||
|-|-|
|コード|置換文字列|
|`%a`|ロケールでの曜日の省略名|
|`%A`|ロケールでの曜日の正式名|
|`%b`|ロケールにおける月の省略名|
|`%B`|ロケールにおける月の正式名|
|`%c`|ロケールに合った日付と時刻の表記|
|`%C`|年が 100 で割った値し、10 進数 (00−99) を整数に切り捨てられます|
|`%d`|10 進数 (01 ~ 31) で月の日|
|`%D`|`%m/%d/%y` と同じ意味です。|
|`%e`|1 桁の数字をスペースでは、場所の前に 10 進数 (1 ~ 31) で月の日|
|`%F`|`%Y-%m-%d` と同じ意味です。|
|`%g`|10 進数として ISO 8601 週に基づく年の最後の 2 つの桁 (00 ~ 99)|
|`%G`|ISO 8601 週に基づく年を 10 進数として|
|`%h`|月の省略名 (に相当`%b`)|
|`%H`|24 時間形式で表される時間 (00 ~ 23)|
|`%I`|12 時間形式 (01 ~ 12)|
|`%j`|10 進数 (001 ~ 366) 年の日付|
|`%m`|月を表す 10 進数値 (01 ~ 12)|
|`%M`|10 進数による分 (00 ~ 59)|
|`%n`|改行文字 (**\n**)|
|`%p`|ロケールのです。 12 時間制のインジケーター|
|`%r`|ロケールの 12 時間制の時刻|
|`%R`|`%H:%M` と同じ意味です。|
|`%S`|10 進数による秒 (00 ~ 59)|
|`%t`|水平タブ文字 (**\t**)|
|`%T`|等価`%H:%M:%S`、ISO 8601 時刻の形式|
|`%u`|ISO 8601 曜日の 10 進数 (1 ~ 7 です。月曜日が 1)|
|`%U`|10 進数年の週番号 (00 ~ 53) で、最初の日曜日は第 1 週の最初の日|
|`%V`|ISO 8601 週数を 10 進数 (00 ~ 53)|
|`%w`|10 進数による曜日 (0 ~ 6 です。日曜日は 0)|
|`%W`|10 進数年の週番号 (00 ~ 53)、最初の月曜日は第 1 週の最初の日|
|`%x`|ロケールの形式の日付形式|
|`%X`|ロケールの時刻の形式|
|`%y`|10 進数として、2 桁の年年 (00 ~ 99)|
|`%Y`|世紀を付けた 10 進数の年|
|`%z`|ISO 8601 形式では、UTC からのオフセットタイム ゾーンが不明の場合は文字なし|
|`%Z`|ロケールのタイム ゾーンの名前またはレジストリの設定に応じて、タイム ゾーンの省略形タイム ゾーンが不明の場合は文字なし|
|`%%`|パーセント記号|

`printf` 関数と同じように、書式コードのプレフィックスとして `#` フラグを付けることができます。 その場合、書式コードの説明は次のように変更します。

|[書式コード]|説明|
|-----------------|-------------|
|`%#a`, `%#A`, `%#b`, `%#B`, `%#g`, `%#G`, `%#h`, `%#n`, `%#p`, `%#t`, `%#u`, `%#w`, `%#X`, `%#z`, `%#Z`, `%#%`|`#` フラグは無視されます。|
|`%#c`|長い日付と時刻形式をロケールに対応します。 たとえば、"Tuesday, March 14, 1995, 12:41:29" です。|
|`%#x`|長い日付形式、ロケールに対応します。 たとえば、"Tuesday, March 14, 1995" です。|
|`%#d`, `%#D`, `%#e`, `%#F`, `%#H`, `%#I`, `%#j`, `%#m`, `%#M`, `%#r`, `%#R`, `%#S`, `%#T`, `%#U`, `%#V`, `%#W`, `%#y`, `%#Y`|先頭のゼロまたは空白 (存在する場合) を削除します。|

によって生成される ISO 8601 曜日と年の週に基づく`%V`、 `%g`、および`%G`、ここで、第 1 週は年 1 月 4 日、これを含む、少なくとも 4 日、年の最初の週はある週の始まりを月曜日を週を使用します。 年の第 1 月曜日が、第 2 の場合は、第 3、または第 4、前の日数は、前の年の最後の週の一部です。 その日の`%V`53 との両方に置き換え、`%g`と`%G`前年の桁の数字によって置き換えられます。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|`strftime`|\<time.h>|
|`wcsftime`|\<time.h> または \<wchar.h>|
|`_strftime_l`|\<time.h>|
|`_wcsftime_l`|\<time.h> または \<wchar.h>|

`_strftime_l`と`_wcsftime_l`関数は、Microsoft に固有です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[time](../../c-runtime-library/reference/time-time32-time64.md) の例を参照してください。

## <a name="see-also"></a>関連項目

[ロケール](../../c-runtime-library/locale.md) <br/>
[時間管理](../../c-runtime-library/time-management.md) <br/>
[文字列操作](../../c-runtime-library/string-manipulation-crt.md) <br/>
[localeconv](../../c-runtime-library/reference/localeconv.md) <br/>
[setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) <br/>
[strcoll 系関数](../../c-runtime-library/strcoll-functions.md) <br/>
[strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
