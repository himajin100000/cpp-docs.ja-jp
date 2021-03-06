---
title: "リソースの追加 ダイアログ ボックス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.insertresource
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], adding
- Add Resource dialog box
ms.assetid: e9fb6967-738f-47e8-ab58-728cf35b3af0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aab285109b34b1de2187e02956cfff2e5a0ba724
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="add-resource-dialog-box"></a>[リソースの追加] ダイアログ ボックス
このダイアログ ボックスは、C++ Windows デスクトップ アプリケーション プロジェクトにリソースを追加するときに使用します。  
  
> [!NOTE]
>  この情報は、ユニバーサル Windows プラットフォーム アプリでのリソースには適用されません。 詳細については、次を参照してください。[アプリのリソースおよびリソース管理システム](/windows/uwp/app-resources/)です。  
  
 **リソースの種類**  
 作成するリソースの種類を指定します。  
  
 カーソルおよびダイアログ ボックスのリソースのカテゴリを展開すると、さらにリソースを表示できます。 ...\Microsoft Visual Studio でこれらのリソースがある`version`\VC\VCResourceTemplates\\< LCID\>\mfc.rct です。 .Rct ファイルを追加する場合、このディレクトリ内に配置する必要がありますを指定する必要があります、[インクルード パス](../windows/how-to-specify-include-directories-for-resources.md)にします。 これらのファイルのリソースは、該当するカテゴリの第 2 レベルに表示されます。 追加できる .rct ファイル数については、事前に設定された制限はありません。  
  
 ツリー コントロールの最上位レベルに表示されるリソースは、Visual Studio に用意されている既定のリソースです。  
  
 **新規**  
 選択した種類に基づいてリソースを作成、**リソースの種類**ボックス。 リソースが適切なエディターで開きます。 たとえば、ダイアログ リソースを作成する場合で開きます、[ダイアログ エディター](../windows/dialog-editor.md)です。  
  
 **Import**  
 開く、**インポート**をすることができますリソースに移動する ダイアログ ボックスで、現在のプロジェクトにインポートします。 ビットマップ、アイコン、カーソル、HTML リソース ファイル、サウンド (.WAV) リソース ファイル、またはカスタム リソース ファイルをインポートできます。  
  
 **カスタム**  
 開く、[新規カスタム リソース ダイアログ ボックス](../windows/new-custom-resource-dialog-box.md)カスタム リソースを作成できます。 カスタム リソースを編集するには、バイナリ エディターを使用する必要があります。  
  
## <a name="requirements"></a>必要条件  
 なし  
  
## <a name="see-also"></a>参照  
 [方法: リソースを作成する](../windows/how-to-create-a-resource.md)