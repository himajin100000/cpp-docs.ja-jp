---
title: "_ _vmx_vmclear |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __vmx_vmclear
dev_langs:
- C++
helpviewer_keywords:
- VMCLEAR instruction
- __vmx_vmclear intrinsic
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 323fcf37ee9ecc9e62abe5d6fdc30944e58862f8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="vmxvmclear"></a>__vmx_vmclear
**Microsoft 固有の仕様**  
  
 指定された仮想マシン制御構造 (VMCS) を初期化し、起動状態に設定`Clear`です。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char __vmx_vmclear(  
   unsigned __int64 *VmcsPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `VmcsPhysicalAddress`|クリアする VMCS の物理アドレスを格納する 64 ビット メモリ位置へのポインター。|  
  
## <a name="return-value"></a>戻り値  
  
|[値]|説明|  
|-----------|-------------|  
|0|操作が成功しました。|  
|1|現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。|  
|2|有効な状態がないため操作は失敗しました。|  
  
## <a name="remarks"></a>コメント  
 アプリケーションはいずれかを使用して VM 入力操作を実行することができます、 [_ _vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)または[_ _vmx_vmresume](../intrinsics/vmx-vmresume.md)関数。 [_ _Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)関数は起動状態が VMCS でのみ使用できます`Clear`、および[_ _vmx_vmresume](../intrinsics/vmx-vmresume.md)関数は起動状態が VMCS でのみ使用できます`Launched`です。 そのため、使用、 [_ _vmx_vmclear](../intrinsics/vmx-vmclear.md)に VMCS の起動状態を設定する関数`Clear`です。 使用して、 [_ _vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 、最初の VM 入力操作の関数と[_ _vmx_vmresume](../intrinsics/vmx-vmresume.md)関数の後続の VM 入力操作します。  
  
 `__vmx_vmclear`関数と同じ、`VMCLEAR`マシン語命令します。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、「Intel 仮想化技術仕様の「ia-32 Intel アーキテクチャ」、ドキュメントの検索に番号 C97063 002 を文書化、 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127)サイトです。  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__vmx_vmclear`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [__vmx_vmresume](../intrinsics/vmx-vmresume.md)