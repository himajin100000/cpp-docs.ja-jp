---
title: "トラブルシューティング C/C++ 分離アプリケーションおよびサイド バイ サイド アセンブリ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- troubleshooting side-by-side assemblies
- troubleshooting isolated applications
- troubleshooting Visual C++
ms.assetid: 3257257a-1f0b-4ede-8564-9277a7113a35
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3ea32a33a3194282657999712effbad0e334bea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="troubleshooting-cc-isolated-applications-and-side-by-side-assemblies"></a>C/C++ 分離アプリケーションおよび side-by-side アセンブリのトラブルシューティング
依存するライブラリが見つからない場合は、C/C++ アプリケーションの読み込みに失敗する場合があります。 ここでは、C/C++ アプリケーションの読み込みに失敗するいくつかの一般的な理由について説明し、問題を解決する手順を提示します。  
  
 side-by-side アセンブリに対する依存関係を指定するマニフェストがアプリケーションに含まれていて、そのアセンブリが実行可能ファイルと同じフォルダーにも %WINDIR%\WinSxS\ フォルダーのネイティブ アセンブリ キャッシュにもプライベート アセンブリとしてインストールされていないことが原因でアプリケーションが読み込みに失敗した場合、アプリケーションを実行しようとしている Windows のバージョンに応じて、次のいずれかのエラー メッセージが表示されることがあります。  
  
-   アプリケーションを正しく初期化できませんでした (0xc0000135)。  
  
-   アプリケーション構成が正しくないため、このアプリケーションの開始に失敗しました。 アプリケーションを再度インストールすることにより問題が解決する場合があります。  
  
-   指定されたプログラムを実行できません。  
  
 アプリケーションにマニフェストが含まれておらず、Windows が一般的な検索場所で見つけることができない DLL にアプリケーションが依存している場合、次のようなエラー メッセージが表示されることがあります。  
  
-   このアプリケーションがあるためにの開始に失敗しました*必要な DLL*が見つかりませんでした。 アプリケーションをインストールし直すとこの問題は解決される場合があります。  
  
 Visual Studio がインストールされていないコンピューターにアプリケーションが配置されていて、上記と似たエラー メッセージでアプリケーションがクラッシュした場合は、次の点を確認してください。  
  
1.  説明されている手順に従います[Visual C アプリケーションの依存関係を理解する](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)です。 Dependency Walker では、アプリケーションまたは DLL のほとんどの依存関係を表示できます。 表示されていない DLL がある場合は、アプリケーションを実行するコンピューターにその DLL をインストールしてください。  
  
2.  オペレーティング システム ローダーは、アプリケーション マニフェストを使用してアプリケーションが依存するアセンブリを読み込みます。 マニフェストは、リソースとしてバイナリに埋め込むことも、個別のファイルとしてアプリケーション フォルダーにインストールすることもできます。 マニフェストがバイナリ内に埋め込まれているかどうかを確認するには、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] でバイナリを開き、リソースの一覧で RT_MANIFEST を探します。 埋め込まれたマニフェストが見つからない場合は、< binary_name > のような名前が、ファイルをアプリケーション フォルダーで検索します。\<拡張子 > .manifest が付いたものです。  
  
3.  アプリケーションが side-by-side アセンブリに依存していて、マニフェストが存在しない場合は、リンカーにプロジェクトのマニフェストを生成させる必要があります。 リンカー オプションをオン**生成マニフェスト**で、**プロジェクト プロパティ**プロジェクトのダイアログ ボックス。  
  
