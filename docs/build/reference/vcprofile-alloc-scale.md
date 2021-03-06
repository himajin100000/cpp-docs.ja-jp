---
title: VCPROFILE_ALLOC_SCALE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VCPROFILE_ALLOC_SCALE
dev_langs:
- C++
helpviewer_keywords:
- VCPROFILE_ALLOC_SCALE environment variable
ms.assetid: 5cb5ce27-f9b8-489b-b46c-d6e9bcab2d34
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7b441f41106544633bd691c409fa04c989146f0
ms.sourcegitcommit: 5cd2e3e51ecc8d9fc0d889555b4bfa193ba1d6a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2018
---
# <a name="vcprofileallocscale"></a>VCPROFILE_ALLOC_SCALE
プロファイル データを保持するために割り当てられたメモリの量を変更します。  
  
## <a name="syntax"></a>構文  
  
```  
VCPROFILE_ALLOC_SCALE=scale_value  
```  
  
#### <a name="parameters"></a>パラメーター  
 `scale_value`  
 テスト シナリオの実行対象とするメモリの量のスケール値。  既定値は 1 です。  
  
## <a name="remarks"></a>コメント  
 まれなケースではありません十分なメモリをサポートするために使用可能なテストのシナリオを実行している場合は、プロファイル データを収集します。  その場合は、メモリの量を向上することが`VCPROFILE_ALLOC_SCALE`です。  
  
 十分なメモリがあることを示すテストの実行中にエラー メッセージを受信する場合より大きい値を割り当てる`VCPROFILE_ALLOC_SCALE`テストの実行がメモリ不足のエラーなく完了するまでです。  
  
## <a name="example"></a>例  
  
```  
set VCPROFILE_ALLOC_SCALE=2  
```  
  
## <a name="see-also"></a>関連項目  
 [ガイド付き最適化のプロファイルの環境変数](../../build/reference/environment-variables-for-profile-guided-optimizations.md)