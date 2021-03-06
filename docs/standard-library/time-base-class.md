---
title: "time_base クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- locale/std::time_base
dev_langs:
- C++
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc7ed644d7c66ea7e3ca49b6d403b17535fa3eb9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="timebase-class"></a>time_base クラス
このクラスは、time_get テンプレート クラスのファセットの基底クラスとして使用されます。**dateorder** 列挙型とこの型の複数の定数のみを定義します。  
  
## <a name="syntax"></a>構文  
  
```
class time_base : public locale::facet {
public:
    enum dateorder {no_order,
    dmy,
 mdy,
    ymd,
 ydm};
    time_base(
 size_t _Refs = 0)
 ~time_base();

};
```  
  
## <a name="remarks"></a>コメント  
 各定数は、日付部分を順序付けるための異なる方法を特徴付けます。 定数は次のとおりです。  
  
- **no_order** は、特定の順序を指定しません。  
  
- **dmy** は、2 December 1979 のように日、月、年という順序を指定します。  
  
- **dmy** は、December 2, 1979 のように、月、日、年という順序を指定します。  
  
- **ymd** は、1979/12/2 のように、年、月、日という順序を指定します。  
  
- **ymd** は、1979: 2 Dec のように、年、日、月という順序を指定します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<locale>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)



