---
title: "登録 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- servers [MFC], initializing
- initializing servers [MFC]
- OLE, registration
- installing servers [MFC]
- registry [MFC], OLE item database
- registration databases [MFC]
- servers [MFC], installing
- OLE server applications [MFC], registering servers
ms.assetid: 991d5684-72c1-4f9e-a09a-9184ed12bbb9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 636a0c2ff254957724511a067fa64533cb4837aa
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2018
---
# <a name="registration"></a>登録
ユーザーがアプリケーションに OLE 項目を挿入しようとすると、OLE から選択するオブジェクトの種類の一覧が表示されます。 OLE は、すべてのサーバー アプリケーションによって提供される情報を含むシステムの登録情報データベースからこの一覧を取得します。 登録すると、サーバー自体、システムの登録データベース (レジストリ) にエントリを提供するオブジェクトの種類ごとの説明、ファイルの拡張機能、およびその他の情報をそれ自体にパス  
  
 フレームワークと OLE システム ダイナミック リンク ライブラリ (DLL) は、このレジストリを使用して OLE 項目の種類が、システムで利用できるかを判断します。 OLE システム Dll もこのレジストリを使用してリンクまたは埋め込みオブジェクトがアクティブになったときに、サーバー アプリケーションを起動する方法を決定します。  
  
 この記事がインストールされている場合に行う必要がある各サーバー アプリケーションについて説明し、それが実行されるたびにします。  
  
 システムの登録データベースおよび更新に使用される .reg ファイルの形式の詳細については、次を参照してください。、 *OLE プログラマーズ リファレンス*です。  
  
##  <a name="_core_server_installation"></a>サーバーのインストール  
 最初に、サーバー アプリケーションをインストールする場合はサポートしている OLE 項目のすべての種類を登録する必要があります。 サーバーのスタンドアロン アプリケーションとして起動するたびに、システムの登録データベースを更新することもできます。 これにより、登録情報データベース最新の状態、サーバーの実行可能ファイルが移動された場合。  
  
> [!NOTE]
>  アプリケーション ウィザードによって自動的に生成された MFC アプリケーションはスタンドアロン アプリケーションとして実行された場合、登録します。  
  
 インストール中にアプリケーションを登録する場合は、RegEdit.exe プログラムを使用します。 アプリケーションで、セットアップ プログラムを追加する場合、セットアップ プログラムの実行がある"RegEdit/S *appname*.reg"です。 (/S フラグが静かな動作を示すは、そのコマンドが正常に完了を報告 ダイアログ ボックスに表示されません。)それ以外の場合、RegEdit を手動で実行するユーザーに指示します。  
  
> [!NOTE]
>  アプリケーション ウィザードで作成した .reg ファイルには、実行可能ファイルの完全なパスは含まれません。 インストール プログラムは、またはインクルード インストール ディレクトリを PATH 環境変数を変更する実行可能ファイルの完全なパスを含める .reg ファイルを変更するか必要があります。  
  
 レジストリ エディターでは、登録情報データベースに .reg テキスト ファイルの内容をマージします。 データベースを確認するか、それを修復するには、レジストリ エディターを使用します。 OLE の基本エントリを削除しないように注意してください。  
  
##  <a name="_core_server_initialization"></a>サーバーの初期化  
 アプリケーション ウィザードを使用して、サーバー アプリケーションを作成するときにウィザードが完了すべての初期化タスクを自動的にします。 このセクションでは、必要なこと、サーバー アプリケーションを手動で作成する場合について説明します。  
  
 コンテナー アプリケーションでサーバー アプリケーションを開始すると、OLE システム Dll は、サーバーのコマンドラインに「/埋め込み」オプションを追加します。 サーバー アプリケーションの動作はため実行を開始すると、アプリケーションで行う必要があります最初に、チェックをコンテナーによって起動されたかどうかによって異なります、「/埋め込み」または"-Embedding"、コマンドラインでオプションです。 このスイッチが存在する場合は、一連の異なるサーバーか、インプレース アクティブなリソースを読み込むか、完全を開きます。 詳細については、次を参照してください。[メニューとリソース: サーバーの変更点](../mfc/menus-and-resources-server-additions.md)です。  
  
 サーバー アプリケーションを呼び出す必要がありますもその`CWinApp::RunEmbedded`コマンドラインを解析する関数。 0 以外の値が返された場合、アプリケーションする必要がありますウィンドウを表示できませんスタンドアロン アプリケーションとしてではなく、コンテナー アプリケーションから実行されました。 この関数は、システムの登録情報データベースとの呼び出しで、サーバーのエントリを更新、`RegisterAll`メンバー関数のインスタンスを登録します。  
  
 サーバー アプリケーションの起動時には、インスタンスの登録を実行できることを確認する必要があります。 インスタンスの登録は、サーバーがアクティブでコンテナーからの要求を受信する準備ができている OLE システム Dll を通知します。 登録データベース エントリは追加されません。 呼び出すことにより、サーバーのインスタンスの登録を実行、`ConnectTemplate`によって定義されたメンバー関数`COleTemplateServer`です。 これは、接続、`CDocTemplate`オブジェクトを`COleTemplateServer`オブジェクト。  
  
 `ConnectTemplate`関数は 3 つのパラメーターを受け取ります。 サーバーの**CLSID**、へのポインター、`CDocTemplate`オブジェクト、および、サーバーが複数のインスタンスをサポートするかどうかを示すフラグ。 ミニサーバーは複数のインスタンスをサポートできる必要があります、つまり、できる必要が同時に、各コンテナーのいずれかを実行するサーバーの複数のインスタンス。 その結果、渡す**TRUE**ミニサーバーを起動するときに、このフラグを使用します。  
  
 定義上は常に、コンテナーによって起動されますミニサーバーを記述する場合。 まだ「/埋め込み」オプションを確認するためのコマンドラインを解析する必要があります。 コマンドラインでこのオプションがない場合は、ユーザーがスタンドアロン アプリケーションとしてミニサーバーを起動しようとしたことを意味します。 これが発生した場合、サーバー システムの登録データベースを登録およびミニサーバーはコンテナー アプリケーションからを起動するユーザーに通知するメッセージ ボックスを表示します。  
  
## <a name="see-also"></a>参照  
 [OLE](../mfc/ole-in-mfc.md)   
 [サーバー](../mfc/servers.md)   
 [CWinApp::RunAutomated](../mfc/reference/cwinapp-class.md#runautomated)   
 [CWinApp::RunEmbedded](../mfc/reference/cwinapp-class.md#runembedded)   
 [COleTemplateServer クラス](../mfc/reference/coletemplateserver-class.md)
