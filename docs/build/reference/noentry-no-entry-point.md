---
title: "-NOENTRY (エントリ ポイントなし) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ResourceOnlyDLL
- /noentry
dev_langs:
- C++
helpviewer_keywords:
- entry points [C++], linker specifying
- -NOENTRY linker option
- resource-only DLLs [C++], creating
- NOENTRY linker option
- /NOENTRY linker option [C++]
- DLLs [C++], creating
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5990123d809a5fdaa00e3fd44666dd3fc37c69bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="noentry-no-entry-point"></a>/NOENTRY (エントリ ポイントなし)
```  
/NOENTRY  
```  
  
## <a name="remarks"></a>コメント  
 /NOENTRY オプションは、実行可能コードが含まれていない、リソースだけの DLL を作成するために必要です。 詳細については、次を参照してください。 [Resource-Only DLL の作成](../../build/creating-a-resource-only-dll.md)です。  
  
 このオプションを使用すると、`_main` 関数への参照が DLL ファイルにリンクされなくなります。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**リンカー**フォルダーです。  
  
3.  選択、**詳細**プロパティ ページ。  
  
4.  変更、**エントリ ポイントなし**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リソース専用 DLL の作成](../../build/creating-a-resource-only-dll.md)   
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)