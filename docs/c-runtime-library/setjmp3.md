---
title: _setjmp3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _setjmp3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- setjmp3
- _setjmp3
dev_langs:
- C++
helpviewer_keywords:
- _setjmp3 function
- setjmp3 function
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 72bc1e833ddaa72979e25274b7328d8987f62763
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setjmp3"></a>_setjmp3
内部 CRT 関数。 `setjmp` 関数の新しい実装。  
  
## <a name="syntax"></a>構文  
  
```  
int _setjmp3(  
   OUT jmp_buf env,  
   int count,  
   (optional parameters)  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `env`  
 状態情報を格納するためのバッファーのアドレス。  
  
 [入力] `count`  
 `DWORD` に格納されている情報の追加 `optional parameters` の数。  
  
 [入力] `optional parameters`  
 `setjmp` の組み込みによってプッシュダウンされる追加データ。 最初の `DWORD` は、追加データをアンワインドして不揮発性レジスタの状態に戻るために使用される関数ポインターです。 2 番目の `DWORD` は、復元される試行レベルです。 これ以上のデータは、`jmp_buf` の一般的なデータ配列に保存されます。  
  
## <a name="return-value"></a>戻り値  
 常に 0 を返します。  
  
## <a name="remarks"></a>コメント  
 この関数は C++ プログラムでは使用しないでください。 これは、C++ をサポートしない組み込み関数です。 `setjmp` の使用方法の詳細については、「[setjmp/longjmp の使用](../cpp/using-setjmp-longjmp.md)」をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [setjmp](../c-runtime-library/reference/setjmp.md)