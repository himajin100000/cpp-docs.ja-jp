---
title: "複合コントロールへの機能の追加 |Microsoft ドキュメント"
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
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6dcf3ffa0c3168c2f96a3ad9bed13ab1213f63da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="adding-functionality-to-the-composite-control"></a>複合コントロールへの機能の追加
複合コントロールに必要なコントロールを挿入した後、次の手順には、新しい機能の追加が含まれます。 この新しい機能は、通常、2 つのカテゴリに分類されます。  
  
-   追加のインターフェイスをサポートして、特定の機能による複合コントロールの動作をカスタマイズします。  
  
-   格納されている ActiveX コントロール (またはコントロール) からのイベントを処理します。  
  
 目的とこの記事の範囲は、このセクションの残りの部分は ActiveX コントロールからのイベントの処理についてのみ説明します。  
  
> [!NOTE]
>  Windows のコントロールからのメッセージを処理する必要がある場合は、次を参照してください[ウィンドウの実装](../atl/implementing-a-window.md)メッセージ atl の処理の詳細について。  
  
 ActiveX コントロールをダイアログ リソースを挿入した後、コントロールを右クリックし、をクリックして**イベント ハンドラーの追加**です。 イベントを処理し、をクリックする選択**の追加し、編集**です。 イベント ハンドラーのコードは、コントロールの .h ファイルに追加されます。  
  
 複合コントロールの ActiveX コントロールの接続ポイントが自動的に接続されへの呼び出しを使用して切断[CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)です。  
  
## <a name="see-also"></a>参照  
 [複合コントロールの基本](../atl/atl-composite-control-fundamentals.md)

