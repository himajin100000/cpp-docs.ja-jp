---
title: -/Qvec-report (自動ベクター化レポート作成レベル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 43c9a182046ff148621151107a98932cc39835f2
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="qvec-report-auto-vectorizer-reporting-level"></a>/Qvec-report (自動ベクター化レポート作成レベル)
コンパイラのレポート機能を有効[自動ベクター化](../../parallel/auto-parallelization-and-auto-vectorization.md)し、コンパイル時に出力の情報メッセージのレベルを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/Qvec-report:{1}{2}  
```  
  
## <a name="remarks"></a>コメント  
 **/Qvec-レポート: 1**  
 ループのベクター化は、情報メッセージを出力します。  
  
 **/Qvec-レポート: 2**  
 ループがベクター化が、ループがベクター化されていない、理由コードと共にが情報メッセージを出力します。  
  
 理由コードとメッセージについては、次を参照してください。[ベクター化と並行化メッセージ](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)です。  
  
### <a name="to-set-the-qvec-report-compiler-option-in-visual-studio"></a>Visual Studio で/Qvec-report コンパイラ オプションを設定するには  
  
1.  **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、 **[プロパティ]**をクリックします。  
  
2.  **プロパティ ページ**ダイアログ ボックスで、 **C/C++****コマンド ライン**です。  
  
3.  **追加オプション**ボックスに、入力`/Qvec-report:1`または`/Qvec-report:2`です。  
  
### <a name="to-set-the-qvec-report-compiler-option-programmatically"></a>/Qvec-report コンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> のコード例を使用してください。  
  
## <a name="see-also"></a>参照  
 [/Q オプション (低水準の操作)](../../build/reference/q-options-low-level-operations.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [ネイティブ コードでの並列プログラミング](http://go.microsoft.com/fwlink/p/?linkid=263662)