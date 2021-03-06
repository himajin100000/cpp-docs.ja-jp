---
title: "Module::GenericReleaseNotifier::GenericReleaseNotifier コンス トラクター |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier, constructor
ms.assetid: feb5b687-a4b0-4809-9022-8f292181b7a1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5f6f656ff1908dc215efb1fc322b348618a236d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="modulegenericreleasenotifiergenericreleasenotifier-constructor"></a>Module::GenericReleaseNotifier::GenericReleaseNotifier コンストラクター
Module::genericreleasenotifier クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      GenericReleaseNotifier(  
   T callback,   
   bool release  
) throw() : ReleaseNotifier(release), callback_(callback);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `callback`  
 ラムダ、ファンクタ、またはかっこ関数演算子を呼び出すことができる関数へのポインターのイベント ハンドラー (`()`)。  
  
 `release`  
 指定`true`を基になる呼び出しを有効にする[モジュール:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md)メソッドです。 それ以外の場合、指定`false`です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [Module::GenericReleaseNotifier クラス](../windows/module-genericreleasenotifier-class.md)