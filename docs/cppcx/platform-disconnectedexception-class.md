---
title: "Platform::disconnectedexception クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::DisconnectedException
- VCCORLIB/Platform::DisconnectedException::DisconnectedException
dev_langs:
- C++
helpviewer_keywords:
- Platform::DisconnectedException
ms.assetid: c25e0d64-5bff-4c21-88e5-c4ec2776fa7f
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 175d132f2c6734f5f8328baee8cbdc4ea7e1b4c3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="platformdisconnectedexception-class"></a>Platform::DisconnectedException クラス
存在しなくなった COM サーバーを COM プロキシ オブジェクトが参照しようとするとスローされます。  
  
## <a name="syntax"></a>構文  
  
```  
public ref class DisconnectedException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="remarks"></a>コメント  
 クラス A が別のプロセスにある他のクラス (クラス B) を参照している場合、クラス A には、クラス B を保持するプロセス外の COM サーバーと通信するプロキシ オブジェクトが必要になります。サーバーがメモリ不足になってもクラス A が認識しないことがあります。 この場合、例外 RPC_E_DISCONNECTED はスローされ、Platform::DisconnectedException に変換されます。 これが発生する 1 つのシナリオは、イベント ソースに渡されたデリゲートをイベント ソースが呼び出したものの、イベントをサブスクライブした後のある時点でデリゲートが破棄された場合です。 この場合、イベント ソースは、呼び出しリストからそのデリゲートを削除します。  
  
 詳細については、 [COMException](../cppcx/platform-comexception-class.md) クラスを参照してください。  
  
### <a name="requirements"></a>必要条件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## <a name="see-also"></a>参照  
 [Platform::COMException クラス](../cppcx/platform-comexception-class.md)