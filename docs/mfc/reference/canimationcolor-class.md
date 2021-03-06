---
title: "CAnimationColor クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationColor [MFC], CAnimationColor
- CAnimationColor [MFC], AddTransition
- CAnimationColor [MFC], GetB
- CAnimationColor [MFC], GetDefaultValue
- CAnimationColor [MFC], GetG
- CAnimationColor [MFC], GetR
- CAnimationColor [MFC], GetValue
- CAnimationColor [MFC], SetDefaultValue
- CAnimationColor [MFC], GetAnimationVariableList
- CAnimationColor [MFC], m_bValue
- CAnimationColor [MFC], m_gValue
- CAnimationColor [MFC], m_rValue
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd6ec3b6d8ee6a37fbe189ff70a2a633cfda9c8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="canimationcolor-class"></a>CAnimationColor クラス
赤、緑、および青の各色要素をアニメーション化できる機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationColor::CAnimationColor](#canimationcolor)|オーバーロードされます。 アニメーション カラー オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationColor::AddTransition](#addtransition)|赤、緑、および青のコンポーネントの遷移を追加します。|  
|[CAnimationColor::GetB](#getb)|青の要素を表す CAnimationVariable へのアクセスを提供します。|  
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|色要素の既定値を返します。|  
|[CAnimationColor::GetG](#getg)|緑の成分を表す CAnimationVariable へのアクセスを提供します。|  
|[CAnimationColor::GetR](#getr)|赤の要素を表す CAnimationVariable へのアクセスを提供します。|  
|[CAnimationColor::GetValue](#getvalue)|現在の値を返します。|  
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|既定値を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|一覧にカプセル化されたアニメーション変数を追加します。 (上書き[CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist))。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationColor::operator COLORREF](#operator_colorref)||  
|[CAnimationColor::operator =](#operator_eq)|CAnimationColor に色を割り当てます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CAnimationColor::m_bValue](#m_bvalue)|アニメーションの色の青の要素を表すアニメーションをカプセル化された変数です。|  
|[CAnimationColor::m_gValue](#m_gvalue)|アニメーションの色の緑の成分を表すアニメーションをカプセル化された変数です。|  
|[CAnimationColor::m_rValue](#m_rvalue)|アニメーションの色の赤の要素を表すアニメーションをカプセル化された変数です。|  
  
## <a name="remarks"></a>コメント  
 CAnimationColor クラスは、3 つの CAnimationVariable オブジェクトをカプセル化し、色のアプリケーションで表すことができます。 たとえば、画面上の任意のオブジェクトの色をアニメーション化するこのクラスを使用できます (テキストの色のように背景色など)。 アプリケーションでこのクラスを使用するには、このクラスのオブジェクトをインスタンス化、CAnimationController::AddAnimationObject を使用してアニメーション コント ローラーに追加してだけ赤、緑、および青のコンポーネントに適用される各移行につき AddTransition の呼び出しです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationColor`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationColor::AddTransition  
 赤、緑、および青のコンポーネントの遷移を追加します。  
  
```  
void AddTransition(
    CBaseTransition* pRTransition,  
    CBaseTransition* pGTransition,  
    CBaseTransition* pBTransition);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRTransition`  
 赤の成分に移行します。  
  
 `pGTransition`  
 緑の成分に移行します。  
  
 `pBTransition`  
 青の成分に移行します。  
  
### <a name="remarks"></a>コメント  
 アニメーション変数の色要素を表すには適用への遷移の内部リストに指定された遷移を追加するには、この関数を呼び出します。 切り替え効果を追加すると、いないすぐに適用されるとなり、内部の一覧に格納されています。 遷移を (特定の値のストーリー ボードへの追加) に適用されます CAnimationController::AnimateGroup を呼び出すとします。 色の要素のいずれかに遷移を適用する必要としない場合は、NULL を渡すことができます。  
  
##  <a name="canimationcolor"></a>CAnimationColor::CAnimationColor  
 CAnimationColor オブジェクトを構築します。  
  
```  
CAnimationColor();
 
CAnimationColor(
    COLORREF color,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `color`  
 既定の色を指定します。  
  
 `nGroupID`  
 グループ ID を指定します  
  
 `nObjectID`  
 オブジェクト ID を指定します  
  
 `dwUserData`  
 ユーザー定義データを指定します。  
  
### <a name="remarks"></a>コメント  
 既定値を赤、緑、青、オブジェクト ID とグループの ID を 0 に設定されますには、オブジェクトを構築します。 これらは、SetDefaultValue および SetID を使用して実行時に後で変更することができます。  
  
##  <a name="getanimationvariablelist"></a>CAnimationColor::GetAnimationVariableList  
 一覧にカプセル化されたアニメーション変数を追加します。  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>パラメーター  
 `lst`  
 関数から返されたときに、赤、緑、青のコンポーネントを表す 3 つの CAnimationVariable オブジェクトへのポインターを格納します。  
  
##  <a name="getb"></a>CAnimationColor::GetB  
 青の要素を表す CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetB();
```  
  
### <a name="return-value"></a>戻り値  
 青の要素を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>コメント  
 青の要素を表す、基になる CAnimationVariable に直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="getdefaultvalue"></a>CAnimationColor::GetDefaultValue  
 色要素の既定値を返します。  
  
```  
COLORREF GetDefaultValue();
```  
  
### <a name="return-value"></a>戻り値  
 RGB コンポーネントの既定値を含む COLORREF 値です。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターまたは SetDefaultValue で以前に設定された既定値を取得するには、この関数を呼び出します。  
  
##  <a name="getg"></a>CAnimationColor::GetG  
 緑の成分を表す CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetG();
```  
  
### <a name="return-value"></a>戻り値  
 カプセル化された CAnimationVariable を表す緑の要素への参照。  
  
### <a name="remarks"></a>コメント  
 基になる CAnimationVariable を表す緑の要素に直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="getr"></a>CAnimationColor::GetR  
 赤の要素を表す CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetR();
```  
  
### <a name="return-value"></a>戻り値  
 赤の要素を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>コメント  
 赤の要素を表す、基になる CAnimationVariable に直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="getvalue"></a>CAnimationColor::GetValue  
 現在の値を返します。  
  
```  
BOOL GetValue(COLORREF& color);
```  
  
### <a name="parameters"></a>パラメーター  
 `color`  
 出力です。 このメソッドが戻るとき、現在の値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 現在の値の取得が成功した場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 アニメーションの色の現在の値を取得するには、この関数を呼び出します。 このメソッドが失敗した、または色の要素の基になる COM オブジェクトが初期化されていない、色には、コンス トラクターまたは SetDefaultValue によって設定されている既定値が含まれています。  
  
##  <a name="m_bvalue"></a>CAnimationColor::m_bValue  
 アニメーションの色の青の要素を表すアニメーションをカプセル化された変数です。  
  
```  
CAnimationVariable m_bValue;  
```  
  
##  <a name="m_gvalue"></a>CAnimationColor::m_gValue  
 アニメーションの色の緑の成分を表すアニメーションをカプセル化された変数です。  
  
```  
CAnimationVariable m_gValue;  
```  
  
##  <a name="m_rvalue"></a>CAnimationColor::m_rValue  
 アニメーションの色の赤の要素を表すアニメーションをカプセル化された変数です。  
  
```  
CAnimationVariable m_rValue;  
```  
  
##  <a name="operator_colorref"></a>CAnimationColor::operator COLORREF  
  
```  
operator COLORREF();
```   
  
### <a name="return-value"></a>戻り値  
  
##  <a name="operator_eq"></a>CAnimationColor::operator =  
 CAnimationColor に色を割り当てます。  
  
```  
void operator=(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 `color`  
 新しい値をアニメーションの色を指定します。  
  
### <a name="remarks"></a>コメント  
 お勧めをアニメーションの開始前に行うにはこの演算子は、それが作成された場合の色要素の基になる COM オブジェクトを作成し直さ SetDefaultValue を呼び出すためです。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
##  <a name="setdefaultvalue"></a>CAnimationColor::SetDefaultValue  
 既定値を設定します。  
  
```  
void SetDefaultValue(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 `color`  
 赤、緑、青のコンポーネントの新しい既定値を指定します。  
  
### <a name="remarks"></a>コメント  
 既定値をアニメーション オブジェクトに設定するのにには、この関数を使用します。 このメソッドは、既定値をアニメーションの色の色要素に代入します。 それが作成された場合は、基になる COM オブジェクトも再作成します。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
## <a name="see-also"></a>参照  
 [クラス](../../mfc/reference/mfc-classes.md)
