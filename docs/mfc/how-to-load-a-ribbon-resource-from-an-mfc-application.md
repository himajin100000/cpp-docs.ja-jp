---
title: '方法: MFC アプリケーションからリボン リソースを読み込む |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a943f82fc9b438a74af3673e0210612183304c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>方法: MFC アプリケーションからリボン リソースを読み込む
アプリケーションでリボン リソースを使用するには、リボン リソースを読み込むアプリケーションを変更します。  
  
### <a name="to-load-a-ribbon-resource"></a>リボン リソースを読み込む  
  
1.  宣言、`Ribbon Control`内のオブジェクト、`CMainFrame`クラスです。  
  
 ```  
    CMFCRibbonBar m_wndRibbonBar;   
 ```  
  
2.  `CMainFrame::OnCreate`を作成し、リボン コントロールを初期化します。  
  
 ```  
    if (!m_wndRibbonBar.Create (this))  
 {  
    return -1;  
 }  
 
    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))  
 {  
    return -1;  
 }  
 ```  
  
## <a name="see-also"></a>参照  
 [リボン デザイナー (MFC)](../mfc/ribbon-designer-mfc.md)

