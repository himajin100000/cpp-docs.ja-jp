---
title: "basic_ofstream クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- fstream/std::basic_ofstream
- fstream/std::basic_ofstream::close
- fstream/std::basic_ofstream::is_open
- fstream/std::basic_ofstream::open
- fstream/std::basic_ofstream::rdbuf
- fstream/std::basic_ofstream::swap
dev_langs:
- C++
helpviewer_keywords:
- std::basic_ofstream [C++]
- std::basic_ofstream [C++], close
- std::basic_ofstream [C++], is_open
- std::basic_ofstream [C++], open
- std::basic_ofstream [C++], rdbuf
- std::basic_ofstream [C++], swap
ms.assetid: 3bcc9c51-6dfc-4844-8fcc-22ef57c9dff1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a85ff0d2b4aa59e956015478c1fc3eee77294fc8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="basicofstream-class"></a>basic_ofstream クラス
`Elem` 型の要素を含む [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> クラスのストリーム バッファーに要素とエンコードされたオブジェクトを挿入する際に、この処理を制御するオブジェクトを記述します。この型の特性は、`Tr` クラスによって決定されます。  
  
## <a name="syntax"></a>構文  
  
```
template <class Elem, class Tr = char_traits<Elem>>  
class basic_ofstream : public basic_ostream<Elem, Tr>
```  
  
#### <a name="parameters"></a>パラメーター  
 `Elem`  
 ファイル バッファーの基本要素。  
  
 `Tr`  
 ファイル バッファーの基本要素の特徴 (通常は `char_traits`< `Elem`>)。  
  
## <a name="remarks"></a>コメント  
 `basic_ofstream` を `wchar_t` で特殊化したクラスがファイルに書き込みを行う場合、ファイルがテキスト モードで開かれていると、MBCS シーケンスが書き込まれます。 内部表現には `wchar_t` 文字のバッファーが使用されます。  
  
 このオブジェクトは、クラス `basic_filebuf`< `Elem`, `Tr`> のオブジェクトを格納します。  
  
## <a name="example"></a>例  
 次の例では、`basic_ofstream` オブジェクトを作成して、これにテキストを書き込む方法を示します。  
  
```  
// basic_ofstream_class.cpp  
// compile with: /EHsc  
#include <fstream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ofstream ofs("ofstream.txt");  
    if (!ofs.bad())  
    {  
        ofs << "Writing to a basic_ofstream object..." << endl;  
        ofs.close();  
    }  
}  
```  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[basic_ofstream](#basic_ofstream)|`basic_ofstream` 型のオブジェクトを作成します。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[close](#close)|ファイルを閉じます。|  
|[is_open](#is_open)|ファイルが開いているかどうかを判断します。|  
|[open](#open)|ファイルを開きます。|  
|[rdbuf](#rdbuf)|格納されたストリーム バッファーのアドレスを返します。|  
|[swap](#swap)|この `basic_ofstream` の内容を、指定された `basic_ofstream` の内容と交換します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator=](#op_eq)|このストリーム オブジェクトの内容を割り当てます。 これは、`rvalue reference` が関係する移動代入で、コピーを残しません。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<fstream>  
  
 **名前空間:** std  
  
##  <a name="basic_ofstream"></a>  basic_ofstream::basic_ofstream  
 `basic_ofstream` 型のオブジェクトを作成します。  
  
```
basic_ofstream();

explicit basic_ofstream(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

explicit basic_ofstream(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

basic_ofstream(
    basic_ofstream&& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Filename`  
 開くファイルの名前。  
  
 `_Mode`  
 [ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。  
  
 `_Prot`  
 [_fsopen、_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md) の `shflag` パラメーターと同等の既定のファイル保護。  
  
 `right`  
 この `basic_ofstream` オブジェクトを初期化するために使用されている `basic_ofstream` オブジェクトへの右辺値参照。  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターは、[basic_ostream](../standard-library/basic-ostream-class.md)( **sb**) を呼び出すことで基底クラスを初期化します。ここで、**sb** はクラス [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> の格納されているオブジェクトです。 また、`basic_filebuf`< `Elem`, `Tr`> を呼び出すことで **sb** の初期化もします。  
  
 2 番目と 3 番目のコンストラクターは、`basic_ostream`( **sb**) を呼び出すことで基底クラスを初期化します。 **sb** も、`basic_filebuf`< `Elem`, `Tr`> を呼び出し、その後に **sb**. [open](../standard-library/basic-filebuf-class.md#open)( `_Filename`, `_Mode` &#124; `ios_base::out`) を呼び出すことで初期化します。 後者の関数が Null ポインターを返す場合、コンストラクターは [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**) を呼び出します。  
  
 4 番目のコンストラクターは、copy 関数です。 これは、右辺値参照として扱われる `right` のコンテンツでオブジェクトを初期化します。  
  
### <a name="example"></a>例  
  次の例では、`basic_ofstream` オブジェクトを作成して、これにテキストを書き込む方法を示します。  
  
```  
// basic_ofstream_ctor.cpp  
// compile with: /EHsc  
#include <fstream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ofstream ofs("C:\\ofstream.txt");  
    if (!ofs.bad())  
    {  
        ofs << "Writing to a basic_ofstream object..." << endl;  
        ofs.close();  
    }  
}  
```  
  
##  <a name="close"></a>  basic_ofstream::close  
 ファイルを閉じます。  
  
```
void close();
```  
  
### <a name="remarks"></a>コメント  
 メンバー関数の呼び出し[rdbuf](../standard-library/basic-ifstream-class.md#rdbuf)**->**[閉じる](../standard-library/basic-filebuf-class.md#close)です。  
  
### <a name="example"></a>例  
  **close** の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。  
  
##  <a name="is_open"></a>  basic_ofstream::is_open  
 ファイルが開いているかどうかを示します。  
  
```
bool is_open() const;
```  
  
### <a name="return-value"></a>戻り値  
 ファイルが開いている場合は `true`、それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 メンバー関数を返します[rdbuf](#rdbuf)  **->**  [is_open](../standard-library/basic-filebuf-class.md#is_open)です。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_ofstream_is_open.cpp  
// compile with: /EHsc  
#include <fstream>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   ifstream file;  
   // Open and close with a basic_filebuf  
   file.rdbuf( )->open( "basic_ofstream_is_open.txt", ios::in );  
   file.close( );  
   if (file.is_open())  
      cout << "it's open" << endl;  
   else  
      cout << "it's closed" << endl;  
}  
```  
  
##  <a name="open"></a>  basic_ofstream::open  
 ファイルを開きます。  
  
```
void open(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Filename`  
 開くファイルの名前。  
  
 `_Mode`  
 [ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。  
  
 `_Prot`  
 [_fsopen、_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md) の `shflag` パラメーターと同等の既定のファイル保護。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、[rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode` &#124; `ios_base::out`) を呼び出します。 その関数が Null ポインターを返す場合、関数は [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**) を呼び出します。  
  
### <a name="example"></a>例  
  **open** の使用例については、「[basic_filebuf::open](../standard-library/basic-filebuf-class.md#open)」を参照してください。  
  
##  <a name="op_eq"></a>  basic_ofstream::operator=  
 このストリーム オブジェクトの内容を割り当てます。 これは、`rvalue reference` が関係する移動代入で、コピーを残しません。  
  
```
basic_ofstream& operator=(basic_ofstream&& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 `basic_ofstream` オブジェクトへの右辺値参照。  
  
### <a name="return-value"></a>戻り値  
 `*this` を返します。  
  
### <a name="remarks"></a>コメント  
 メンバー演算子により、右辺値の参照として扱われる `right` の内容を使用して、オブジェクトの内容が置き換えられます。  
  
##  <a name="rdbuf"></a>  basic_ofstream::rdbuf  
 格納されたストリーム バッファーのアドレスを返します。  
  
```
basic_filebuf<Elem, Tr> *rdbuf() const
```  
  
### <a name="return-value"></a>戻り値  
 格納されたストリーム バッファーのアドレスを返します。  
  
### <a name="example"></a>例  
  `rdbuf` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。  
  
##  <a name="swap"></a>  basic_ofstream::swap  
 2 つの `basic_ofstream` オブジェクトの内容を交換します。  
  
```
void swap(basic_ofstream& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 別の `basic_ofstream` オブジェクトへの `lvalue` 参照です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、`right` の内容を、このオブジェクトの内容と交換します。  
  
## <a name="see-also"></a>参照  
 [basic_ostream Class](../standard-library/basic-ostream-class.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)



