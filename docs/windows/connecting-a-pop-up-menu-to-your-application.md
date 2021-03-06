---
title: "ポップアップ メニューをアプリケーションに接続する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- pop-up menus, connecting to applications
- context menus, connecting to applications
- menus, pop-up
- shortcut menus, connecting to applications
ms.assetid: 295cbf0e-6416-478e-bc3d-472fb98e0e52
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2e04a2d042c3bfa9fc10bb1a5e79bd2b22134ea4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="connecting-a-pop-up-menu-to-your-application"></a>ショートカット メニューとアプリケーションの関連付け
### <a name="to-connect-a-pop-up-menu-to-your-application"></a>ショートカット メニューをアプリケーションに関連付けるには  
  
1.  (たとえば) WM_CONTEXTMENU のメッセージ ハンドラーを追加します。 詳細については、次を参照してください。[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md)です。  
  
2.  次のコードをメッセージ ハンドラーに追加します。  
  
    ```  
    CMenu menu;  
    VERIFY(menu.LoadMenu(IDR_MENU1));  
    CMenu* pPopup = menu.GetSubMenu(0);  
    ASSERT(pPopup != NULL);  
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());  
    ```  
  
    > [!NOTE]
    >  [CPoint](../atl-mfc-shared/reference/cpoint-class.md) **渡されるでメッセージ ハンドラーは、画面座標。**  
  

  
 **必要条件**  
  
 MFC  
  
## <a name="see-also"></a>参照  
 [ポップアップ メニューを作成します。](../windows/creating-pop-up-menus.md)   
 [メニュー エディター](../windows/menu-editor.md)   
