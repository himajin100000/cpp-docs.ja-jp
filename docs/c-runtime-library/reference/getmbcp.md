---
title: _getmbcp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _getmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getmbcp
- getmbcp
dev_langs:
- C++
helpviewer_keywords:
- code pages, determining current
- _getmbcp function
- getmbcp function
ms.assetid: 2db202d4-5c3d-4871-a0b8-ceb0b79ee7bb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5cfb2ee9e84d8a586d14cb95558d7d59967eeecc
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="getmbcp"></a>_getmbcp
現在のコード ページを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
int _getmbcp( void );  
```  
  
## <a name="return-value"></a>戻り値  
 現在のマルチバイト コード ページを返します。 戻り値 0 は、シングル バイトのコード ページが使用中であることを示します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_getmbcp`|\<mbctype.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>参照  
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)