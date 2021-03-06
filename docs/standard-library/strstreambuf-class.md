---
title: "strstreambuf クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- strstream/std::strstreambuf::freeze
- strstream/std::strstreambuf::overflow
- strstream/std::strstreambuf::pbackfail
- strstream/std::strstreambuf::pcount
- strstream/std::strstreambuf::seekoff
- strstream/std::strstreambuf::seekpos
- strstream/std::strstreambuf::str
- strstream/std::strstreambuf::underflow
dev_langs:
- C++
helpviewer_keywords:
- std::strstreambuf [C++], freeze
- std::strstreambuf [C++], overflow
- std::strstreambuf [C++], pbackfail
- std::strstreambuf [C++], pcount
- std::strstreambuf [C++], seekoff
- std::strstreambuf [C++], seekpos
- std::strstreambuf [C++], str
- std::strstreambuf [C++], underflow
ms.assetid: b040b8ea-0669-4eba-8908-6a9cc159c54b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 702d5bfa1b01f0207b0745cec030723b25fcfe6f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="strstreambuf-class"></a>strstreambuf クラス
`char` 配列オブジェクトに格納されている要素のシーケンスとの間で行う、要素の送信を制御するストリーム バッファーを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class strstreambuf : public streambuf  
```  
  
## <a name="remarks"></a>コメント  
 オブジェクトの構築方法に応じて、シーケンスにおける変更に対応できるように割り当て、拡張、解放を必要に応じて行えます。  
  
 クラス `strstreambuf` のオブジェクトは、`strstreambuf` モードのモード情報が入っているいくつかのビットを格納します。 これらのビットは、制御対象シーケンスに関して次の情報を示します。  
  
-   割り当てがなされていて、最終的に解放する必要があるかどうか。  
  
-   変更可能かどうか。  
  
-   記憶域の再割り当てによって拡張可能かどうか。  
  
-   操作できないようにされていて、オブジェクトを破棄する前に操作できるようにする必要があるかどうか、またはオブジェクト以外のエージェンシーで解放する必要があるかどうか (割り当てがなされている場合)。  
  
 操作できないようにされている制御対象シーケンスは、これらの別個のモード ビットに関係なく、変更も拡張もできません。  
  
 またオブジェクトは、`strstreambuf` 割り当てを制御する 2 つの関数へのポインターも格納します。 これらが null ポインターである場合、オブジェクトは制御対象シーケンスに対して記憶域の割り当ておよび解放を行う独自のメソッドを考案します。  
  
> [!NOTE]
>  このクラスは使用されていません。 代わりに [stringbuf](../standard-library/sstream-typedefs.md#stringbuf) または [wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf) を使用することを検討してください。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[strstreambuf](#strstreambuf)|`strstreambuf` 型のオブジェクトを構築します。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[freeze](#freeze)|ストリーム バッファーの操作により、ストリーム バッファーを使用不可にします。|  
|[overflow](#overflow)|いっぱいのバッファーに新しい文字が挿入されたときに呼び出すことができる、プロテクト仮想関数。|  
|[pbackfail](#pbackfail)|要素を入力ストリームに戻してから、その要素を現在の要素 (ネクスト ポインターによって指される) にしようとするプロテクト仮想メンバー関数。|  
|[pcount](#pcount)|被制御シーケンスに書き込まれる要素の数を返します。|  
|[seekoff](#seekoff)|制御対象ストリームの現在の位置を変更しようと試みるプロテクト仮想メンバー関数。|  
|[seekpos](#seekpos)|制御対象ストリームの現在の位置を変更しようと試みるプロテクト仮想メンバー関数。|  
|[str](#str)|[freeze](#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。|  
|[underflow](#underflow)|入力ストリームから現在の要素を抽出するプロテクト仮想関数。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<strstream>  
  
 **名前空間:** std  
  
##  <a name="freeze"></a>  strstreambuf::freeze  
 ストリーム バッファーの操作により、ストリーム バッファーを使用不可にします。  
  
```  
void freeze(bool _Freezeit = true);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Freezeit`  
 ストリームを停止させるかどうか示す `bool`。  
  
### <a name="remarks"></a>コメント  
 `_Freezeit` が true の場合、この関数によって格納されている `strstreambuf` モードが変更され、被制御シーケンスが固定されます。 それ以外の場合、被制御シーケンスは固定されません。  
  
 [str](#str) は `freeze` を意味します。  
  
> [!NOTE]
>  固定されたバッファーは、`strstreambuf` の破棄中には解放されません。 メモリ リークを避けるために、バッファーを解放する前に固定解除する必要があります。  
  
### <a name="example"></a>例  
  
```cpp  
// strstreambuf_freeze.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <strstream>  
  
using namespace std;  
  
void report(strstream &x)  
{  
    if (!x.good())  
        cout << "stream bad" << endl;  
    else  
        cout << "stream good" << endl;  
}  
  
