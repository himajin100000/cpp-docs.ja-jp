---
title: Module::genericreleasenotifier クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier class
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f867b0cff559ead40be9b2e3ff0722fdb9943034
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier クラス
現在のモジュールの最後のオブジェクトを解放すると、イベント ハンドラーを呼び出します。 イベント ハンドラーは、ラムダ、ファンクタ、または関数へのポインターによって指定されます。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T>  
class GenericReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 イベント ハンドラーの場所が含まれているデータ メンバーの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::GenericReleaseNotifier コンストラクター](../windows/module-genericreleasenotifier-genericreleasenotifier-constructor.md)|Module::genericreleasenotifier クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::Invoke メソッド](../windows/module-genericreleasenotifier-invoke-method.md)|Module::genericreleasenotifier の現在のオブジェクトに関連付けられているイベント ハンドラーを呼び出します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::callback_ データ メンバー](../windows/module-genericreleasenotifier-callback-data-member.md)|ラムダ、ファンクタ、または現在の module::genericreleasenotifier オブジェクトに関連付けられている関数へのポインターのイベント ハンドラーが保持されます。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ReleaseNotifier`  
  
 `GenericReleaseNotifier`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)