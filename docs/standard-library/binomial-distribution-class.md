---
title: "binomial_distribution クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- random/std::binomial_distribution
- random/std::binomial_distribution::reset
- random/std::binomial_distribution::p
- random/std::binomial_distribution::t
- random/std::binomial_distribution::param
- random/std::binomial_distribution::min
- random/std::binomial_distribution::max
- random/std::binomial_distribution::operator()
- random/std::binomial_distribution::param_type
- random/std::binomial_distribution::param_type::p
- random/std::binomial_distribution::param_type::t
- random/std::binomial_distribution::param_type::operator==
- random/std::binomial_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- std::binomial_distribution [C++]
- std::binomial_distribution [C++], reset
- std::binomial_distribution [C++], p
- std::binomial_distribution [C++], t
- std::binomial_distribution [C++], param
- std::binomial_distribution [C++], min
- std::binomial_distribution [C++], max
- std::binomial_distribution [C++], param_type
- std::binomial_distribution [C++], param_type
ms.assetid: b7c8a26a-da8c-45a5-a3a8-208f7a3609ce
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0576050177fa7685f38265ba24f43dab01749b73
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="binomialdistribution-class"></a>binomial_distribution クラス
二項分布を生成します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class IntType = int>
class binomial_distribution  
   {  
public:  
   // types  
   typedef IntType result_type;  
   struct param_type;  
   
   // constructors and reset functions  
   explicit binomial_distribution(result_type t = 1, double p = 0.5);
   explicit binomial_distribution(const param_type& parm);
   void reset();
   
   // generating functions  
   template <class URNG>  
   result_type operator()(URNG& gen);
   template <class URNG>  
   result_type operator()(URNG& gen, const param_type& parm);
   
   // property functions  
   result_type t() const;
   double p() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };  
```  
#### <a name="parameters"></a>パラメーター  
*IntType*  
結果を表す整数型。既定値は `int` です。 使用可能な型については、[\<random>](../standard-library/random.md) をご覧ください。  
  
*URNG* Uniform Random Number Generator エンジン。 使用可能な型については、[\<random>](../standard-library/random.md) をご覧ください。  

## <a name="remarks"></a>コメント  
このテンプレート クラスは、二項分布の離散確率関数に従って分布した、ユーザー指定の整数型の値または型 `int` の値 (指定がない場合) を生成する分布を表します。 次の表は、個々のメンバーに関する記事にリンクしています。  
  
||||  
|-|-|-|  
|[binomial_distribution](#binomial_distribution)|`binomial_distribution::t`|`binomial_distribution::param`|  
|`binomial_distribution::operator()`|`binomial_distribution::p`|[param_type](#param_type)|  
  
プロパティ メンバー `t()` と `p()` はそれぞれ、格納されている分布パラメーター `t` と `p` の値を返します。  
  
プロパティ メンバー関数 `param()` は、格納されている分布パラメーター パッケージ `param_type` を設定または返します。  

メンバー関数の `min()` と `max()` はそれぞれ、考えられる結果の最小値と最大値を返します。  
  
`reset()` メンバー関数は、次回 `operator()` を呼び出したときに、その結果が、その前にエンジンから取得された値に左右されないようにするため、キャッシュされている値をすべて破棄します。  
  
`operator()` メンバー関数は、現在のパラメーター パッケージと指定したパラメーター パッケージのいずれかから、URNG エンジンに基づいて次に生成された値を返します。
  
分布クラスとそのメンバーの詳細については、[\<random>](../standard-library/random.md) を参照してください。  
  
二項分布の離散確率関数の詳細については、Wolfram MathWorld の記事「[二項分布](http://go.microsoft.com/fwlink/p/?linkid=398469)」を参照してください。  
  
## <a name="example"></a>例  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const int t, const double p, const int& s) {  
  
    // uncomment to use a non-deterministic seed  
    //    std::random_device rd;  
    //    std::mt19937 gen(rd());  
    std::mt19937 gen(1729);  
  
    std::binomial_distribution<> distr(t, p);  
  
    std::cout << std::endl;  
    std::cout << "p == " << distr.p() << std::endl;  
    std::cout << "t == " << distr.t() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<int, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Histogram for " << s << " samples:" << std::endl;  
    for (const auto& elem : histogram) {  
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    int    t_dist = 1;  
    double p_dist = 0.5;  
    int    samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter an integer value for t distribution (where 0 <= t): ";  
    std::cin >> t_dist;  
    std::cout << "Enter a double value for p distribution (where 0.0 <= p <= 1.0): ";  
    std::cin >> p_dist;  
    std::cout << "Enter an integer value for a sample count: ";  
    std::cin >> samples;  
  
    test(t_dist, p_dist, samples);  
}  
```  
  
