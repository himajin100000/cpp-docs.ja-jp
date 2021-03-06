---
title: "ATL コントロール ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding controls
- controls [ATL], adding to projects
- ATL Control Wizard
ms.assetid: 991f8e72-ffbc-4382-a4ce-e255acfba5b6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5a9167153c2b827e1bc2597e830e9b3c82ee31b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atl-control-wizard"></a>ATL コントロール ウィザード
ATL プロジェクト (または ATL サポートを MFC プロジェクト) への挿入、ATL コントロール。 このウィザードを使用して、3 種類のコントロールの 1 つを挿入することができます。  
  
-   標準コントロール  
  
-   複合コントロール  
  
-   DHTML コントロール  
  
 さらに、ことを指定する最小限の制御からインターフェイスを削除する、[インターフェイス](../../atl/reference/interfaces-atl-control-wizard.md) ボックスの一覧を開くにはほとんどのコンテナーでコントロールの既定値として提供されます。 内のコントロールをサポート インターフェイスを設定することができます、**インターフェイス**ウィザードのページです。  
  
## <a name="remarks"></a>コメント  
 このウィザードで生成された登録スクリプトは、HKEY_LOCAL_MACHINE ではなく HKEY_CURRENT_USER の下には、その COM コンポーネントを登録します。 この動作を変更するには、設定、**すべてのユーザー コンポーネントを登録**ATL ウィザードのオプションです。  
  
## <a name="names"></a>名前  
 オブジェクト、インターフェイス、およびプロジェクトに追加するクラスの名前を指定します。 除く**短い名前**、その他のすべてのボックス別に変更することができます。 テキストを変更する場合**短い名前**、このページの他のすべてのボックスの名前に、変更が反映されます。 変更した場合、**コクラス**のセクションでは、COM、変更の名前が反映されます、**型**ボックスで、ですが、**インターフェイス**名および**ProgID**しないでください変わりません。 この名前付けの動作は、コントロールを開発する際に簡単に識別できるように、すべての名前に設計されています。  
  
> [!NOTE]
>  **コクラス**は属性を持たないコントロールのみで編集します。 編集することはできません、プロジェクトが考えられる場合**コクラス**です。  
  
### <a name="c"></a>C++  
 オブジェクトを実装するために作成された C++ クラスの情報を提供します。  
  
 **短い名前**  
 オブジェクトの省略名を設定します。 指定した名前が、クラスを決定し、**コクラス**ファイルの名前 (です。CPP とします。H) 名、インターフェイス名、および**型**名前をそれらのフィールドを個別に変更しない限り、します。  
  
 **クラス**  
 オブジェクトを実装するクラスの名前を設定します。 この名前は内に指定した名前に基づいて**短い名前**、'C'、クラス名の一般的なプレフィックスが付きます。  
  
 **.h ファイル**  
 新しいオブジェクトのクラスのヘッダー ファイルの名前を設定します。 既定では、この名前は、名に基づいてで提供される**短い名前**です。 ファイル名を任意の場所に保存するか、既存のファイルに、クラスの宣言を追加する、省略記号ボタンをクリックします。 既存のファイルを選択した場合、ウィザードに保存されません、選択した場所まで をクリック**完了**です。  
  
 ウィザードでは、ファイルは上書きされません。 クリックすると、既存のファイルの名前を選択するかどうかは**完了**ウィザードの指示に従って、クラス宣言が、ファイルの内容に追加されるかどうかを指定するようにします。 をクリックして**はい**; ファイルを追加する をクリックして**なし**ウィザードに戻り、別のファイル名を指定します。  
  
 **.cpp ファイル**  
 新しいオブジェクトのクラスの実装ファイルの名前を設定します。 既定では、この名前は、名に基づいてで提供される**短い名前**です。 ファイル名を任意の場所に保存する、省略記号ボタンをクリックします。 クリックするまで、選択した場所にファイルが保存されません**完了**ウィザード。  
  
 ウィザードでは、ファイルは上書きされません。 クリックすると、既存のファイルの名前を選択するかどうかは**完了**ウィザードの指示に従って、クラスの実装が、ファイルの内容に追加されるかどうかを指定するようにします。 をクリックして**はい**; ファイルを追加する をクリックして**なし**ウィザードに戻り、別のファイル名を指定します。  
  
 **属性付き**  
 オブジェクトが属性を使用するかどうかを示します。 属性付きの ATL プロジェクトにオブジェクトを追加する場合は、このオプションが選択されを変更するには使用できません。 つまり、属性のサポートで作成されたプロジェクトに、属性付きのオブジェクトのみを追加できます。  
  
 属性付きのオブジェクトは、属性を使用して ATL プロジェクトにのみ追加できます。 属性のサポートがない ATL プロジェクトに対してこのオプションを選択した場合、ウィザードの指示に従って属性のサポートをプロジェクトに追加するかどうかを指定します。  
  
 既定で、このオプションを設定した後に追加するすべてのオブジェクトを属性として指定されます (チェック ボックスが選択されています)。 属性を使用しないオブジェクトを追加するには、このボックスをオフにすることができます。  
  
 参照してください[アプリケーションの設定、ATL プロジェクト ウィザード](../../atl/reference/application-settings-atl-project-wizard.md)と[属性の基本的なしくみ](../../windows/basic-mechanics-of-attributes.md)詳細についてはします。  
  
### <a name="com"></a>COM  
 オブジェクトの COM 機能に関する情報を提供します。  
  
 **コクラス**  
 オブジェクトによってサポートされているインターフェイスの一覧を含むコンポーネント クラスの名前を設定します。  
  
> [!NOTE]
>  属性を使用してプロジェクトを作成するか、指定したこのウィザード ページで、コントロールが属性を使用する場合は、ATL が含まれていないためこのオプションを変更することはできません、**コクラス**属性。  
  
 **Interface**  
 オブジェクトのインターフェイスの名前を設定します。 既定では、インターフェイス名は"I"が先頭に追加されます。  
  
 **Type**  
 レジストリに表示されるオブジェクトの説明を設定します。  
  
 **ProgID**  
 コンテナーは、オブジェクトの CLSID の代わりに使用できる名前を設定します。 このフィールドは自動的に作成されません。 このフィールドを手動で設定しない場合、制御できない場合がありますを他のツールです。 なしで生成されている ActiveX コントロールなど、`ProgID`では使用できない、 **ActiveX コントロールの挿入** ダイアログ ボックス。 ダイアログ ボックスの詳細については、次を参照してください。 [ActiveX コントロールの挿入 ダイアログ ボックス](../../windows/insert-activex-control-dialog-box.md)です。  
  
## <a name="see-also"></a>参照  
 [ATL コントロール](../../atl/reference/adding-an-atl-control.md)   
 [複合コントロールへの機能の追加](../../atl/adding-functionality-to-the-composite-control.md)   
 [ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)

