---
title: "コンパイラ エラー C2592 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2592
dev_langs:
- C++
helpviewer_keywords:
- C2592
ms.assetid: 833a4d7b-66ef-4d4c-ae83-a533c2b0eb07
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3528354797987b47379d0ec56e103223ac87892f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2592"></a>コンパイラ エラー C2592
'class': 'base_class_2' は、'base_class_1' から継承されるので、再指定することはできません  
  
 他の基底クラスから継承していない基底クラスのみを指定できます。 この場合は、`base_class_1` が既に `base_class_2` を継承しているため、`class` の指定で必要になるのは `base_class_1` のみです。