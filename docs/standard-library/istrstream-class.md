---
title: "istrstream クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
dev_langs:
- C++
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aec0c2bbac29da5406002aefbd6a6adcac926a33
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="istrstream-class"></a>istrstream クラス
クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーからの、要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```
class istrstream : public istream
```  
  
## <a name="remarks"></a>コメント  
 このオブジェクトは、クラス `strstreambuf` のオブジェクトを格納します。  
  
> [!NOTE]
>  このクラスは使用されていません。 代わりに、[istringstream](../standard-library/sstream-typedefs.md#istringstream) または [wistringstream](../standard-library/sstream-typedefs.md#wistringstream) を使用することを検討してください。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[istrstream](#istrstream)|`istrstream` 型のオブジェクトを構築します。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[rdbuf](#rdbuf)|ストリームの関連付けられた `strstreambuf` オブジェクトへのポインターを返します。|  
|[str](#str)|[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<strstream>  
  
 **名前空間:** std  
  
##  <a name="istrstream"></a>  istrstream::istrstream  
 `istrstream` 型のオブジェクトを構築します。  
  
```
explicit istrstream(
    const char* ptr);

explicit istrstream(
    char* ptr);

istrstream(
    const char* ptr,
    streamsize count);

istrstream(
    char* ptr,
    int count);
```  
  
### <a name="parameters"></a>パラメーター  
 `count`  
 バッファー (`ptr`) の長さ。  
  
 `ptr`  
 バッファーが初期化されているコンテンツ。  
  
### <a name="remarks"></a>コメント  
 すべてのコンストラクターは、[istream](../standard-library/istream-typedefs.md#istream)(**sb**) を呼び出すことにより基本クラスを初期化します。ここで、**sb** は [strstreambuf](../standard-library/strstreambuf-class.md) クラスの格納されているオブジェクトです。 最初の 2 つのコンストラクターは、`strstreambuf`( ( **const**`char` \*) `ptr`, 0 ) を呼び出すことによって **sb** の初期化も行います。 残りの 2 つのコンストラクターは、代わりに `strstreambuf`( ( **const**`char` *) `ptr`, `count` ) を呼び出します。  
  
##  <a name="rdbuf"></a>  istrstream::rdbuf  
 ストリームの関連付けられた strstreambuf オブジェクトへのポインターを返します。  
  
```
strstreambuf *rdbuf() const
```  
  
### <a name="return-value"></a>戻り値  
 ストリームの関連付けられた strstreambuf オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、ポインター型の格納されたストリーム バッファーのアドレスを [strstreambuf](../standard-library/strstreambuf-class.md) に返します。  
  
### <a name="example"></a>例  
  `rdbuf` の使用例は、[strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) を参照してください。  
  
##  <a name="str"></a>  istrstream::str  
 [freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。  
  
```
char *str();
```  
  
### <a name="return-value"></a>戻り値  
 被制御シーケンスの先頭へのポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、[rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str) を返します。  
  
### <a name="example"></a>例  
  **str** の使用例は、[strstream::str](../standard-library/strstreambuf-class.md#str) をご覧ください。  
  
## <a name="see-also"></a>参照  
 [istream](../standard-library/istream-typedefs.md#istream)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)



