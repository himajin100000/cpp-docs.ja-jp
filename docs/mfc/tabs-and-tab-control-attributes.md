---
title: "タブおよびタブの属性を制御します |。Microsoft ドキュメント"
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
- attributes [MFC], reference topics
- tab controls [MFC], attributes
- tabs [MFC]
- tabs [MFC], attributes
- CTabCtrl class [MFC], tab control attributes
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d10db5f1282c726b30536be35b348d50c8bb4a14
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tabs-and-tab-control-attributes"></a>タブおよびタブ コントロールの属性
タブ コントロールを構成するタブの動作と外観を細かく制御がある ([CTabCtrl](../mfc/reference/ctabctrl-class.md))。 各タブには、ラベル、アイコン、項目の状態、および関連付けられている、アプリケーションで定義された 32 ビット値を持つことができます。 各タブには、アイコン、ラベル、またはその両方を表示できます。  
  
 さらに、各タブの項目が 3 つの状態を持つことができます: 押された、元の状態、または強調表示されます。 この状態は、既存のタブ項目を変更することによってのみ設定できます。 既存のタブ項目を変更するへの呼び出しで取得[GetItem](../mfc/reference/ctabctrl-class.md#getitem)、変更、`TCITEM`構造 (具体的には、 **dwState**と**dwStateMask**データ メンバー)、し、変更された返す`TCITEM`への呼び出しを含む構造体[SetItem](../mfc/reference/ctabctrl-class.md#setitem)です。 内のすべてのタブ項目の項目の状態をクリアする必要があるかどうか、`CTabCtrl`オブジェクト、呼び出しを行う[DeselectAll](../mfc/reference/ctabctrl-class.md#deselectall)です。 この関数は、すべてのタブ項目または現在選択されている 1 つを除くすべての項目の状態をリセットします。  
  
 次のコードでは、すべてのタブ項目の状態を解除し、3 番目の項目の状態を変更します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/cpp/tabs-and-tab-control-attributes_1.cpp)]  
  
 タブの属性の詳細については、次を参照してください。[タブおよびタブ属性](http://msdn.microsoft.com/library/windows/desktop/bb760550)Windows SDK に含まれています。 タブ コントロールにタブを追加する方法の詳細については、次を参照してください。[タブ コントロールに追加するタブ](../mfc/adding-tabs-to-a-tab-control.md)このトピックで後述します。  
  
## <a name="see-also"></a>参照  
 [CTabCtrl の使い方](../mfc/using-ctabctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

