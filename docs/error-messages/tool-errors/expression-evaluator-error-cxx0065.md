---
title: "式エバリュエーター エラー CXX0065 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0065
dev_langs:
- C++
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: db01baa10191df50c1f319bf8320263657088d75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0065"></a>式エバリュエーター エラー CXX0065
変数には、スタック フレームが必要です。  
  
 式には、現在のスコープ内に存在するが、まだ作成されていない変数が含まれています。  
  
 このエラーは、関数がされていない関数では、スタック フレームのセットアップのプロローグにステップ インするとき、または関数の終了コードにステップ インした場合に発生することができます。  
  
 式を評価する前に設定されているスタック フレームまでプロローグ コードをステップ実行します。  
  
 このエラーは、can0065 と同じものと同じです。