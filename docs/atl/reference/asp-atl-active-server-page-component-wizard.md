---
title: "ASP、ATL Active Server Page コンポーネント ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.asp.asp
dev_langs:
- C++
helpviewer_keywords:
- ATL Active Server Page Component Wizard, ASP
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69d3837cc0996c0e0e0784214cfbfa6744afbf94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="asp-atl-active-server-page-component-wizard"></a>ASP、ATL Active Server Page コンポーネント ウィザード
ATL Active Server Page コンポーネント ウィザードのこのページを使用すると、情報と、ASP のコンポーネントに関連する状態を処理するためのオプションの設定を指定できます。  
  
 **省略可能なメソッド**  
 ASP のオプションのメソッドを追加**OnStartPage**と**OnEndPage**オブジェクトにします。 Active Server Pages の組み込みオブジェクトを設定するには、このオプションを選択してください。 既定では、選択されています。  
  
-   **OnStartPage または OnEndPage** [OnStartPage](https://msdn.microsoft.com/library/ms691624.aspx)スクリプトが、オブジェクトにアクセスしようとしています。 最初に呼び出されます。 **OnEndPage**オブジェクトが完了したときに呼び出されるスクリプトを処理します。  
  
 **組み込みオブジェクト**  
 選択する必要があります、 **OnStartPage または OnEndPage** ASP 組み込みオブジェクトを設定するオプションです。  
  
|オプション|説明|  
|------------|-----------------|  
|**要求**|組み込みの Active Server Pages にアクセスできるように**要求**オブジェクト。 要求オブジェクトを使用して、HTTP 要求を渡します。|  
|**応答**|組み込みの Active Server Pages にアクセスできるように**応答**オブジェクト。 要求に応答してでは、応答オブジェクトは、情報をユーザーに表示するには、ブラウザーに送信します。|  
|**セッション**|組み込みの Active Server Pages にアクセスできるように**セッション**オブジェクト。 **セッション**オブジェクトが格納する、状態情報を取得するなど、現在のユーザー セッションに関する情報を保持します。|  
|**アプリケーション**|組み込みの Active Server Pages にアクセスできるように**アプリケーション**オブジェクト。 **アプリケーション**オブジェクトが複数の ASP オブジェクトで共有される状態を管理します。|  
|**サーバー**|組み込みの Active Server Pages にアクセスできるように**サーバー**オブジェクト。 **サーバー**オブジェクトでは、その他の ASP オブジェクトを作成することができます。|  
  
## <a name="see-also"></a>参照  
 [ATL Active Server Page コンポーネント ウィザード](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server Page コンポーネント](../../atl/reference/adding-an-atl-active-server-page-component.md)

