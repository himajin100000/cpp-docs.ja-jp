---
title: .SETFRAME | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .SETFRAME
dev_langs:
- C++
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fce923925cba53e0c5f8dc57450cbfb64b00e056
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="setframe"></a>.SETFRAME
指定のレジスタを使用してアンワインド情報のフレームの塗りつぶしレジスタ フィールドとオフセット (`reg`) とオフセット (`offset`)。 オフセットは 16 の倍数である必要があります 240 以下です。 このディレクティブはまた、生成、`UWOP_SET_FPREG`アンワインド コード エントリを現在のプロローグのオフセットを使用して、指定した登録します。  
  
## <a name="syntax"></a>構文  
  
```  
.SETFRAME reg, offset  
```  
  
## <a name="remarks"></a>コメント  
 .SETFRAME できる ml64.exe フレーム関数をアンワインドするとはから拡張すると、プロローグ内でのみ使用する方法を指定、 [PROC](../../assembler/masm/proc.md)フレームの宣言、[です。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブです。 これらのディレクティブは、コードを生成しません。のみを生成する`.xdata`と`.pdata`です。 .SETFRAME は、実際にはアンワインドにアクションを実装する命令によって先行されなければなりません。 アンワインド ディレクティブとして、本来はマクロでのアンワインドに同意を得るようにコードの両方をラップすることをお勧めします。  
  
 詳細については、次を参照してください。 [x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)です。  
  
## <a name="sample"></a>サンプル  
  
### <a name="description"></a>説明  
 次の例では、フレーム ポインターを使用する方法を示します。  
  
### <a name="code"></a>コード  
  
```  
; ml64 frmex2.asm /link /entry:frmex2 /SUBSYSTEM:CONSOLE  
_text SEGMENT  
frmex2 PROC FRAME  
   push rbp  
.pushreg rbp  
   sub rsp, 010h  
.allocstack 010h  
   mov rbp, rsp  
.setframe rbp, 0  
.endprolog  
   ; modify the stack pointer outside of the prologue (similar to alloca)  
   sub rsp, 060h  
  
   ; we can unwind from the following AV because of the frame pointer     
   mov rax, 0  
   mov rax, [rax] ; AV!  
  
   add rsp, 060h  
   add rsp, 010h  
   pop rbp  
   ret  
frmex2 ENDP  
_text ENDS  
END  
```  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)