4.  マニフェストがライブラリ内に埋め込まれている場合は、RT_MANIFEST の ID がこのタイプのバイナリに適した ID であることを確認します。 使用するリソース ID の詳細については、次を参照してください。[サイド バイ サイド アセンブリを使用するリソース (Windows) として](http://msdn.microsoft.com/library/windows/desktop/aa376617.aspx)です。 マニフェストが個別ファイルの場合は、XML エディターまたはテキスト エディターで開きます。 マニフェストと配置のルールの詳細については、次を参照してください。[マニフェスト](http://msdn.microsoft.com/library/aa375365)です。  
  
    > [!NOTE]
    >  埋め込みマニフェストと個別マニフェスト ファイルの両方が存在する場合、オペレーティング システム ローダーは埋め込みマニフェストを使用し、個別ファイルは無視します。 ただし、Windows XP ではその反対です。つまり、個別マニフェスト ファイルが使用され、埋め込みマニフェストは無視されます。  
  
5.  DLL が `LoadLibrary` 呼び出しによって読み込まれるときには外部マニフェストは無視されるため、すべての DLL にマニフェストを埋め込むことをお勧めします。 詳細については、次を参照してください。[アセンブリ マニフェスト](http://msdn.microsoft.com/library/aa374219)です。  
  
6.  マニフェストに列挙されているすべてのアセンブリがコンピューターに正しくインストールされていることを確認します。 各アセンブリは、名前、バージョン番号、およびプロセッサ アーキテクチャでマニフェストに指定されます。 アプリケーションは、サイド バイ サイド アセンブリに依存する場合は、これらのアセンブリが正しくインストールされているコンピューターのオペレーティング システム ローダーは、それらを検出できるようにする」の説明に従ってを確認[Assembly Searching Sequence](http://msdn.microsoft.com/library/aa374224)です。 64 ビット アセンブリは、32 ビット プロセスで読み込んだり、32 ビット オペレーティング システムで実行したりできないことに注意してください。  
  
## <a name="example"></a>例  
 Visual C を使用してビルドされた appl.exe、アプリケーションがあると仮定します。 アプリケーション マニフェストは、ID が 1 のバイナリ リソース RT_MANIFEST として appl.exe 内に埋め込まれているか、個別ファイル appl.exe.manifest として格納されています。 このマニフェストの内容は次のようになります。  
  
```  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <dependency>  
    <dependentAssembly>  
      <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"></assemblyIdentity>  
    </dependentAssembly>  
  </dependency>  
</assembly>  
```  
  
 このマニフェストは、オペレーティング システム ローダーに対して、appl.exe が、32 ビットの x86 プロセッサ アーキテクチャ用にビルドされた Fabrikam.SxS.Library という名前のバージョン 2.0.20121.0 のアセンブリに依存していることを通知します。 依存 side-by-side アセンブリは、共有アセンブリまたはプライベート アセンブリとしてインストールできます。  
  
 共有アセンブリのアセンブリ マニフェストは、%WINDIR%\WinSxS\Manifests\ フォルダーにインストールされます。 また、アセンブリを識別して、その内容 (アセンブリに含まれる DLL) を一覧表示します。  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
   <noInheritable/>  
   <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
   <file name="Fabrikam.Main.dll" hash="3ca5156e8212449db6c622c3d10f37d9adb1ab12" hashalg="SHA1"/>  
   <file name="Fabrikam.Helper.dll" hash="92cf8a9bb066aea821d324ca4695c69e55b2d1c2" hashalg="SHA1"/>  
</assembly>  
```  
  
 サイド バイ サイド アセンブリが使用することができますも[発行者構成ファイル](http://msdn.microsoft.com/library/aa375682)— ポリシー ファイルとも呼ばれる — が同じ別のバージョンではなく 1 つのバージョンのサイド バイ サイド アセンブリを使用するには、アプリケーションおよびアセンブリをグローバルにリダイレクトするにはアセンブリ。 共有アセンブリのポリシーは、%WINDIR%\WinSxS\Policies\ フォルダーで確認できます。 ポリシー ファイルの例を次に示します。  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  
   <assemblyIdentity type="win32-policy" name="policy.2.0.Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
   <dependency>  
      <dependentAssembly>  
         <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
         <bindingRedirect oldVersion="2.0.10000.0-2.0.20120.99" newVersion="2.0.20121.0"/>  
      </dependentAssembly>  
   </dependency>  
</assembly>  
```  
  
 このポリシー ファイルは、アプリケーションまたはアセンブリが、このアセンブリのバージョン 2.0.10000.0 を要求する場合は、代わりにシステムに現在インストールされているバージョン 2.0.20121.0 を使用するように指定しています。 アプリケーションのマニフェストで示されたアセンブリのバージョンがポリシー ファイルに指定されている場合、ローダーは、マニフェストで指定されたバージョンのアセンブリを、%WINDIR%\WinSxS\ フォルダーで探します。このバージョンがインストールされていない場合、読み込みは失敗します。 バージョン 2.0.20121.0 のアセンブリがインストールされていない場合、バージョン 2.0.10000.0 のアセンブリを要求するアプリケーションで読み込みが失敗します。  
  
 ただし、アセンブリは、インストールされたアプリケーションのフォルダーにプライベート side-by-side アセンブリとしてインストールされている可能性もあります。 オペレーティング システムは、共有アセンブリとしてのアセンブリの検出に失敗した場合、そのアセンブリをプライベート アセンブリとして次の順序で検索します。  
  
1.  フォルダーを調べて、アプリケーションのマニフェスト ファイルの名前を持つ\<assemblyName > .manifest が付いたものです。 この例では、ローダーは、appl.exe が格納されているフォルダーで Fabrikam.SxS.Library.manifest を検索します。 マニフェストが見つかった場合、ローダーはアプリケーション フォルダーからアセンブリを読み込みます。 アセンブリが見つからない場合、読み込みは失敗します。  
  
2.  開こうと、 \\< assemblyName\>\、appl.exe が格納されているフォルダー内のフォルダー場合\\< assemblyName\>\ が存在する名前を持つマニフェスト ファイルを読み込むしようとしています。 \<assemblyName >。このフォルダーからマニフェストします。 ローダーがからアセンブリを読み込みますマニフェストが見つかった場合、 \\< assemblyName\>\ フォルダー。 アセンブリが見つからない場合、読み込みは失敗します。  
  
 ローダーで依存アセンブリを検索する方法の詳細については、次を参照してください。 [Assembly Searching Sequence](http://msdn.microsoft.com/library/aa374224)です。 ローダーがプライベート アセンブリとしての依存アセンブリの検出に失敗した場合、読み込みは失敗し、"指定されたプログラムを実行できません。" というメッセージが表示されます。 このエラーを解決するには、依存アセンブリとそれを構成する DLL をプライベート アセンブリまたは共有アセンブリとしてコンピューターにインストールする必要があります。  
  
## <a name="see-also"></a>参照  
 [分離アプリケーションとサイド バイ サイド アセンブリの概念](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)