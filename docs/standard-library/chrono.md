---
title: '&lt;chrono&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- chrono/std::chrono::nanoseconds
- chrono/std::chrono::minutes
- chrono/std::chrono::seconds
- <chrono>
- chrono/std::chrono::hours
- chrono/std::chrono::milliseconds
- chrono/std::chrono::microseconds
dev_langs:
- C++
ms.assetid: 844de749-f306-482e-89bc-6f53c99c8324
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 255c70eeb29e8bedaeec43d9844ca41b42fb470a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ltchronogt"></a>&lt;chrono&gt;
期間と時点を表し、操作するクラスと関数を定義するために、標準ヘッダー \<chrono> を含めます。  
  
 以降、Visual Studio 2015 の実装で`steady_clock`安定性と単調性の C++ 標準の要件を満たすに変更されました。 現在、`steady_clock` は QueryPerformanceCounter() に基づき、`high_resolution_clock` は `steady_clock` の typedef です。 結果として、Visual C++ では現在、`steady_clock::time_point` は `chrono::time_point<steady_clock>` の typedef です。ただし、他の実装では異なる場合があります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
#include <chrono>  
```  

### <a name="classes"></a>クラス  
  
|名前|説明|  
|----------|-----------------|  
|[duration クラス](../standard-library/duration-class.md)|時間間隔を保持する型を表します。|  
|[time_point クラス](../standard-library/time-point-class.md)|時点を表す型を表します。|  
  
### <a name="structs"></a>構造体  
  
|name|説明|  
|----------|-----------------|  
|[common_type 構造体](../standard-library/common-type-structure.md)|`duration` と `time_point` のインスタンス化のテンプレート クラス [common_type](../standard-library/common-type-class.md) の特殊化を表します。|  
|[duration_values 構造体](../standard-library/duration-values-structure.md)|`duration` テンプレート パラメーター `Rep` に特定の値を指定します。|  
|[steady_clock 構造体](../standard-library/steady-clock-struct.md)|`steady` クロックを表します。|  
|[system_clock 構造体](../standard-library/system-clock-structure.md)|システムのリアルタイム クロックに基づく*クロックの型*を表します。|  
|[treat_as_floating_point 構造体](../standard-library/treat-as-floating-point-structure.md)|型を浮動小数点型として扱うことができるかどうかを指定します。|  
  
### <a name="functions"></a>関数  
  
|名前|説明|  
|----------|-----------------|  
|[duration_cast](../standard-library/chrono-functions.md#duration_cast)|`duration` オブジェクトを指定した型にキャストします。|  
|[time_point_cast](../standard-library/chrono-functions.md#time_point_cast)|`time_point` オブジェクトを指定した型にキャストします。|  
  
### <a name="operators"></a>演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator-](../standard-library/chrono-operators.md#operator-)|`duration` オブジェクトおよび `time_point` オブジェクトの減算または否定の演算子。|  
|[operator!=](../standard-library/chrono-operators.md#op_neq)|`duration` オブジェクトおよび `time_point` オブジェクトで使用される非等値演算子。|  
|[modulo 演算子](../standard-library/chrono-operators.md#op_modulo)|`duration` オブジェクトに対するモジュロ演算の演算子。|  
|[operator*](../standard-library/chrono-operators.md#op_star)|`duration` オブジェクトの乗算演算子。|  
|[operator/](../standard-library/chrono-operators.md#op_div)|`duration` オブジェクトの除算演算子。|  
|[operator+](../standard-library/chrono-operators.md#op_add)|`duration` オブジェクトおよび `time_point` オブジェクトを追加します。|  
|[operator&lt;](../standard-library/chrono-operators.md#op_lt)|一方の `duration` オブジェクトまたは `time_point` オブジェクトの値が、もう一方の `duration` オブジェクトまたは `time_point` オブジェクトの値未満かどうかを判断します。|  
|[operator&lt;=](../standard-library/chrono-operators.md#op_lt_eq)|一方の `duration` オブジェクトまたは `time_point` オブジェクトの値が、もう一方の `duration` オブジェクトまたは `time_point` オブジェクトの値以下かどうかを判断します。|  
|[operator==](../standard-library/chrono-operators.md#op_eq_eq)|2 つの `duration` オブジェクトが同じ長さの時間間隔を表しているかどうか、または 2 つの `time_point` オブジェクトが同じ時点を表しているかどうかを判断します。|  
|[operator&gt;](../standard-library/chrono-operators.md#op_gt)|一方の `duration` オブジェクトまたは `time_point` オブジェクトの値が、もう一方の `duration` オブジェクトまたは `time_point` オブジェクトの値より大きいかどうかを判断します。|  
|[operator&gt;=](../standard-library/chrono-operators.md#op_gt_eq)|一方の `duration` オブジェクトまたは `time_point` オブジェクトの値が、もう一方の `duration` オブジェクトまたは `time_point` オブジェクトの値以上かどうかを判断します。|  
  
### <a name="predefined-duration-types"></a>定義済みの期間の種類  
 次の typedef で使用される比率の種類の詳細については、「[\<<ratio>](../standard-library/ratio.md)」を参照してください。  
  
|Typedef|説明|  
|-------------|-----------------|  
|`typedef duration<long long, nano> nanoseconds;`|ティック間隔が 1 ナノ秒の `duration` 型のシノニムです。|  
|`typedef duration<long long, micro> microseconds;`|ティック間隔が 1 マイクロ秒の `duration` 型のシノニムです。|  
|`typedef duration<long long, milli> milliseconds;`|ティック間隔が 1 ミリ秒の `duration` 型のシノニムです。|  
|`typedef duration<long long> seconds;`|ティック間隔が 1 秒の `duration` 型のシノニムです。|  
|`typedef duration<int, ratio<60> > minutes;`|ティック間隔が 1 分の `duration` 型のシノニムです。|  
|`typedef duration<int, ratio<3600> > hours;`|ティック間隔が 1 時間の `duration` 型のシノニムです。|  
  
### <a name="literals"></a>リテラル  
 **(C++11)** \<chrono> ヘッダーでは、次の[ユーザー定義リテラル](../cpp/user-defined-literals-cpp.md)を定義します。これを使用することで、コードの利便性、タイプ セーフ、保守性が向上します。 これらのリテラルは `literals::chrono_literals` インライン名前空間で定義されており、std::chrono がスコープに含まれている場合にスコープに含まれます。  
  
|Literal|説明|  
|-------------|-----------------|  
|chrono::hours operator "" h(unsigned long long Val)|時間を整数値として指定します。|  
|:duration\<double 比\<3600 >> operator""h (long double Val)|時間を浮動小数点値として指定します。|  
|chrono::minutes (operator "" min)(unsigned long long Val)|分を整数値として指定します。|  
|:duration\<double 比\<60 >> (operator""min) (long double 型 Val)|分を浮動小数点値として指定します。|  
|chrono::seconds operator "" s(unsigned long long Val)|分を整数値として指定します。|  
|chrono::duration\<double> operator "" s(long double Val)|秒を浮動小数点値として指定します。|  
|chrono::milliseconds operator "" ms(unsigned long long Val)|ミリ秒を整数値として指定します。|  
|chrono::duration\<double, milli> operator "" ms(long double Val)|ミリ秒を浮動小数点値として指定します。|  
|chrono::microseconds operator "" us(unsigned long long Val)|マイクロ秒を整数値として指定します。|  
|chrono::duration\<double, micro> operator "" us(long double Val)|マイクロ秒を浮動小数点値として指定します。|  
|chrono::nanoseconds operator "" ns(unsigned long long Val)|ナノ秒を整数値として指定します。|  
|chrono::duration\<double, nano> operator "" ns(long double Val)|ナノ秒を浮動小数点値として指定します。|  
|||  
  
chrono リテラルを使用する方法の例を次に示します。  
  
```  
constexpr auto day = 24h;  
constexpr auto week = 24h* 7;  
constexpr auto my_duration_unit = 108ms;  
```  
## <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)



