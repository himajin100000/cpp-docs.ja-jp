---
title: codecvt_utf8 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- codecvt/std::codecvt_utf8
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf8 class
ms.assetid: 2a87478f-e2d4-4b8d-ad9c-00add01d1bb0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e211d58843b365610a674500afa3b713b37d7a2c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="codecvtutf8"></a>codecvt_utf8
UCS-2 または UCS-4 としてエンコードされたワイド文字と、UTF-8 としてエンコードされたバイト ストリームを変換する[ロケール](../standard-library/locale-class.md) ファセットを表します。

```
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>パラメーター

`Elem`  
ワイド文字要素型。  
`Maxcode`  
ロケール ファセットの文字の最大数。  
`Mode`  
ロケール ファセットの構成情報。  

## <a name="remarks"></a>コメント

このバイト ストリームはバイナリ ファイルまたはテキスト ファイルに書き込むことができます。  

## <a name="requirements"></a>必要条件

ヘッダー: <codecvt> 名前空間: std
