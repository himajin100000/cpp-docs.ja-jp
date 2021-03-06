---
title: "codecvt_byname クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xlocale/std::codecvt_byname
dev_langs:
- C++
helpviewer_keywords:
- codecvt_byname class
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0241d88c532fc5f4bff0d8a76a16c5bfe434e22a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="codecvtbyname-class"></a>codecvt_byname クラス
特定のロケールの照合ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。変換に関する文化的領域に固有の情報を取得できるようにします。  
  
## <a name="syntax"></a>構文  
  
```
template <class CharType, class Byte, class StateType>
class codecvt_byname: public codecvt<CharType, Byte, StateType> {
public:
    explicit codecvt_byname(
    const char* _Locname,
    size_t _Refs = 0);
```  
  
```
explicit codecvt_byname(
    const string& _Locname,
    size_t _Refs = 0);
```  
  
```
protected:
    virtual ~codecvt_byname();

};
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Locname`  
 名前付きのロケール。  
  
 `_Refs`  
 最初の参照数。  
  
## <a name="remarks"></a>コメント  
 名前付きのロケールが作成されると、byname ファセットが自動的に作成されます。  
  
 その動作は名前付きのロケール `_Locname` で決まります。 各コンストラクターは、[codecvt](../standard-library/codecvt-class.md)\<CharType, Byte, StateType>( `_Refs`) を使用して、その基本オブジェクトを初期化します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<locale>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)



