---
title: "単純な読み取り専用プロバイダーの向上 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6eb3c583d217e421909236c09ccac6c406cf6a7c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="enhancing-the-simple-read-only-provider"></a>単純な読み取り専用プロバイダーの機能の拡張
このセクションの内容を強化する方法を示しています、[単純な読み取り専用プロバイダー](../../data/oledb/implementing-the-simple-read-only-provider.md)前のセクションで作成します。 `IRowsetLocateImpl` 実装が作成、`IRowsetLocate`インターフェイスし、ブックマーク サポートを追加します。  
  
 プロバイダーがある場合は、ときに、機能を拡張して、トランザクションの処理または行をフェッチするアルゴリズムのパフォーマンスの向上は、プロバイダーの更新を行うことができます。 ほとんどのプロバイダーの機能強化には、既存の COM オブジェクトへのインターフェイスの追加が含まれます。  
  
 次のトピックの例では追加することによって行フェッチのメカニズムの強化、`IRowsetLocate`インターフェイスを`CAgentRowset`です。 トピックが方法を説明します。  
  
-   [RMyProviderRowset IRowsetLocate から継承する](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md)です。  
  
-   [コンシューマーに返される列を動的に決定](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)です。  
  
## <a name="see-also"></a>参照  
 [単純な読み取り専用プロバイダーの作成](../../data/oledb/creating-a-simple-read-only-provider.md)