最初の実行:  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter an integer value for t distribution (where 0 <= t): 22  
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .25  
Enter an integer value for a sample count: 100  
 
p == 0.25  
t == 22  
Histogram for 100 samples:  
    1 :  
    2 ::  
    3 :::::::::::::  
    4 ::::::::::::::  
    5 :::::::::::::::::::::::::  
    6 ::::::::::::::::::  
    7 :::::::::::::  
    8 ::::::  
    9 ::::::  
    11 :  
    12 :  
```  
  
2 回目の実行:  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter an integer value for t distribution (where 0 <= t): 22  
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .5  
Enter an integer value for a sample count: 100  
 
p == 0.5  
t == 22  
Histogram for 100 samples:  
    6 :  
    7 ::  
    8 :::::::::  
    9 ::::::::::  
    10 ::::::::::::::::  
    11 :::::::::::::::::::  
    12 :::::::::::  
    13 :::::::::::::  
    14 :::::::::::::::  
    15 ::  
    16 ::  
```  
  
3 回目の実行:  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter an integer value for t distribution (where 0 <= t): 22  
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .75  
Enter an integer value for a sample count: 100  
 
p == 0.75  
t == 22  
Histogram for 100 samples:  
    13 ::::  
    14 :::::::::::  
    15 :::::::::::::::  
    16 :::::::::::::::::::::  
    17 ::::::::::::::  
    18 :::::::::::::::::  
    19 :::::::::::  
    20 ::::::  
    21 :  
```  
  
## <a name="requirements"></a>必要条件  
**ヘッダー:** \<random>  
  
**名前空間:** std  
  
##  <a name="binomial_distribution"></a>  binomial_distribution::binomial_distribution  
分布を作成します。  
  
```  
explicit binomial_distribution(result_type t = 1, double p = 0.5);
explicit binomial_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>パラメーター  
*t*  
`t` 分布パラメーター。  
  
*p*  
`p` 分布パラメーター。  
  
*parm*  
分布の作成に使用される `param_type` の構造体。  
  
### <a name="remarks"></a>コメント  
**前提条件:** `0 ≤ t` および `0.0 ≤ p ≤ 1.0`  
  
1 つ目のコンストラクターは、格納されている値 `p` と `t` にそれぞれ *p* と *t* の値を保持するオブジェクトを作成します。  
  
2 つ目のコンストラクターは、格納されているパラメーターが *parm* から初期化されるオブジェクトを作成します。 `param()` メンバー関数を呼び出すと、既存の分布の現在のパラメーターを取得および設定できます。  
  
##  <a name="param_type"></a>  binomial_distribution::param_type  
分布のすべてのパラメーターを格納します。  
  
```cpp  
struct param_type {  
   typedef binomial_distribution<result_type> distribution_type;  
   param_type(result_type t = 1, double p = 0.5);
   result_type t() const;
   double p() const;
   .....  
   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  
  
### <a name="parameters"></a>パラメーター  
*t*  
`t` 分布パラメーター。  
  
*p*  
`p` 分布パラメーター。  
  
*right*  
 このオブジェクトと比較する `param_type` オブジェクト。  
  
### <a name="remarks"></a>コメント  
**前提条件:** `0 ≤ t` および `0.0 ≤ p ≤ 1.0`  
  
この構造体は、インスタンス化時に分布のクラス コンストラクターに渡したり、`param()` メンバー関数に渡して、既存の分布の格納されているパラメーターを設定したり、`operator()` に渡して、格納されているパラメーターの代わりに使用したりすることができます。  
  
## <a name="see-also"></a>参照  
 [\<random>](../standard-library/random.md)



