---
title: "@ (コンパイラ応答ファイルの指定) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- '@'
dev_langs:
- C++
helpviewer_keywords:
- response files, C/C++ compiler
- '@ compiler option'
- cl.exe compiler, specifying response files
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 698039e22a8c760097d009454db5a3872666729b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="-specify-a-compiler-response-file"></a>@ (コンパイラ応答ファイルの指定)
コンパイラ応答ファイルを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
@response_file  
```  
  
## <a name="arguments"></a>引数  
 `response_file`  
 コンパイラのコマンドを含むテキスト ファイル。  
  
## <a name="remarks"></a>コメント  
 応答ファイルには、コマンドラインで指定するとどのようなコマンドを含めることができます。 これは、コマンドライン引数は、127 文字を超えた場合に便利ですできます。  
  
 指定することはできません、  **@** から応答ファイル内ではオプションです。 つまり、応答ファイルには、別の応答ファイルを埋め込むことはできません。  
  
 コマンドラインから多くの応答ファイル オプションを指定できます (たとえば、 `@respfile.1 @respfile.2`) します。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
-   応答ファイルは、開発環境内から指定することはできませんし、コマンドラインで指定する必要があります。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   このコンパイラ オプションをプログラムで変更できません。  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)