---
title: "CMFCBaseToolBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCBaseToolBar
- AFXBASETOOLBAR/CMFCBaseToolBar
- AFXBASETOOLBAR/CMFCBaseToolBar::GetDockingMode
- AFXBASETOOLBAR/CMFCBaseToolBar::GetMinSize
- AFXBASETOOLBAR/CMFCBaseToolBar::OnAfterChangeParent
dev_langs:
- C++
helpviewer_keywords:
- CMFCBaseToolBar [MFC], GetDockingMode
- CMFCBaseToolBar [MFC], GetMinSize
- CMFCBaseToolBar [MFC], OnAfterChangeParent
ms.assetid: 5d79206d-55e4-46f8-b1b8-042e34d7f9da
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c57a09465a342a74e69d199d725ec64e7c60ca2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcbasetoolbar-class"></a>CMFCBaseToolBar クラス
ツールバーの基本クラス。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCBaseToolBar : public CPane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCBaseToolBar::CMFCBaseToolBar`|既定のコンストラクター|  
|`CMFCBaseToolBar::~CMFCBaseToolBar`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCBaseToolBar::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCBaseToolBar::GetDockingMode](#getdockingmode)|ドッキングのモードを返します。 (上書き[cbasepane::getdockingmode](../../mfc/reference/cbasepane-class.md#getdockingmode))。|  
|[CMFCBaseToolBar::GetMinSize](#getminsize)|ツールバーの最小サイズを返します。 (上書き[CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize))。|  
|[CMFCBaseToolBar::OnAfterChangeParent](#onafterchangeparent)|ウィンドウの親の変更後に、フレームワークによって呼び出されます。 (上書き[CBasePane::OnAfterChangeParent](../../mfc/reference/cbasepane-class.md#onafterchangeparent))。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxbasetoolbar.h  
  
##  <a name="getdockingmode"></a>CMFCBaseToolBar::GetDockingMode  
 ドッキングのモードを返します。  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドッキングのモードです。  
  
##  <a name="getminsize"></a>CMFCBaseToolBar::GetMinSize  
 ツールバーの最小サイズを返します。  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `size`  
 ツールバーの最小サイズ。  
  
##  <a name="onafterchangeparent"></a>CMFCBaseToolBar::OnAfterChangeParent  
 ウィンドウの親の変更後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndOldParent`  
 前の親ウィンドウへのポインター。  
  
## <a name="see-also"></a>参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
