---
title: ptr::CreateInstance |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- ptr.CreateInstance
- msclr::com::ptr::CreateInstance
- msclr.com.ptr.CreateInstance
- ptr::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- ptr::CreateInstance
ms.assetid: 9e8e4c4c-1651-4839-8829-5857d74470fe
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d764d18f3148dba663e1e6796c44a0add6aa8109
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ptrcreateinstance"></a>ptr::CreateInstance
内の COM オブジェクトのインスタンスを作成、`com::ptr`です。  
  
## <a name="syntax"></a>構文  
  
```  
void CreateInstance(  
   System::String ^ progid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   System::String ^ progid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   System::String ^ progid  
);  
void CreateInstance(  
   const wchar_t * progid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   const wchar_t * progid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   const wchar_t * progid  
);  
void CreateInstance(  
   REFCLSID rclsid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   REFCLSID rclsid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   REFCLSID rclsid  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `progid`  
 `ProgID` 文字列。  
  
 `pouter`  
 集約オブジェクトの IUnknown インターフェイス (controlling IUnknown) へのポインター。 場合`pouter`が指定されていない`NULL`を使用します。  
  
 `cls_context`  
 新しく作成されたオブジェクトを管理するコードを実行するコンテキスト。 値がから取得されます、`CLSCTX`列挙します。 場合`cls_context`が指定されていない値 CLSCTX_ALL が使用されます。  
  
 `rclsid`  
 `CLSID`データとオブジェクトの作成に使用されるコードに関連付けられています。  
  
## <a name="exceptions"></a>例外  
 場合、 `com::ptr` COM オブジェクトへの参照が既に所有して`CreateInstance`スロー<xref:System.InvalidOperationException>です。  
  
 この関数が呼び出す`CoCreateInstance`を使用して<xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>エラーに変換する`HRESULT`適切な例外にします。  
  
## <a name="remarks"></a>コメント  
 `CreateInstance`使用して`CoCreateInstance`ProgID または CLSID のいずれかを識別する、指定したオブジェクトの新しいインスタンスを作成します。 `com::ptr`新しく作成されたオブジェクトを参照し、自動的に破棄後に所有しているすべての参照を解放します。  
  
## <a name="example"></a>例  
 この例を使用して CLR クラスを実装して、`com::ptr`をそのプライベート メンバーをラップする`IXMLDOMDocument`オブジェクト。 クラスのコンス トラクターの 2 つの異なる形式を使用して`CreateInstance`ProgID または CLSID に加えて、CLSCTX からドキュメント オブジェクトを作成します。  
  
```  
// comptr_createinstance.cpp  
// compile with: /clr /link msxml2.lib  
#include <msxml2.h>  
#include <msclr\com\ptr.h>  
  
#import <msxml3.dll> raw_interfaces_only  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
using namespace msclr;  
  
// a ref class that uses a com::ptr to contain an   
// IXMLDOMDocument object  
ref class XmlDocument {  
public:  
   // construct the internal com::ptr with a null interface  
   // and use CreateInstance to fill it  
   XmlDocument(String^ progid) {  
      m_ptrDoc.CreateInstance(progid);     
   }  
   XmlDocument(REFCLSID clsid, DWORD clsctx) {  
      m_ptrDoc.CreateInstance(clsid, NULL, clsctx);  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   try {  
      // create the class from a progid string  
      XmlDocument doc1("Msxml2.DOMDocument.3.0");  
  
      // or from a clsid with specific CLSCTX  
      XmlDocument doc2(CLSID_DOMDocument30, CLSCTX_INPROC_SERVER);  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー ファイル** \<msclr\com\ptr.h >  
  
 **Namespace** msclr::com  
  
## <a name="see-also"></a>参照  
 [ptr のメンバー](../dotnet/ptr-members.md)