int main()  
{  
    strstream x;  
  
    x << "test1";  
    cout << "before freeze: ";  
    report(x);  
  
    // Calling str freezes stream.  
    cout.write(x.rdbuf()->str(), 5) << endl;  
    cout << "after freeze: ";  
    report(x);  
  
    // Stream is bad now, wrote on frozen stream  
    x << "test1.5";  
    cout << "after write to frozen stream: ";  
    report(x);  
  
    // Unfreeze stream, but it is still bad  
    x.rdbuf()->freeze(false);  
    cout << "after unfreezing stream: ";  
    report(x);  
  
    // Clear stream  
    x.clear();  
    cout << "after clearing stream: ";  
    report(x);  
  
    x << "test3";  
    cout.write(x.rdbuf()->str(), 10) << endl;  
  
    // Clean up.  Failure to unfreeze stream will cause a  
    // memory leak.  
    x.rdbuf()->freeze(false);  
}  
```  
  
```Output  
before freeze: stream good  
test1  
after freeze: stream good  
after write to frozen stream: stream bad  
after unfreezing stream: stream bad  
after clearing stream: stream good  
test1test3  
```  
  
##  <a name="overflow"></a>  strstreambuf::overflow  
 いっぱいのバッファーに新しい文字が挿入されたときに呼び出すことができる、プロテクト仮想関数。  
  
```  
virtual int overflow(int _Meta = EOF);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Meta`  
 バッファーに挿入する文字または `EOF`。  
  
### <a name="return-value"></a>戻り値  
 関数が成功しない場合は、`EOF` が返されます。 それ以外の場合、_ *Meta* == `EOF` の場合に `EOF` 以外の値が返されます。 それ以外の場合は、\_ *Meta* が返されます。  
  
### <a name="remarks"></a>コメント  
 _ *Meta* != `EOF` の場合、プロテクト仮想メンバー関数は要素 ( `char`)\_ *Meta* を出力バッファーに挿入しようとします。 これはさまざまな方法で行うことができます。  
  
-   書き込み位置が使用可能な場合は、書き込み位置に要素を格納し、出力バッファーの次のポインターをインクリメントできます。  
  
-   格納されている strstreambuf モードによって被制御シーケンスが変更可能、拡張可能で、固定されていないことが示されている場合、この関数は出力バッファーに新規に割り当てることによって書き込み位置を使用可能にできます。 このように出力バッファーを拡張すると、関連付けられているすべての入力バッファーも拡張されます。  
  
##  <a name="pbackfail"></a>  strstreambuf::pbackfail  
 要素を入力ストリームに戻してから、その要素を現在の要素に (次のポインターによって指されるように) しようとするプロテクト仮想メンバー関数。  
  
```  
virtual int pbackfail(int _Meta = EOF);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Meta`  
 バッファーに挿入する文字または `EOF`。  
  
### <a name="return-value"></a>戻り値  
 関数が成功しない場合は、`EOF` が返されます。 それ以外の場合、_ *Meta* == `EOF` の場合に `EOF` 以外の値が返されます。 それ以外の場合は、\_ *Meta* が返されます。  
  
### <a name="remarks"></a>コメント  
 プロテクト仮想メンバー関数が要素を入力バッファーに戻そうと試み、その要素を現在の要素に (次のポインターによって指されるように) します。  
  
 _ *Meta* == `EOF` の場合、プッシュ バックする要素は、実質的に、現在の要素の前に既にストリームにある要素になります。 それ以外の場合、この要素は **ch** = ( `char`)\_ *Meta* によって置き換えられます。 この関数は、さまざまな方法で要素を戻すことができます。  
  
-   戻り位置が使用可能であり、格納されている要素が **ch** に等しい場合、入力バッファーの次のポインターをデクリメントできます。  
  
-   戻り位置が使用可能であり、strstreambuf モードによって被制御シーケンスが変更可能であることが示されている場合、この関数は **ch** を戻り位置に格納し、入力バッファーの次のポインターをデクリメントできます。  
  
##  <a name="pcount"></a>  strstreambuf::pcount  
 被制御シーケンスに書き込まれる要素の数を返します。  
  
```  
streamsize pcount() const;
```  
  
### <a name="return-value"></a>戻り値  
 被制御シーケンスに書き込まれる要素の数。  
  
### <a name="remarks"></a>コメント  
 具体的には、[pptr](../standard-library/basic-streambuf-class.md#pptr) が Null ポインターの場合、この関数はゼロを返します。 返しますそれ以外の場合、 `pptr`  -  [pbase](../standard-library/basic-streambuf-class.md#pbase)です。  
  
### <a name="example"></a>例  
  
```cpp  
// strstreambuf_pcount.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <strstream>  
using namespace std;  
  
