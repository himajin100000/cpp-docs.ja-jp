---
title: "CToolBarCtrl オブジェクトの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CToolBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e86fad8191c4dea2eed3ae34ec96ed853ac1deae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-ctoolbarctrl-object"></a>CToolBarCtrl オブジェクトの作成
[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)オブジェクトはいくつかの内部データ構造体を含む — ボタン イメージのビットマップの一覧、ボタンのラベルの文字列のリストの一覧`TBBUTTON`構造体 — するイメージを関連付けるや文字列の位置、スタイル、状態、およびボタンのコマンド ID。 これらのデータ構造体の要素のそれぞれは、0 から始まるインデックスによって呼ばれます。 使用する前に、`CToolBarCtrl`オブジェクト、これらのデータ構造を設定する必要があります。 データ構造の一覧は、次を参照してください。[ツール バー コントロール](controls-mfc.md)Windows SDK に含まれています。 文字列の一覧は、ボタンのラベルに対してのみ使用できます。ツールバーから文字列を取得することはできません。  
  
 使用する、`CToolBarCtrl`オブジェクトは通常これらの手順を行います。  
  
### <a name="to-use-a-ctoolbarctrl-object"></a>CToolBarCtrl オブジェクトを使用するには  
  
1.  構築、 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)オブジェクト。  
  
2.  呼び出す[作成](../mfc/reference/ctoolbarctrl-class.md#create)Windows ツール バー コモン コントロールを作成してアタッチする、`CToolBarCtrl`オブジェクト。 ボタン用ビットマップ イメージをする場合、ボタンのビットマップ ツールバーに呼び出すことによって追加[表示](../mfc/reference/ctoolbarctrl-class.md#addbitmap)です。 ボタンの文字列のラベルをする場合、文字列、ツールバーを追加を呼び出して[AddString](../mfc/reference/ctoolbarctrl-class.md#addstring)や[AddStrings](../mfc/reference/ctoolbarctrl-class.md#addstrings)です。 呼び出した後`AddString`や`AddStrings`、呼び出す必要があります[AutoSize](../mfc/reference/ctoolbarctrl-class.md#autosize)または表示する複数の文字列を取得するためにします。  
  
3.  呼び出して、ツールバーにボタンの構造を追加[AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)です。  
  
4.  ツール ヒントを表示する場合は、処理**TTN_NEEDTEXT**ツールバーのオーナー ウィンドウにメッセージが表示」の説明に従って[ツール ヒントの通知の処理](../mfc/handling-tool-tip-notifications.md)です。  
  
5.  ツールバーをカスタマイズすることができるようにする場合は、」の説明に従って、オーナー ウィンドウのカスタマイズの通知メッセージを処理[カスタマイズ通知の処理](../mfc/handling-customization-notifications.md)です。  
  
## <a name="see-also"></a>参照  
 [CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

