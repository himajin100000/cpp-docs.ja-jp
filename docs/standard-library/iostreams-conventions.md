---
title: "iostreams の規則 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- iostream header
- C++ Standard Library, iostreams
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b6a89479eaef6839d1c0f6d30061b53dd198e592
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="iostreams-conventions"></a>iostreams の規則
iostreams のヘッダーは、テキストとエンコードされた形式間の変換、および外部ファイルへの入力と出力の間の変換をサポートします。  
  
|||  
|-|-|  
|[\<fstream >](../standard-library/fstream.md)|[\<iomanip >](../standard-library/iomanip.md)|  
|[\<ios>](../standard-library/ios.md)|[\<iosfwd >](../standard-library/iosfwd.md)|  
|[\<iostream>](../standard-library/iostream.md)|[\<istream>](../standard-library/istream.md)|  
|[\<ostream>](../standard-library/ostream.md)|[\<sstream>](../standard-library/sstream.md)|  
|[\<streambuf>](../standard-library/streambuf.md)|[\<sstream>](../standard-library/strstream.md)|  
  
 iostreams の最も単純に使用するには、[\<iostream >](../standard-library/iostream.md) のヘッダーを含めるだけです。 これにより、[cin](../standard-library/iostream.md#cin) または [wcin](../standard-library/iostream.md#wcin) から値を抽出して標準の入力を読み取ることができます。 この操作を行うための規則は、クラスの説明「[basic_istream クラス](../standard-library/basic-istream-class.md)」で概要が示されています。 値を [cout](../standard-library/iostream.md#cout) または [wcout](../standard-library/iostream.md#wcout) に挿入して、標準出力を書き込むこともできます。 この操作を行うための規則は、クラスの説明「[basic_ostream クラス](../standard-library/basic-ostream-class.md)」で概要が示されています。 抽出と挿入の両方に共通するコントロールの書式設定は、クラス [basic_ios クラス](../standard-library/basic-ios-class.md) によって管理されています。 オブジェクトの抽出および挿入という名目でのこの書式設定情報の操作は、少数のマニピュレ―ターのみが行うことができます。  
  
 [\<fstream >](../standard-library/fstream.md) で宣言されたクラスを使用して、名前で開いたファイルに同じ iostream 操作を実行することができます。 iostream とクラス [basic_string クラス](../standard-library/basic-string-class.md)のオブジェクト間で変換するには、[\<sstream >](../standard-library/sstream.md) で宣言されたクラスを使用します。 同じ操作を C 文字列で行うには、[\<strstream >](../standard-library/strstream.md) で宣言されたクラスを使用します。  
  
 残りのヘッダーは、通常は iostreams クラスの上級ユーザーのみに直接利益があるサポート サービスを提供するものです。  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