int main( )  
{  
   strstream x;  
   x << "test1";  
   cout << x.rdbuf( )->pcount( ) << endl;  
   x << "test2";  
   cout << x.rdbuf( )->pcount( ) << endl;  
}  
```  
  
##  <a name="seekoff"></a>  strstreambuf::seekoff  
 制御対象ストリームの現在の位置を変更しようと試みるプロテクト仮想メンバー関数。  
  
```  
virtual streampos seekoff(streamoff _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Off`  
 シークする `_Way` の相対位置。  
  
 `_Way`  
 オフセット演算の開始位置。 有効値については、「[seekdir](../standard-library/ios-base-class.md#seekdir)」を参照してください。  
  
 `_Which`  
 ポインター位置のモードを指定します。 既定では、読み取り位置および書き込み位置を変更できます。  
  
### <a name="return-value"></a>戻り値  
 いずれかまたは両方のストリームの位置を変更することで、関数が成功すると、結果のストリームの位置が返されます。 それ以外の場合は、失敗し、無効なストリームの位置が返されます。  
  
### <a name="remarks"></a>コメント  
 プロテクト仮想メンバー関数が、制御対象ストリームの現在の位置を変更しようと試みます。 クラス strstreambuf のオブジェクトの場合、ストリームの位置がストリーム オフセットのみで構成されます。 オフセット ゼロは、被制御シーケンスの最初の要素を指定します。  
  
 新しい位置は、次のように判断されます。  
  
-   `_Way` == `ios_base::beg` の場合、新しい位置はストリームの先頭と _ *Off* です。  
  
-   `_Way` == `ios_base::cur` の場合、新しい位置は現在のストリームの位置と _ *Off* です。  
  
-   `_Way` == `ios_base::end` の場合、新しい位置はストリームの最後と _ *Off* です。  
  
 `_Which` & **ios_base::in** が 0 以外であり、入力バッファーが存在する場合、この関数は次の位置を変更して入力バッファーに読み取ります。 `_Which` & **ios_base::out** も 0 以外であり、`_Way` != **ios_base::cur** で、出力バッファーが存在する場合、この関数は、次の位置を設定して読み取る次の位置に一致するように書き込みます。  
  
 それ以外の場合、`_Which` & `ios_base::out` が 0 以外であり、出力バッファーが存在する場合、この関数は次の位置を変更して出力バッファーに書き込みます。 それ以外の場合、配置操作が失敗します。 配置操作を正常に完了するためには、結果のストリームの位置が被制御シーケンス内になければなりません。  
  
##  <a name="seekpos"></a>  strstreambuf::seekpos  
 制御対象ストリームの現在の位置を変更しようと試みるプロテクト仮想メンバー関数。  
  
```  
virtual streampos seekpos(streampos _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Sp`  
 シークする位置。  
  
 `_Which`  
 ポインター位置のモードを指定します。 既定では、読み取り位置および書き込み位置を変更できます。  
  
### <a name="return-value"></a>戻り値  
 いずれかまたは両方のストリームの位置を変更することで、関数が成功すると、結果のストリームの位置が返されます。 それ以外の場合は、失敗し、無効なストリームの位置が返されます。 ストリームの位置が無効であることを確認するには、戻り値と `pos_type(off_type(-1))` を比較します。  
  
### <a name="remarks"></a>コメント  
 プロテクト仮想メンバー関数が、制御対象ストリームの現在の位置を変更しようと試みます。 クラス strstreambuf のオブジェクトの場合、ストリームの位置がストリーム オフセットのみで構成されます。 オフセット ゼロは、被制御シーケンスの最初の要素を指定します。 新しい位置は、_ *Sp* によって判断されます。  
  
 `_Which` & **ios_base::in** が 0 以外であり、入力バッファーが存在する場合、この関数は次の位置を変更して入力バッファーに読み取ります。 `_Which` & `ios_base::out` が 0 以外であり、出力バッファーが存在する場合、この関数は、次の位置を設定して読み取る次の位置に一致するように書き込みます。 それ以外の場合、`_Which` & `ios_base::out` が 0 以外であり、出力バッファーが存在する場合、この関数は次の位置を変更して出力バッファーに書き込みます。 それ以外の場合、配置操作が失敗します。 配置操作を正常に完了するためには、結果のストリームの位置が被制御シーケンス内になければなりません。  
  
##  <a name="str"></a>  strstreambuf::str  
 [freeze](#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。  
  
```  
char *str();
```  
  
### <a name="return-value"></a>戻り値  
 被制御シーケンスの先頭へのポインター。  
  
### <a name="remarks"></a>コメント  
 明示的に挿入しない場合、終端の null 要素は存在しません。  
  
### <a name="example"></a>例  
  **str** の使用例は、「[strstreambuf::freeze](#freeze)」を参照してください。  
  
##  <a name="strstreambuf"></a>  strstreambuf::strstreambuf  
 `strstreambuf` 型のオブジェクトを構築します。  
  
```  
explicit strstreambuf(streamsize count = 0);

strstreambuf(void (* _Allocfunc)(size_t),
    void (* _Freefunc)(void*));

strstreambuf(char* _Getptr,
    streamsize count,
    char* _Putptr = 0);

strstreambuf(signed char* _Getptr,
    streamsize count,
    signed char* _Putptr = 0);

strstreambuf(unsigned char* _Getptr,
    streamsize count,
    unsigned char* _Putptr = 0);

strstreambuf(const char* _Getptr,
    streamsize count);

strstreambuf(const signed char* _Getptr,
    streamsize count);

strstreambuf(const unsigned char* _Getptr,
    streamsize count);
```  
  
### <a name="parameters"></a>パラメーター  
 *_Allocfunc*  
 バッファー メモリの割り当てに使用される関数。  
  
 `count`  
 `_Getptr` で指し示されるバッファーの長さを指定します。 `_Getptr` が引数ではない場合 (最初のコンストラクター フォーム)、バッファーの割り当てサイズの提案。  
  
 *_Freefunc*  
 バッファー メモリを解放するために使用する関数。  
  
 `_Getptr`  
 入力に使用するバッファー。  
  
 `_Putptr`  
 出力に使用するバッファー。  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターは、入力バッファー、出力バッファー、および strstreambuf 割り当てを制御するすべてのポインターに Null ポインターを格納します。 被制御シーケンスを変更および拡張できるように、ストアド strstreambuf モードに設定します。 また、提案される初期割り当てサイズとして `count` を受け入れます。  
  
 2 番目のコンストラクターは、ストレージを割り当てるために呼び出す関数へのポインターとしての _ *Allocfunc* と、ストレージを解放するために呼び出す関数へのポインターとしての \_ *Freefunc* を格納する点を除いて、最初のコンストラクターのように動作します。  
  
 3 つのコンストラクター:  
  
```  
strstreambuf(char *_Getptr,
    streamsize count,  
    char *putptr = 0);
  
strstreambuf(signed char *_Getptr,
    streamsize count,  
    signed char *putptr = 0);
  
strstreambuf(unsigned char *_Getptr,
    streamsize count,  
    unsigned char *putptr = 0);
```  
  
 これらは、`_Getptr` が被制御シーケンスを保持するために使用する配列オブジェクトを指定する点を除いて、最初のコンストラクターのように動作します。 (したがって、Null ポインターにすることはできません。)配列内の要素の数 *N* は、次のように決定されます。  
  
-   場合 (`count` > 0)、し*N*は`count`します。  
  
-   場合 (`count` = = 0)、し*N*は`strlen`(( **const** `char` *) `_Getptr` )。  
  
-   場合 (`count` < 0)、し*N*は**INT_MAX**です。  
  
 `_Putptr` が Null ポインターの場合、関数は次を実行することによって入力バッファーだけを確立します。  
  
```  
setg(_Getptr,
    _Getptr,
    _Getptr + N);
```  
  
 それ以外の場合、次を実行することによって入力と出力の両方のバッファーを確立します。  
  
```  
setg(_Getptr,
    _Getptr,
    _Putptr);

setp(_Putptr,
    _Getptr + N);
```  
  
 この場合、`_Putptr` は間隔 [ `_Getptr`, `_Getptr` + *N*] 内である必要があります。  
  
 最後に、3 つのコンストラクターを示します。  
  
```  
strstreambuf(const char *_Getptr,
    streamsize count);

strstreambuf(const signed char *_Getptr,
    streamsize count);

strstreambuf(const unsigned char *_Getptr,
    streamsize count);
```  
  
 すべて次と同様に動作します。  
  
```  
streambuf((char *)_Getptr, count);
```  
  
 ストアド モードによって被制御シーケンスが変更可能にも拡張可能にもならない点を除きます。  
  
##  <a name="underflow"></a>  strstreambuf::underflow  
 入力ストリームから現在の要素を抽出するプロテクト仮想関数。  
  
```  
virtual int underflow();
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功しない場合は、`EOF` が返されます。 それ以外の場合、上記のように変換された入力ストリームの現在の要素が返されます。  
  
### <a name="remarks"></a>コメント  
 現在の要素を抽出するプロテクト仮想メンバー関数がよう努めて**ch**は入力バッファーから現在のストリームの位置を進めるととしての要素を返します (`int`) (`unsigned char`) **ch**. これは 1 つの方法でのみ実行可能です。読み取り位置が使用可能な場合は、読み取り位置に格納されている要素として **ch** を使用し、入力バッファーの次のポインターを進めます。  
  
## <a name="see-also"></a>参照  
 [streambuf](../standard-library/streambuf-typedefs.md#streambuf)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)

